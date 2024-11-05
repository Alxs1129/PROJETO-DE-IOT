Projeto: Monitoramento de Umidade do Solo e Controle com LED






1. Descrição
Este projeto visa monitorar a umidade do solo e a temperatura ambiente, utilizando sensores DHT11 e HD-38, para controlar o estado de LEDs e um buzzer.
O sistema também transmite os dados coletados via Bluetooth, proporcionando um feedback remoto sobre as condições do solo e ambiente.
 O microcontrolador utilizado é o Arduino, que gerencia tanto a leitura dos sensores quanto o acionamento de componentes de saída, como LEDs e o buzzer.
O sensor DHT11 realiza a medição de temperatura e umidade relativa do ar, enquanto o sensor de umidade do solo HD-38 permite avaliar a quantidade de água presente no solo.
O sistema utiliza três LEDs (vermelho, amarelo e verde) para indicar diferentes níveis de umidade do solo, e um buzzer para sinalizar quando a umidade está fora da faixa ideal.
Além disso, os dados coletados são enviados para um dispositivo remoto por meio de um módulo Bluetooth, possibilitando a visualização das informações em tempo real.

2. Objetivos
>Monitorar a umidade do solo: Medir a quantidade de umidade no solo através do sensor HD-38.
>Monitorar a temperatura e umidade do ar: Medir as condições ambientais utilizando o sensor DHT11.
>Controle de LEDs e Buzzer: Acionar LEDs e buzzer para indicar as condições da umidade do solo:
>LED vermelho acende quando a umidade do solo está abaixo de 40%.
>LED verde acende quando a umidade do solo está entre 40% e 60%.
>LED amarelo acende quando a umidade do solo está acima de 60%.
>Buzzer é ativado sempre que a umidade do solo estiver fora da faixa ideal.
>Comunicação Bluetooth: Enviar os dados de temperatura, umidade do ar e do solo para um dispositivo remoto via Bluetooth.


3. Organização Eletrônica
   
O circuito é composto pelos seguintes componentes:

Arduino (Plataforma de desenvolvimento):
O microcontrolador (responsável por ler os dados dos sensores, controlar os LEDs, o buzzer e enviar os dados via Bluetooth.)

Sensores:

DHT11: Sensor de temperatura e umidade do ar, conectado ao pino digital 7.
HD-38: Sensor de umidade do solo, conectado ao pino analógico A0.
LEDs e Buzzer:

LEDs
(vermelho, amarelo e verde) conectados aos pinos digitais 2, 3 e 4, respectivamente.
Buzzer conectado ao pino digital 8.
Módulo Bluetooth (HC-05 ou similar): Conectado aos pinos 10 (RX) e 11 (TX) para comunicação serial.



4. Descrição do Algoritmo
O processo de funcionamento é descrito abaixo:

Inicialização dos componentes:

Inicializa o monitor serial para debug.
Inicializa a comunicação Bluetooth.
Configura os pinos de entrada e saída para os sensores e atuadores (LEDs e buzzer).
Leitura dos sensores:

O sensor DHT11 é lido para obter a temperatura e a umidade do ar.
O sensor de umidade do solo HD-38 é lido para obter o valor da umidade do solo.
Processamento dos dados:

A leitura do sensor de umidade do solo é mapeada para um valor entre 0 e 100, representando a umidade em percentual.
Com base nos valores lidos, o sistema decide qual LED acender:
LED vermelho se a umidade do solo for inferior a 40% (indica que o solo está seco).
LED verde se a umidade do solo estiver entre 40% e 60% (indica que o solo está em condições ideais).
LED amarelo se a umidade do solo for superior a 60% (indica que o solo está muito úmido).
O buzzer é ativado quando a umidade do solo estiver fora da faixa de 40% a 60%.
Exibição de dados:

Os dados de temperatura e umidade do ar, bem como a umidade do solo, são exibidos no monitor serial.
As mesmas informações são enviadas via Bluetooth para um dispositivo remoto.
Controle do tempo:

O sistema executa essas operações a cada 2 segundos, garantindo que as leituras e os controles sejam feitos periodicamente.
