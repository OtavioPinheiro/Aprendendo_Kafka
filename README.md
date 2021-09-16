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
A seguir alguns conceitos sobre sistemas de mensageria para ter um melhor entendimento sobre o Kafka.

## O que são sistemas de mensageria?
> Mensageria é um conceito que define que sistemas distribuídos, possam se comunicar por meio de troca de mensagens (evento), sendo que estas mensagens serão gerenciadas por um "*Message Broker* (servidor/módulo de mensagens)."

[FONTE](https://medium.com/@devbrito91/mensageria-1330c6032049).

## O que são middlewares?
> O middleware é o software que se encontra entre o sistema operacional e os aplicativos nele executados. Funcionando de forma essencial como uma camada oculta de tradução, o middleware permite a comunicação e o gerenciamento de dados para aplicativos distribuídos. Muitas vezes, o middleware é chamado de “encanamento”, uma vez que ele conecta dois aplicativos para que os dados e bancos de dados possam ser facilmente transportados através do “cano”. O uso do middleware permite que os usuários executem solicitações como enviar formulários em um navegador da Web ou permitir que o servidor Web apresente páginas dinâmicas da web com base no perfil de um usuário.
>
> Exemplos comuns de middleware incluem middleware de banco de dados, middleware de servidor de aplicativos, middleware orientado a mensagens, middleware de web e monitores de processamento de transações. Normalmente, cada programa oferece serviços de sistemas de mensagens para que diversos aplicativos possam se comunicar utilizando estruturas de mensagens como protocolo SOAP, serviços Web, REST (representational state transfer) e JSON (JavaScript Object Notation). Embora todos os tipos de middleware executem funções de comunicação, o tipo que uma empresa escolherá depende de qual serviço está sendo utilizado e qual tipo de informação deve ser comunicado. Isso pode incluir autenticação de segurança, gerenciamento de transações, consultas de mensagens, servidores de aplicativos, servidores da web e diretórios. O middleware também pode ser utilizado para processamento distribuído com ações que ocorrem em tempo real em vez de envio e recebimento repetitivo de dados.

FONTE: [Microsoft - O que é middleware?](https://azure.microsoft.com/pt-br/overview/what-is-middleware/)

## O que é um *Message Broker*?
> Os *Message Brokers* são uma tecnologia de comunicação entre aplicativos para ajudar a construir um mecanismo de integração comum para oferecer suporte a arquiteturas de nuvem híbrida, baseada em microsserviços, sem servidor (*serverless*) e nativa da nuvem.
> 
> Um *Message Broker* é um software que permite que aplicativos, sistemas e serviços se comuniquem entre si e troquem informações. O *Message Broker* faz isso traduzindo mensagens entre protocolos de mensagens formais. Isso permite que serviços interdependentes “falem” uns com os outros diretamente, mesmo que tenham sido escritos em linguagens diferentes ou implementados em plataformas diferentes.
> 
> Os *Message Brokers* são módulos de software dentro de soluções de middleware de mensagens ou de middleware orientado a mensagens (MOM). Esse tipo de middleware fornece aos desenvolvedores um meio padronizado de lidar com o fluxo de dados entre os componentes de um aplicativo para que eles possam se concentrar em sua lógica central. Ele pode servir como uma camada de comunicação distribuída que permite que aplicativos abrangendo várias plataformas se comuniquem internamente.
> 
> Os *Message Brokers* podem validar, armazenar, rotear e entregar mensagens aos destinos apropriados. Eles atuam como intermediários entre outras aplicações, permitindo que os remetentes emitam mensagens sem saber onde estão os destinatários, se estão ativos ou não, ou quantos deles existem. Isso facilita o desacoplamento de processos e serviços dentro dos sistemas.
> 
> Para fornecer armazenamento confiável de mensagens e entrega garantida, os *Message Brokers* geralmente contam com uma subestrutura ou componente chamado fila de mensagens que armazena e ordena as mensagens até que os aplicativos de consumo possam processá-las. Em uma fila de mensagens, as mensagens são armazenadas na ordem exata em que foram transmitidas e permanecem na fila até que o recebimento seja confirmado.
> 
> Mensagens assíncronas referem-se ao tipo de comunicação entre aplicativos que os *message brokers* tornam possível. Ele evita a perda de dados valiosos e permite que os sistemas continuem funcionando mesmo quando a conectividade está intermitente ou quando há problemas de latência, problemas comuns em redes públicas. O sistema de mensagens assíncronas garante que as mensagens serão entregues uma vez (e apenas uma vez) na ordem correta em relação às outras mensagens.
> 
> Os *Message Brokers* podem incluir gerenciadores de filas para lidar com as interações entre as várias filas de mensagens, bem como serviços que forneçam roteamento de dados, tradução de mensagens, persistência e funcionalidades de gerenciamento de estado do cliente.

FONTE: [IBM - Message Brokers](ttps://www.ibm.com/cloud/learn/message-brokers)

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
- IBM. ***Message Brokers***. Disponível em: https://www.ibm.com/cloud/learn/message-brokers