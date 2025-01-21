# Comandos Essenciais do Kafka
## Init o Kafka e o Zookeeper
    - Iniciar o Zookeeper (necessário para o Kafka)
bin/zookeeper-server-start.sh config/zookeeper.properties

    - Iniciar o Kafka
bin/kafka-server-start.sh config/server.properties
## Stop o Kafka e o Zookeeper
bin/kafka-server-stop.sh
bin/zookeeper-server-stop.sh
## Criar um novo tópico
bin/kafka-topics.sh --create --topic <nome-do-topico> --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1
## Listar todos os tópicos
bin/kafka-topics.sh --list --bootstrap-server localhost:9092
## Exibir detalhes do tópico 
bin/kafka-topics.sh --describe --topic <nome-do-topico> --bootstrap-server localhost:9092
## Deletar um tópico
bin/kafka-topics.sh --delete --topic <nome-do-topico> --bootstrap-server localhost:9092
## Produzir mensagens para um tópico (modo interativo)
bin/kafka-console-producer.sh --topic <nome-do-topico> --bootstrap-server localhost:9092
## Consumir mensagens de um tópico
bin/kafka-console-consumer.sh --topic <nome-do-topico> --bootstrap-server localhost:9092 --from-beginning
## Contar o número de mensagens em um tópico
bin/kafka-run-class.sh kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic <nome-do-topico> --time -1
## Listar grupos de consumidores
bin/kafka-consumer-groups.sh --list --bootstrap-server localhost:9092
## Descrever um grupo de consumidores
bin/kafka-consumer-groups.sh --describe --group <nome-do-grupo> --bootstrap-server localhost:9092
## Redefinir o deslocamento de consumidores (offsets)
bin/kafka-consumer-groups.sh --reset-offsets --group <nome-do-grupo> --topic <nome-do-topico> --to-earliest --bootstrap-server localhost:9092
## Produzir mensagens de um arquivo
bin/kafka-console-producer.sh --topic <nome-do-topico> --bootstrap-server localhost:9092 < arquivo.txt
## Consumir mensagens e salvar em um arquivo
bin/kafka-console-consumer.sh --topic <nome-do-topico> --bootstrap-server localhost:9092 --from-beginning > mensagens.txt
## Alterar o número de partições de um tópico
bin/kafka-topics.sh --alter --topic <nome-do-topico> --partitions 5 --bootstrap-server localhost:9092
## Exibir logs do servidor Kafka
tail -f logs/kafka-server.log
## Exibir logs do Zookeeper
tail -f logs/zookeeper.log
## Contar o número de mensagens em um tópico
bin/kafka-run-class.sh kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic <nome-do-topico> --time -1
# Produtor
    - Publica msg em tópicos específicos, distribuidas entre suas partições
    - Decide para qual partição enviar, e suporta diferentes estrátegias de particionamento(hashing key,round,robin)
    - Possui diferentes níveis de garantia de entrega( fire-and forget, at least once, exactly once)
    - Usa protocolo TCP para comunicação eficient com cluster do Kafka
    
    *Fluxo
    - Msg Criada -> Serializer -> Particionamento -> Envio assíncrono -> Confirmação Recebimento
    -> Reptição em caso de erro(Dependendo da config, produtor pode reenviar a mensagem
## Criando Produtor
```text
import org.apache.kafka.clients.producer.*;

import java.util.Properties;

        public class KafkaProducerExample {
            public static void main(String[] args) {
                // Configurações do produtor
                Properties props = new Properties();
                props.put("bootstrap.servers", "localhost:9092");  // Endereço do broker
                props.put("key.serializer", "org.apache.kafka.common.serialization.StringSerializer");
                props.put("value.serializer", "org.apache.kafka.common.serialization.StringSerializer");
                props.put("acks", "all");  // Garantia de entrega
                props.put("retries", 3);   // Tentativas de reenvio em caso de falha
        
                // Criando o produtor
                KafkaProducer<String, String> producer = new KafkaProducer<>(props);
        
                // Criando a mensagem (tópico, chave, valor)
                ProducerRecord<String, String> record = new ProducerRecord<>("meu-topico", "chave1", "Olá, Kafka!");
        
                // Enviando mensagem de forma assíncrona
                producer.send(record, (metadata, exception) -> {
                    if (exception == null) {
                        System.out.println("Mensagem enviada para a partição " + metadata.partition() +
                                " com offset " + metadata.offset());
                    } else {
                        exception.printStackTrace();
                    }
                });
        
                producer.close();  // Finalizar o produtor
            }
        }

```
## Configs Do Produtor
        Parâmetro	                    Descrição	                    Valores Possíveis
    bootstrap.servers	    Lista de brokers Kafka para conexão.	    localhost:9092,localhost:9093
    key.serializer	        Serializador para a chave da mensagem.	    StringSerializer, ByteArraySerializer
    value.serializer	    Serializador para o valor da mensagem.	    StringSerializer, JsonSerializer
    acks	C               onfirmação de recebimento pelo broker.	        0, 1, all
    retries	                Número de tentativas em caso de falha.	        Inteiro (ex: 3)
    linger.ms	        Tempo de espera antes de enviar lote de msg.	    Inteiro (ex: 5 ms)
    batch.size	            Tamanho max lote de mensagens.	                Bytes (ex: 16384)
    compression.type	Tipo de compressão para reduzir tamanho.	    none, gzip, snappy, lz4
## Garantia de Entrega
    - At most once: msg pode ser perdida, mas nunca duplicada
        * Config: acks=0, retries=0
    - At least Once: msg pode ser duplicada,mas nunca perdida
        * Config: acks=1, retries > 0
    - Exaclty Once: Nenhuma msg sera perdida ou duplicada ( requer trasações Kafka )
        * Config: acks=all, enable.idempotence=true
# Partição
## Conceito
    - São usadas para distribuir a carga entre os brokers e consumidores
    - Ordenação: garantida dentro da partição, não há garantia de ordem entre partições distintas do mesmo tópico
    - Replicação: Cada partição pode ser atribuida a um ou mais brokers, tolerancia a falha
    - OFF-set: 
    - Poll:
## Vantagem
    - Escalabilidade horizontal: Mais partições, mais consumers trabalhando
    - Tolerancia a falhas: Na falha de um broker,dados podem ser recuperados, com a replicação das partições
## Distribuição das MSG
    - Partition KEY: Msg com a mesma chave vão para mesma partição, usa função HASH para isso
```text 
        ProducerRecord<String, String> record = new ProducerRecord<>("orders", "customer-123", "Pedido #123");
```
    - Round-ROBIN: Sem fornecer chave, a distribuição é feita de forma balanceada algoritmo ROUND-ROBIN
## Replicação de Partições
    - Partition Leader: Broker principal que lida com leitura e escrita
    - Follower Replica: Copias para redundancia, assume em caso de falaha do lider
## Comandos Partição
    - Kafka não permite reduzir o num de partições após criação
    - Aumenta ro num de partições pode quebrar a ordenação das msg
### Topico multiplas partições
bin/kafka-topics.sh --create --topic meu-topico --bootstrap-server localhost:9092 --partitions 4 --replication-factor 2
### Aumentando num partições
bin/kafka-topics.sh --alter --topic meu-topico --partitions 6 --bootstrap-server localhost:9092
# Cosumidor
    - Serviço que se conecta ao kluster, inscreve-se em tópicos, consome msg de suas partições
    - Trabalahm em conjunto de grupos de consumidores, garantindo balanceamento de carga e tolerancia falaha
    - Fluxo:    
        consumer conecta ao broker -> inscreve-se no tópico -> Kafka atribui a partição ao consumer
    -> consumer chama regularmente poll() para buscar msg -> Processa msg e confirma leitura via commit offset
    -> KAfka redistribui partições automaticamente caso consumer entrem ou saiam do grupo
## Componentes 
### Group Consumer: 
    - Coleção de ocnsumidores que consomem msg de um ou mias tópicos
    - Cada partição é atribuida a apenas um consumer dentro do mesmo grupo
    - Especificando um grupo:
        * props.put("group.id", "grupo-pedidos");
### Offset:
    - Identificador único para cada msg dentro da partição
    - Permite consumer acompanhar o seu progresso e saiba onde começar da proxima msg
    - ajuda o kafka a recuperar falhas
    - COMMITS
        * automático: kafka armazena automaticamente em intervalos regulares os offset
            - config: props.put("enable.auto.commit", "true");
                      props.put("auto.commit.interval.ms", "1000"); // Commit a cada 1 segundo
        * manual: Consumer decide quando commitar, controle total
            - config: consumer.commitSync();  // Commit síncrono
                      consumer.commitAsync(); // Commit assíncrono
## Consumo de MSG
    - Earliest: Comsome todas as msg desde o inicio da partição
        * Config: props.put("auto.offset.reset", "earliest");
    - Latest: Consome msg publicadas apenas após a conexão
         * Config: props.put("auto.offset.reset", "latest");
## Falhas no consumer
    - Retries e exception: Implementar tentativa de reprocessamento no cod consumer
    - Partições Presas: Configurar alertas para consumer que nao avaçam nos offset
    - Rebalanceamento frequente: Avaliar o tmepo de polling e manter consumer ativos
## Criando Consumer
```text
        import org.apache.kafka.clients.consumer.ConsumerRecords;
        import org.apache.kafka.clients.consumer.ConsumerRecord;
        import org.apache.kafka.clients.consumer.KafkaConsumer;
        
        import java.time.Duration;
        import java.util.Collections;
        import java.util.Properties;
        
        public class KafkaConsumerExample {
            public static void main(String[] args) {
                Properties props = new Properties();
                props.put("bootstrap.servers", "localhost:9092");
                props.put("group.id", "meu-grupo");
                props.put("key.deserializer", "org.apache.kafka.common.serialization.StringDeserializer");
                props.put("value.deserializer", "org.apache.kafka.common.serialization.StringDeserializer");
                props.put("enable.auto.commit", "false");  // Commit manual do offset
                props.put("auto.offset.reset", "earliest"); // Começa do início caso não tenha offset salvo
        
                KafkaConsumer<String, String> consumer = new KafkaConsumer<>(props);
                consumer.subscribe(Collections.singletonList("meu-topico"));
        
                while (true) {
                    ConsumerRecords<String, String> records = consumer.poll(Duration.ofMillis(1000));
        
                    for (ConsumerRecord<String, String> record : records) {
                        System.out.println("Recebido: " + record.value() + " com offset " + record.offset());
                    }
        
                    consumer.commitSync();  // Confirmação manual do offset
                }
            }
        }

```
## Config Consumidor
        Parâmetro	                Descrição	                            Valores possíveis
    bootstrap.servers	        Lista de brokers para conexão	                localhost:9092
    group.id	                Grupo de consumidores	                        meu-grupo
    auto.offset.reset	Onde iniciar a leitura se não houver offset salvo	    earliest, latest
    enable.auto.commit	Define se o commit de offset será automático	        true, false
    session.timeout.ms	Tempo de timeout antes do consumidor ser considerado morto	45000
    max.poll.records	Número máximo de mensagens processadas por poll	             100
# Se e De serialização
