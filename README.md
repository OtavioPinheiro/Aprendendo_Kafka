# Aprendendo Kafka
Projeto com o objetivo de aprender os conceitos do Kafka.

# Sumário
- [O que é Kafka?](#o-que-é-kafka)
- [Instalando o Kafka](#instalando-o-kafka)
- [Referências](#referências)

# O que é Kafka?
> O Apache Kafka foi desenvolvido para processar fluxos de dados provenientes de diversas fontes, bem como para entregá-los a vários clientes. Em resumo, essa plataforma movimenta volumes imensos de dados não apenas do ponto A ao ponto B, mas também de A a Z e para qualquer outro local que você precisar simultaneamente.

> O Apache Kafka é uma alternativa aos sistemas de mensageria corporativos tradicionais. Inicialmente, ele era um sistema interno desenvolvido pela LinkedIn para processar 1,4 trilhão de mensagens por dia. Mas agora é uma solução de transmissão de dados open source aplicável a variadas necessidades corporativas.

**Fonte:** [Red Hat](https://www.redhat.com/pt-br/topics/integration/what-is-apache-kafka)

# Instalando o Kafka
Para fazer download do Kafka, siga para o [site oficial](https://kafka.apache.org/downloads). Realize o download da última versão do Kafka, baixando o arquivo `.tgz`. Um arquivo TGZ ou GZ é um tipo de arquivo GZIP *Compressed Tar Archive*. Ou seja, é um tipo de arquivo compactado ("zipado"). [Mais informações](https://www.lifewire.com/what-are-tgz-gz-files-2622391).

Depois de ter baixado o Kafka, descompacte o arquivo `.tgz` em uma pasta que não possua espaços e nem caracteres especiais, evitando, assim, problemas futuros na hora de excutar o Kafka.

# Comandos
Antes de apresentar os comandos usados no Kafka, é importante lembrar que para que funcionem, é necessário estar dentro da pasta do Kafka, a mesma pasta que foi gerada quando o arquivo de download foi descompactado.

| Comandos | Funcionalidade |
|----------|----------------|
| `bin/kafka-server-start.sh config/server.properties` | Sobe o servidor Kafka, usando as configurações padrões de servidor. |

# Referências
- Kafka. Kafka. Disponível em: https://kafka.apache.org/intro#intro_streaming
- Red Hat. O que é Kafka. Disponível em: https://www.redhat.com/pt-br/topics/integration/what-is-apache-kafka