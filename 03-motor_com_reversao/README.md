# PROJETO 04 – MOTOR TRIFÁSICO COM REVERSÃO DE GIRO

![diagrama\_comando](https://github.com/SEU-USUARIO/SEU-REPOSITORIO/imagem_diagrama.png)

## DESCRIÇÃO

Este projeto implementa o controle de **REVERSÃO DE GIRO DE UM MOTOR TRIFÁSICO**, utilizando contatores, relé térmico de proteção e circuito de comando com intertravamento elétrico.

O sistema permite operar o motor nos sentidos:

* **HORÁRIO (Direto)**
* **ANTI-HORÁRIO (Reverso)**

O projeto garante que os dois sentidos de rotação **não possam ser acionados simultaneamente**, evitando curto-circuito entre fases e danos ao equipamento.

---

## FUNCIONAMENTO DO SISTEMA

O sistema opera conforme as seguintes regras:

1. Ao pressionar **S1**, o motor gira no **SENTIDO DIRETO**.
2. Ao pressionar **S2**, o motor gira no **SENTIDO REVERSO**.
3. O acionamento de um sentido **bloqueia automaticamente** o outro.
4. Caso o motor esteja em funcionamento, o comando oposto é ignorado.
5. A botoeira **S0** realiza o **DESLIGAMENTO GERAL** do sistema.
6. O relé térmico **RT1** protege o motor contra sobrecarga.
7. Sinalizadores luminosos indicam o sentido ativo do motor.

---

## COMPONENTES DO SISTEMA

### Elementos de Força

* **Q1** – Disjuntor geral
* **KM1** – Contator sentido direto
* **KM2** – Contator sentido reverso
* **RT1** – Relé térmico de proteção
* **M1** – Motor Trifásico

### Elementos de Comando

* **F1 / F2** – Relés monofásicos de alimentação do comando
* **S0** – Botoeira DESLIGAR (STOP)
* **S1** – Botoeira giro DIRETO
* **S2** – Botoeira giro REVERSO
* **K1** – Relé auxiliar (direto)
* **K2** – Relé auxiliar (reverso)
* **H1** – Sinalização giro direto
* **H2** – Sinalização giro reverso
* **Contatos auxiliares KM1 e KM2** – Intertravamento elétrico

---

## ESTADOS DE OPERAÇÃO

| ESTADO         | DESCRIÇÃO                             |
| -------------- | ------------------------------------- |
| PARADO         | Motor desligado                       |
| GIRO DIRETO    | Motor girando no sentido horário      |
| GIRO REVERSO   | Motor girando no sentido anti-horário |
| BLOQUEIO ATIVO | Intertravamento impedindo conflito    |

---

## LÓGICA DE OPERAÇÃO

* O acionamento utiliza **selagem elétrica (auto retenção)**.
* O contator **KM1** inverte duas fases para operação direta.
* O contator **KM2** realiza a inversão de fases para reversão do giro.
* Existe intertravamento elétrico através de contatos **NF cruzados**, impedindo energização simultânea.
* Os sinalizadores indicam qual sentido está ativo.
* O botão **S0** interrompe a alimentação do comando.
* O relé térmico desarma o circuito em caso de sobrecarga.

---

## OBJETIVO DO PROJETO

Este exercício tem como objetivo praticar:

* REVERSÃO DE MOTORES TRIFÁSICOS
* INVERSÃO DE FASES
* INTERTRAVAMENTO ELÉTRICO
* COMANDOS ELÉTRICOS INDUSTRIAIS
* PROTEÇÃO DE MOTORES
* SINALIZAÇÃO DE ESTADOS OPERACIONAIS

---

## ESTRUTURA DO REPOSITÓRIO

```
03-motor_com_reversao/
│
├── README.md
├── IMAGEM_DIAGRAMA.png
└── DIAGRAMA_MOTOR_REVERSAO.cad
```