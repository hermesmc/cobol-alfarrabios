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

  Quando precisamos gerar um arquivo posicional a partir de um que tenha a informação, separada uma da outra por um caracter definido(geralmente ";"), onde cada informação deve ser obtida conforme a posição no arquivo, por exemplo: A data de nascimento do cliente está na posição 30 até a 40, podemos utilizar o comando UNSTRING em um programa Cobol. Primeiro deve ser lido o arquivo e cada linha colocada em uma variável com o tamanho total da linha. Depois, deve ser usado o comando UNSTRING e informado o separador. Na sequencia devem ser colocadas as variáveis que receberam o conteúdo separado.
  
  Ex.:
  
  
