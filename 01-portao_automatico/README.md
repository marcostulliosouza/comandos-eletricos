# PROJETO 01 – PORTÃO AUTOMÁTICO

![diagrama_comando](https://github.com/marcostulliosouza/comandos-eletricos/blob/main/01-portao_automatico/imagem_diagrama.png)

## DESCRIÇÃO

Este projeto implementa a lógica de controle de um **PORTÃO AUTOMÁTICO DESLIZANTE**, utilizando sensores de fim de curso e botões de acionamento. O objetivo é simular o funcionamento de abertura e fechamento automático do portão conforme as regras especificadas no exercício.

O sistema executa automaticamente o ciclo de **ABERTURA E FECHAMENTO**, além de possuir uma **SINALIZAÇÃO ATIVA ENQUANTO O PORTÃO ESTIVER ABERTO OU EM MOVIMENTO**.

---

## FUNCIONAMENTO DO SISTEMA

O portão opera de acordo com as seguintes regras:

1. Quando **B1** ou **B2** for acionado, o portão **COMEÇA A ABRIR AUTOMATICAMENTE**.
2. Ao alcançar o **SENSOR DE FIM DE CURSO DE ABERTURA (F1)**, o portão **INVERTE O MOVIMENTO E COMEÇA A FECHAR**.
3. Ao alcançar o **SENSOR DE FIM DE CURSO DE FECHAMENTO (F2)**, o portão **PARA E PERMANECE AGUARDANDO UM NOVO ACIONAMENTO**.
4. Caso **B1 OU B2 SEJAM PRESSIONADOS ENQUANTO O PORTÃO ESTÁ ABRINDO OU FECHANDO**, **NENHUMA AÇÃO DEVE OCORRER**.
5. Sempre que o portão **ESTIVER ABERTO OU EM MOVIMENTO**, a **SINALIZAÇÃO (LED) DEVE PERMANECER ACIONADA**.

---

## COMPONENTES DO SISTEMA

* **B1** – BOTÃO DE ACIONAMENTO INTERNO
* **B2** – BOTÃO DE ACIONAMENTO EXTERNO
* **F1** – SENSOR DE FIM DE CURSO (PORTÃO TOTALMENTE ABERTO)
* **F2** – SENSOR DE FIM DE CURSO (PORTÃO TOTALMENTE FECHADO)
* **M1** – MOTOR DO PORTÃO
* **LED** – SINALIZADOR DE ESTADO DO PORTÃO

---

## ESTADOS DO PORTÃO

| ESTADO   | DESCRIÇÃO                            | LED       |
| -------- | ------------------------------------ | --------- |
| ABRINDO  | MOTOR MOVIMENTA O PORTÃO PARA ABRIR  | LIGADO    |
| ABERTO   | PORTÃO TOTALMENTE ABERTO             | LIGADO    |
| FECHANDO | MOTOR MOVIMENTA O PORTÃO PARA FECHAR | LIGADO    |
| FECHADO  | PORTÃO TOTALMENTE FECHADO            | DESLIGADO |

---

## LÓGICA DE OPERAÇÃO

* O portão **INICIA O CICLO DE ABERTURA** ao receber um comando.
* Após atingir o limite de abertura (**F1**), **AUTOMATICAMENTE INICIA O FECHAMENTO**.
* O ciclo **TERMINA AO ATINGIR O LIMITE DE FECHAMENTO (F2)**.
* O sistema **IGNORA NOVOS COMANDOS ENQUANTO O PORTÃO ESTIVER EM MOVIMENTO**.

---

## OBJETIVO DO PROJETO

Este exercício tem como objetivo praticar:

* LÓGICA DE CONTROLE
* AUTOMAÇÃO INDUSTRIAL
* CONTROLE DE MOTORES
* USO DE SENSORES DE FIM DE CURSO
* IMPLEMENTAÇÃO DE LÓGICA SEQUENCIAL

---

## ESTRUTURA DO REPOSITÓRIO

```
01-portao_automatico/
│
├── README.md
├── IMAGEM_DIAGRAMA.png
└── DIAGRAMA.cad
```

---

