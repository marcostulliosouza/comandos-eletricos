# PROJETO 04 – SEQUÊNCIA DE PARTIDA DE MOTORES

![diagrama\_comando]()

## DESCRIÇÃO

Este projeto implementa um sistema de **PARTIDA SEQUENCIAL DE TRÊS MOTORES TRIFÁSICOS**, utilizando contatores, relés térmicos de proteção e temporizadores.

O objetivo é evitar picos de corrente na rede elétrica, realizando o acionamento dos motores de forma **escalonada**, com um intervalo de tempo entre cada partida.

Após o acionamento inicial, os motores são ligados na seguinte ordem:

**MOTOR 1 → MOTOR 2 → MOTOR 3**

Cada motor entra em funcionamento somente após o término do tempo de temporização do motor anterior.

---

## FUNCIONAMENTO DO SISTEMA

O sistema opera conforme as seguintes etapas:

1. Ao pressionar a botoeira **S1**, o **MOTOR 1 (M1)** é acionado.
2. Simultaneamente, o temporizador **KTM1** inicia a contagem.
3. Após o tempo ajustado no **KTM1**, o **MOTOR 2 (M2)** é acionado.
4. O temporizador **KTM2** inicia sua contagem.
5. Após o tempo ajustado no **KTM2**, o **MOTOR 3 (M3)** é acionado.
6. A botoeira **S0** realiza o **DESLIGAMENTO GERAL**, interrompendo o funcionamento de todos os motores.
7. Cada motor possui proteção individual através de relés térmicos.

---

## COMPONENTES DO SISTEMA

### Elementos de Força

* **F1** – Proteção do Motor 1
* **F2** – Proteção do Motor 2
* **F3** – Proteção do Motor 3
* **KM1** – Contator do Motor 1
* **KM2** – Contator do Motor 2
* **KM3** – Contator do Motor 3
* **RT1** – Relé térmico do Motor 1
* **RT2** – Relé térmico do Motor 2
* **RT3** – Relé térmico do Motor 3
* **M1** – Motor Trifásico 1
* **M2** – Motor Trifásico 2
* **M3** – Motor Trifásico 3

### Elementos de Comando

* **R1** – Relé de alimentação do circuito de comando
* **S0** – Botoeira DESLIGAR (STOP)
* **S1** – Botoeira PARTIDA (START)
* **KTM1** – Temporizador para partida do Motor 2
* **KTM2** – Temporizador para partida do Motor 3

---

## ESTADOS DE OPERAÇÃO

| ESTADO          | DESCRIÇÃO                         |
| --------------- | --------------------------------- |
| PARADO          | Todos os motores desligados       |
| PARTIDA MOTOR 1 | Apenas o M1 está em funcionamento |
| PARTIDA MOTOR 2 | M1 e M2 em funcionamento          |
| PARTIDA MOTOR 3 | M1, M2 e M3 em funcionamento      |

---

## LÓGICA DE OPERAÇÃO

* O sistema é iniciado através de **selagem do contator KM1**.
* Ao energizar **KM1**, o temporizador **KTM1** inicia a contagem.
* Após o tempo programado, **KM2** é acionado.
* O acionamento de **KM2** inicia a contagem do **KTM2**.
* Após o tempo programado no **KTM2**, **KM3** é energizado.
* A botoeira **S0** interrompe a alimentação do circuito de comando.
* Os relés térmicos desligam os motores em caso de sobrecarga.

---

## OBJETIVO DO PROJETO

Este exercício tem como objetivo praticar:

* PARTIDA SEQUENCIAL DE MOTORES
* TEMPORIZAÇÃO EM COMANDOS ELÉTRICOS
* COORDENAÇÃO DE CARGAS ELÉTRICAS
* CIRCUITOS DE POTÊNCIA E COMANDO
* PROTEÇÃO INDIVIDUAL DE MOTORES
* AUTOMAÇÃO DE PROCESSOS INDUSTRIAIS

---

## ESTRUTURA DO REPOSITÓRIO

```
04-sequencia_motores/
│
├── README.md
├── IMAGEM_DIAGRAMA.png
└── DIAGRAMA_SEQUENCIA_MOTORES.cad
```