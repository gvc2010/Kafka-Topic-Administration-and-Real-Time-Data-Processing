# Kafka Data Streaming Project

Este projeto demonstra como configurar produtores e consumidores no Apache Kafka para enviar e receber dados de diferentes fontes.

## Pré-requisitos

- Apache Kafka instalado e em execução.
- Biblioteca `Faker` instalada para gerar dados fictícios.
- Arquivo `covid.csv` contendo dados de exemplo.

## Criando o Tópico no Kafka

Execute o seguinte comando para criar um tópico com duas partições no Apache Kafka:

```sh
kafka-topics.sh --create --topic s7projeto --bootstrap-server guilherme.venturini-broker:29092 --partitions 2 --replication-factor 1
```

## Consumidor (Consumer_covid_faker)

Este consumidor lê mensagens das partições 0 e 1 do tópico s7projeto no Apache Kafka. Ele identifica a origem dos dados (COVID ou Faker) com base no prefixo da mensagem e imprime o conteúdo correspondente

## Producer (producer_covid)

Este produtor lê dados de um arquivo CSV chamado covid.csv e envia cada linha como uma mensagem para a partição 0 do tópico s7projeto no Apache Kafka. As mensagens são prefixadas com "COVID," para identificação fácil pelo consumidor.

## Producer (producer_faker)

Este produtor utiliza a biblioteca Faker para gerar dados fictícios e envia cada conjunto de dados como uma mensagem para a partição 1 do tópico s7projeto no Apache Kafka. As mensagens são prefixadas com "FAKE," para identificação fácil pelo consumidor.
