# cobol-alfarrabios
Lembretes de situações que não ocorrem no dia-a-dia.

<h1>Índice</h1>
<h4>1 - Cobol IIB</h4>
<a href="#C1">- Array na requisição e resposta</a><br>
<h4>2 - Cobol BATCH</h4>
<a href="#C2">- Arquivos posicionais</a><br>

<h2> <a name="C1"> - Array na requisição e resposta</ a></h2>

  Em programas Cobol IIB que precisam um array na area de requisição, e outro na área de resposta: 
  O book deve começar na posição 01 e na sua declaração,dentro do programa não deve ter nivel 1. 

<h2> <a name="C2"> - Arquivos posicionais</ a></h2>

  Quando precisamos gerar um arquivo posicional a partir de um que tenha a informação separada uma da outra por um caracter pré definido(geralmente ";"), onde cada informação deve ser obtida conforme a posição no arquivo, por exemplo: A data de nascimento do cliente está na posição 30 até a 40, podemos utilizar o comando UNSTRING em um programa Cobol. Primeiro deve ser lido o arquivo e cada linha colocada em uma variável com o tamanho total da linha. Depois, deve ser usado o comando UNSTRING e informado o separador. Na sequencia devem ser colocadas as variáveis que receberam o conteúdo separado.
  
  Exemplo:
  
  Área de entrada:
  
       01 DJOF165-TOTAL                     PIC  X(130).
  
  Area de saída
  
       01 DJOPE165-TX-LNH                   PIC  X(130).
       01 FILLER REDEFINES DJOPE165-TX-LNH.
           03 DJOPE165-NR-CONTA             PIC  X(019).
           03 DJOPE165-S1                   PIC  X(001).
           03 DJOPE165-DT-ABERTURA          PIC  X(010).
           03 DJOPE165-S2                   PIC  X(001).
           03 DJOPE165-COMARCA              PIC  X(050).
           03 DJOPE165-S3                   PIC  X(001).
           03 DJOPE165-VARA                 PIC  X(040).
           03 DJOPE165-S4                   PIC  X(008).
           
   Sintaxe do UNSTRING           
           
           UNSTRING DJOF165-TOTAL
              DELIMITED BY ';'         INTO
                 DJOPE165-NR-CONTA
                 DJOPE165-DT-ABERTURA
                 DJOPE165-COMARCA
                 DJOPE165-VARA
           END-UNSTRING.
  
  
