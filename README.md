# Aprendendo Kafka
Projeto com o objetivo de aprender os conceitos do Kafka.

# Sumário
- [O que é Kafka?](#o-que-é-kafka)
- [Instalando o Kafka](#instalando-o-kafka)
- [Conceitos do Kafka](#conceitos-do-kafka)
- [Comandos](#comandos)
- [Referências](#referências)

# O que é Kafka?
> O Apache Kafka é uma plataforma distribuída de transmissão de dados que é capaz de publicar, subscrever, armazenar e processar fluxos de registro em tempo real.
> 
> O Apache Kafka foi desenvolvido para processar fluxos de dados provenientes de diversas fontes, bem como para entregá-los a vários clientes. Em resumo, essa plataforma movimenta volumes imensos de dados não apenas do ponto A ao ponto B, mas também de A a Z e para qualquer outro local que você precisar simultaneamente.
> 
> O Apache Kafka é uma alternativa aos sistemas de mensageria corporativos tradicionais. Inicialmente, ele era um sistema interno desenvolvido pela LinkedIn para processar 1,4 trilhão de mensagens por dia. Mas agora é uma solução de transmissão de dados open source aplicável a variadas necessidades corporativas.

**Fonte:** [Red Hat](https://www.redhat.com/pt-br/topics/integration/what-is-apache-kafka)

# Instalando o Kafka
Para fazer download do Kafka, siga para o [site oficial](https://kafka.apache.org/downloads). Realize o download da última versão do Kafka, baixando o arquivo `.tgz`. Um arquivo TGZ ou GZ é um tipo de arquivo GZIP *Compressed Tar Archive*. Ou seja, é um tipo de arquivo compactado ("zipado"). [Mais informações](https://www.lifewire.com/what-are-tgz-gz-files-2622391).

Depois de ter baixado o Kafka, descompacte o arquivo `.tgz` em uma pasta que não possua espaços e nem caracteres especiais, evitando, assim, problemas futuros na hora de excutar o Kafka.

# Conceitos do Kafka
A seguir alguns conceitos sobre Kafka.

## O que são sistemas de mensageria?


## O que é um *consumer*?


## O que é um *producer*?


# Comandos
Antes de apresentar os comandos usados no Kafka, é importante lembrar que para que funcionem, é necessário estar dentro da pasta do Kafka, a mesma pasta que foi gerada quando o arquivo de download foi descompactado.

**OBS-1:** Apache Kafka pode ser executado em qualquer Sistema Operacional, porém o recomendado é o Linux. Dito isso, fique ciente de que alguns bugs podem ocorrer quando executamos o Kafka no Windows e que alguns comandos e configurações podem ser diferentes devido as peculiaridades de cada sistema operacional.

**OBS-2:** Antes de iniciar o Kafka, inicie o Zookeeper primeiro!

| OS | Comandos | Funcionalidade |
|----|----------|----------------|
| Linux | `bin/zookeeper-server-start.sh config/zookeeper.properties` | Inicia o Zookeeper na porta 2181, usando as configurações padrões do servidor. |
| Windows | `.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties` |  |
| Linux | `bin/zookeeper-server-stop.sh` | Interrompe o Zookeeper na porta 2181, usando as configurações padrões do servidor. |
| Windows | `.\bin\windows\zookeeper-server-stop.bat` |  |
| Linux | `bin/kafka-server-start.sh config/server.properties` | Inicia o Kafka, usando as configurações padrões de servidor. |
| Windows | `.\bin\windows\kafka-server-start.bat .\config\server.properties` |  |
| Linux | `bin/kafka-server-stop.sh` | Interrompe o Kafka, usando as configurações padrões de servidor. |
| Windows | `.\bin\windows\kafka-server-stop.bat` |  |
| Linux | `bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic <nomeDoTópico>` | Cria um tópico no Kafka. |
| Windows | `.\bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic <nomeDoTópico>` |  |
| Linux | `bin/kafka-console-producer.sh --broker-list localhost:9092 --topic <nomeDoTópico>` | Cria um *producer* no Kafka para produzir mensagens a serem consumidas. |
| Windows | `.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic <nomeDoTópico>` |  |
| Linux | `bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic <nomeDoTópico> --from-beginning` | Cria um *consumer* no Kafka. O *consumer* começará desde o ínicio a consumir as mensagens. |
| Windows | `.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic <nomeDoTópico> --from-beginning` |  |


# Referências
- Kafka. **Kafka**. Disponível em: https://kafka.apache.org/intro#intro_streaming
- Red Hat. **O que é Kafka**. Disponível em: https://www.redhat.com/pt-br/topics/integration/what-is-apache-kafka
- HowToDoInJava. **Apache Kafka - Getting Started on Windows 10**. Disponível em: https://howtodoinjava.com/kafka/getting-started-windows-10/
- Thiago Brito. **01-Mensageria**. Diponível em: https://medium.com/@devbrito91/mensageria-1330c6032049