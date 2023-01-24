# Trabalho 2 - Fundamentos de Sistemas Embarcados

Nome: Wictor Bastos Girardi
Matrícula: 17/0047326

## Introdução

No trabalho, o aluno deverá desenvolver o software que efetua o controle de temperatura do forno utilizando dois atuadores para este controle: um resistor de potência de 15 Watts utilizado para aumentar temperatura e; uma ventoinha que puxa o ar externo (temperatura ambiente) para reduzir a temperatura do sistema.
Os comandos do usuário do sistema para definir a temperatura desejada serão controlados de duas maneiras:

Manualmente através do seletor de temperatura no dashboard (Thingsboad);
Automaticamente seguindo uma curva de temperatura pré-definida em arquivo de configuração (Arquivo da Curva).

O controle da temperatura será realizado através da estratégia PID onde deverão estar disponíveis para o usuário o ajuste dos parâmetros Kp, Ki e Kd nas configurações do sistema (Via terminal).

Para mais informações: <https://gitlab.com/fse_fga/trabalhos-2022_2/trabalho-2-2022-2>

## Como executar

Entrando na pasta raíz do projeto em: https://github.com/Wictorgirardi/Trabalho-2-FSE

Execute os comandos:

```
make
bin/bin
```

Os comando `make` irá compilar o código e o `bin/bin` irá executá-lo.

## Execução

Dentro do programa o usuário pode realizar o controle das placas de duas formas:

* 1 - Manual
* 2 - Dashboard


### Manual

Para controle manual do forno o usuario deve entrar com os seguintes valores:

* Controle Proporcional (P): ajusta a variável de controle de forma proporcional ao erro, ou seja, quanto maior o erro, maior a intensidade de acionamento do resistor (0 a 100%). Esse ajuste é feito pela variável Kp.

* Controle Integral (PI): ajusta a variável de controle baseando-se no tempo em que o erro acontece, acumulando este erro (integral). Esse ajuste é feito pela variável Ki.

* Controle Derivativo (PD): ajusta a variável de controle tendo como base a taxa de variação do erro ou a velocidade com a qual o sistema está variando o erro. Esse ajuste é feito pela variável Kd.

* Temperatura do forno desejada.

Vale lembrar que para obter as temperaturas em tempo real das placas deve-se utilizar as placas 2 ou 3, já que as placas 1 e 4 não possuem sensores BME para leitura de temperaturas.

### Dashboard

Nessa opção o usúario tem o controle da placa pela dashboard disponibilizada pelo professor, ele pode acompanhar o acionamento das funções pelo terminal da aplicação e mais detalhadamente pela live no youtube das placas.

## Vídeo de funcionamento
<https://youtu.be/lN6xB7Z2uNc>

## Gráficos de funcionamento

### Aquecimento
Curva de aquecimento mostrando sinal de controle atuando de maneira positiva para o aquecimento do resistor da placa, ao atingir o valor de refêrencia é possivel ver pelo sinal a atuação dos ventiladores da placa e o desligamento do resistor:

<img width="1041" alt="Captura de Tela 2023-01-24 às 11 09 59" src="https://user-images.githubusercontent.com/40725728/214322037-68f83e7c-139a-425a-b9d0-9363acce62c3.png">

### Resfriamento 
Curva de resfriamento mostrando sinal de controle atuando de maneira que o resistor esteja desligado e os ventiladores ligados(sinal: -100):

<img width="1019" alt="Captura de Tela 2023-01-24 às 11 14 59" src="https://user-images.githubusercontent.com/40725728/214322721-fb14fa82-680a-41a3-932e-e3cadb1caccc.png">

### Capturas de temperaturas 
Pelo terminal da aplicaçao é possivel acompanhar as temperaturas coletadas durante o aquecimento ou resfriamento da placa:
<img width="221" alt="Captura de Tela 2023-01-24 às 11 38 51" src="https://user-images.githubusercontent.com/40725728/214323555-ae67b7bf-e089-4d98-ae0e-1682a3c48081.png">



