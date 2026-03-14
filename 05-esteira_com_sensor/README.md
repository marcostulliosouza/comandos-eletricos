# PROJETO 05 – ESTEIRA TRANSPORTADORA COM SENSOR DE PRESENÇA

![diagrama\_comando](https://github.com/marcostulliosouza/comandos-eletricos/blob/main/05-esteira_com_sensor/imagem_diagrama.png)

## DESCRIÇÃO

Este projeto simula o funcionamento de uma **ESTEIRA TRANSPORTADORA AUTOMÁTICA**, utilizando um sensor de presença e um temporizador para controle do tempo de funcionamento do motor.

O sistema foi desenvolvido para representar aplicações industriais onde o transporte de peças ocorre somente quando há detecção de material, garantindo economia de energia e operação automática.

O motor permanece ligado por um tempo determinado após a detecção da peça, reiniciando a temporização caso uma nova peça seja detectada.

---

## FUNCIONAMENTO DO SISTEMA

O sistema opera conforme as seguintes regras:

1. O **sensor de presença (S1)** detecta a chegada de uma peça.
2. Ao detectar a peça, o **motor da esteira (M1)** é acionado.
3. O **temporizador KTM1** inicia a contagem de **10 segundos**.
4. Após o tempo ajustado, o motor é desligado automaticamente.
5. Caso uma nova peça seja detectada **antes do término da temporização**, o tempo é **reiniciado**, mantendo o motor em funcionamento.
6. A botoeira **S0** realiza o desligamento geral do sistema.

---

## COMPONENTES DO SISTEMA

### Elementos de Força

* **DSJ1** – Disjuntor geral
* **KM1** – Contator do motor
* **RT1** – Relé térmico de proteção
* **M1** – Motor trifásico da esteira

### Elementos de Comando

* **DSJ2 / DSJ3** – Proteção do circuito de comando
* **S0** – Botoeira DESLIGAR (STOP)
* **S1** – Sensor de presença (detecção da peça)
* **KTM1** – Temporizador (10 s)
* **Contato auxiliar KM1** – Selagem do circuito

---

## ESTADOS DE OPERAÇÃO

| ESTADO       | DESCRIÇÃO                          |
| ------------ | ---------------------------------- |
| AGUARDANDO   | Sistema energizado aguardando peça |
| DETECÇÃO     | Sensor identifica peça             |
| TRANSPORTE   | Motor da esteira em funcionamento  |
| TEMPORIZANDO | Contagem ativa do temporizador     |
| PARADO       | Motor desligado após tempo         |

---

## LÓGICA DE OPERAÇÃO

* O sensor atua como comando automático de partida.
* O contator **KM1** realiza a energização do motor.
* O temporizador **KTM1** é do tipo **retardo na desenergização (off-delay)** ou lógica equivalente.
* Cada nova detecção reinicia a temporização.
* O motor permanece ligado enquanto houver detecção dentro do intervalo configurado.
* O relé térmico protege o motor contra sobrecorrente.
* O botão **S0** interrompe imediatamente o funcionamento.

---

## OBJETIVO DO PROJETO

Este exercício tem como objetivo praticar:

* AUTOMAÇÃO DE TRANSPORTE INDUSTRIAL
* USO DE SENSORES EM COMANDOS ELÉTRICOS
* TEMPORIZAÇÃO RESETÁVEL
* CONTROLE AUTOMÁTICO DE MOTORES
* LÓGICA SEQUENCIAL
* ECONOMIA ENERGÉTICA EM PROCESSOS INDUSTRIAIS

---

## ESTRUTURA DO REPOSITÓRIO

```id="p06esteira"
05-esteira_com_sensor/
│
├── README.md
├── IMAGEM_DIAGRAMA.png
└── DIAGRAMA_ESTEIRA_SENSOR.cad
```
