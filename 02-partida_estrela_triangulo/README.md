# PROJETO 03 – PARTIDA ESTRELA-TRIÂNGULO

![diagrama\_comando](https://github.com/marcostulliosouza/comandos-eletricos/blob/main/02-partida_estrela_triangulo/imagem_diagrama.png)

## DESCRIÇÃO

Este projeto implementa o sistema de **PARTIDA ESTRELA-TRIÂNGULO PARA MOTOR TRIFÁSICO**, utilizando contatores, relé térmico de proteção e temporizador para comutação automática.

O objetivo é reduzir a **corrente de partida do motor**, iniciando o funcionamento em **ligação estrela** e, após um tempo determinado, realizar a comutação automática para **ligação triângulo**, permitindo operação em regime nominal.

A temporização é realizada pelo relé **K4**, ajustado para **5 segundos**, responsável pela transição entre os modos de partida.

---

## FUNCIONAMENTO DO SISTEMA

O sistema opera conforme as seguintes etapas:

1. Ao pressionar a botoeira de acionamento (**S1**), o motor inicia em **LIGAÇÃO ESTRELA**.
2. Os contatores de linha e estrela são energizados simultaneamente.
3. O temporizador **K4** inicia a contagem de **5 segundos**.
4. Após o tempo ajustado:

   * O contator estrela é desligado.
   * O contator triângulo é acionado automaticamente.
5. O motor passa a operar em **REGIME NORMAL (TRIÂNGULO)**.
6. Ao pressionar **S0 (STOP)**, todo o sistema é desligado.
7. O relé térmico (**RT1**) protege o motor contra sobrecarga.

---

## COMPONENTES DO SISTEMA

### Elementos de Força

* **DJ1** – Disjuntor de proteção geral
* **KM1** – Contator de Linha
* **KM2** – Contator Estrela
* **KM3** – Contator Triângulo
* **RT1** – Relé térmico de proteção
* **M1** – Motor Trifásico

### Elementos de Comando

* **F1 / F2** – Relés monofásicos de alimentação do comando
* **S0** – Botoeira de DESLIGAR (STOP)
* **S1** – Botoeira de PARTIDA (START)
* **K1** – Relé auxiliar de selagem
* **K4** – Relé temporizador (5 segundos)
* **Contatos auxiliares KM1, KM2 e KM3** – Intertravamento elétrico

---

## ESTADOS DE OPERAÇÃO

| ESTADO           | DESCRIÇÃO                            |
| ---------------- | ------------------------------------ |
| PARADO           | Motor desligado                      |
| PARTIDA ESTRELA  | Motor parte com corrente reduzida    |
| TEMPORIZANDO     | K4 realizando contagem de 5 segundos |
| REGIME TRIÂNGULO | Motor operando em potência nominal   |

---

## LÓGICA DE OPERAÇÃO

* O acionamento do sistema ocorre através de **auto retenção (selagem)**.
* Inicialmente, o motor é conectado em **estrela**, reduzindo corrente e torque de partida.
* O temporizador **K4** inicia a contagem assim que o motor é acionado.
* Após 5 segundos:

  * O circuito estrela é interrompido.
  * O circuito triângulo é habilitado.
* Existe **intertravamento elétrico** entre os contatores estrela e triângulo, impedindo acionamento simultâneo.
* O botão **S0** remove a alimentação do comando.
* O relé térmico interrompe o circuito em caso de sobrecarga.

---

## OBJETIVO DO PROJETO

Este exercício tem como objetivo praticar:

* PARTIDA ESTRELA-TRIÂNGULO
* REDUÇÃO DE CORRENTE DE PARTIDA
* TEMPORIZAÇÃO EM COMANDOS ELÉTRICOS
* INTERTRAVAMENTO ENTRE CONTATORES
* CIRCUITOS DE POTÊNCIA E COMANDO
* PROTEÇÃO DE MOTORES TRIFÁSICOS

---

## ESTRUTURA DO REPOSITÓRIO

```
02-partida_estrela_triangulo/
│
├── README.md
├── IMAGEM_DIAGRAMA.png
└── DIAGRAMA_ESTRELA_TRIANGULO.cad
```
