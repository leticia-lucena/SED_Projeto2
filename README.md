# A onda verde do Professor Kyller
Projeto 2 - Sistemas a Eventos Discretos

* Alexsandra Macedo Souto
* Gabriel Araújo Miranda
* Leticia Rebecca Medeiros de Lucena

# Sobre o projeto
Este projeto tem como objetivo modelar um sistema de semáforos que permita um comportamento de onda verde para os semáforos, ou seja, que o motorista chegue ao seu destino encontrando, no máximo, um sinal vermelho.
A modelagem foi realizada na ferramenta UPPALL, um ambiente integrado para modelagem, validação e verificação de sistemas em tempo real modelados como redes de autômatos temporizados.
Além da modelagem, foi realizada a simulação e a validação, utilizando lógica temporal.

## Regras do sistema

Os modelos de autômatos temporizados modelam comportamento dos 4 semáforos e de um motorista, seguindo os seguintes regras:

Distância do posto ao 1º semáforo: 1.200m
Distância do 1º ao 2º semáforo: 130m
Distância do 2º ao 3º semáforo: 160m
Distância do 3º ao 4º semáforo: 170m
Distância do 4º semáforo ao Destino: 90m
Distância total: 1.750m
Velocidade média de deslocamento: 40 km/h

# Modelagem
Para este projeto, foram modelados dois autômatos: O Semáforo e a Via.
Por se tratar de quatro semáforos, foram criadas 4 instâncias do autômato Semáforo e 4 instâncias do autômato Via, representando os quatro trechos que dependem do semáforo para passagem.

## Autômato do Semáforo
Representa o comportamento dos semáforos, contendo três estados: Vermelho, Verde e Amarelo. 

A transição entre os estados, chamada de evento, é definida pelo tempo. Cada semáforo terá um tempo de espera do estado Vermelho para Verde diferente, que irá depender da distância que o carro leva para sair de um semáforo e chegar em outro. O tempo no estado Verde é de 15 segundos e de 5 segundos no estado Amarelo.

Além disso, há o canal de comunicação síncrona entre eles, pelo qual o semáforo atual sinaliza para o seguinte, que já está apto a mudar do estado Vermelho para o Verde.

## Autômato da Via
Representa o comportamento da via, com os seguintes estados: SemCarro, CarroChegando, CarroEmMovimento, CarroNoSemaforo, CarroSaindo e ProximaVia, quando o carro entra na próxima via.

# Demonstração 

Uma demonstração da implementação e do funcionamento deste projeto pode ser observada no link abaixo:

https://youtu.be/i1-2RXinE0Q

