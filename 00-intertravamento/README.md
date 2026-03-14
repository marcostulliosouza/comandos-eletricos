# PROJETO 02 – INTERTRAVAMENTO DE DOIS MOTORES

![diagrama\_comando](https://github.com/marcostulliosouza/comandos-eletricos/blob/main/00-intertravamento/imagem_diagrama.png)

## DESCRIÇÃO

Este projeto implementa a lógica de controle para o **INTERTRAVAMENTO ELÉTRICO DE DOIS MOTORES TRIFÁSICOS**, utilizando contatores, relés de proteção e circuito de comando convencional.

O objetivo é garantir que **apenas um motor possa operar por vez**, evitando acionamento simultâneo e protegendo o sistema elétrico e mecânico contra sobrecargas e conflitos operacionais.

O sistema utiliza comandos por botoeiras e intertravamento elétrico através dos contatos auxiliares dos contatores.

---

## FUNCIONAMENTO DO SISTEMA

O sistema opera conforme as seguintes regras:

1. Ao pressionar a botoeira **S1**, o **MOTOR 1 (M1)** é acionado.
2. Ao pressionar a botoeira **S2**, o **MOTOR 2 (M2)** é acionado.
3. O acionamento de um motor **BLOQUEIA AUTOMATICAMENTE** o acionamento do outro.
4. Caso um motor esteja em funcionamento, o comando do outro motor é **IGNORADO**.
5. A botoeira **S0** realiza o **DESLIGAMENTO GERAL**, interrompendo o funcionamento de qualquer motor ativo.
6. A proteção contra sobrecarga é realizada pelos relés térmicos **RT1** e **RT2**.
7. Os circuitos de comando operam em fase distinta do circuito de potência, garantindo maior segurança operacional.

---

## COMPONENTES DO SISTEMA

### Elementos de Força

* **DJ1** – Disjuntor do Motor 1
* **DJ2** – Disjuntor do Motor 2
* **RT1** – Relé de Proteção (Motor 1)
* **RT2** – Relé de Proteção (Motor 2)
* **KM1** – Contator do Motor 1
* **KM2** – Contator do Motor 2
* **M1** – Motor Trifásico 1
* **M2** – Motor Trifásico 2

### Elementos de Comando

* **F1** – Relé Monofásico de Comando 1
* **F2** – Relé Monofásico de Comando 2
* **S0** – Botoeira de DESLIGAR (STOP)
* **S1** – Botoeira de acionamento do Motor 1
* **S2** – Botoeira de acionamento do Motor 2
* **K1** – Relé auxiliar de comando
* **K2** – Relé auxiliar de comando
* **KM1 / KM2** – Contatos auxiliares utilizados no intertravamento elétrico

---

## ESTADOS DE OPERAÇÃO

| ESTADO         | DESCRIÇÃO                              |
| -------------- | -------------------------------------- |
| MOTOR 1 LIGADO | Apenas o M1 está em funcionamento      |
| MOTOR 2 LIGADO | Apenas o M2 está em funcionamento      |
| SISTEMA PARADO | Nenhum motor acionado                  |
| BLOQUEIO ATIVO | Um motor impede o acionamento do outro |

---

## LÓGICA DE OPERAÇÃO

* O acionamento ocorre por **auto retenção do contator** correspondente.
* O intertravamento é realizado através dos **contatos normalmente fechados (NF)** dos contatores opostos.
* Quando **KM1 está energizado**, o circuito de comando de **KM2 é interrompido**, e vice-versa.
* O botão **S0** remove a alimentação do circuito de comando, desligando qualquer motor ativo.
* Os relés térmicos interrompem o circuito em caso de sobrecarga.

---

## OBJETIVO DO PROJETO

Este exercício tem como objetivo praticar:

* COMANDOS ELÉTRICOS INDUSTRIAIS
* PARTIDA DIRETA DE MOTORES
* INTERTRAVAMENTO ELÉTRICO
* CIRCUITOS DE POTÊNCIA E COMANDO
* PROTEÇÃO DE MOTORES TRIFÁSICOS
* LÓGICA DE SELAGEM (AUTO RETENÇÃO)

---

## ESTRUTURA DO REPOSITÓRIO

```
00-intertravamento/
│
├── README.md
├── IMAGEM_DIAGRAMA.png
└── DIAGRAMA.cad
```
