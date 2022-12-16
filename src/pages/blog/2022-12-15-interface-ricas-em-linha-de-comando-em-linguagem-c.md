---
templateKey: blog-post
title: Interface ricas em linha de comando em linguagem C
date: 2022-12-15T08:36:25.134Z
description: "Interface ricas em linha de comando em linguagem C - um guia de
  como usando aritmética basica as interface em linha de comando podem ser
  aplicados conhecimentos de UI e UX...  "
featuredpost: true
featuredimage: /img/tutorials.png
tags:
  - ux ui langC
---
Uma das grandes vantagens de linguagens mais próximas ao hardware são as possibilidade de usar a imaginação.

Sem desprender da preformace como usar as técnicas de ***UX*** e ***UI*** em aplicação via linha de comando?

Pensemos assim se o nos temos uso do cursor em interface gráficas porquê não simular o mesmo comportamento no nosso código, em vez, de usar números para está função:

**\#include <conio.h>** está linha importa uma serie de funções para o nosso caso. Mas será fácil? Bem depende do tempo que temos para estudar-a-lá, e ela não e do grupo padrão das livrarias de funções em compiladores como ***“gcc”***, embora como temos o objetivo de interfaces fácil e agora confesso também rápidas se não desrespeitaria uma das condições de ***UX***.

**getch()** do grupo de funções da library citada acima lê o valor inteiro correspondente a tabela **ASCII** <https://en.wikipedia.org/wiki/ASCII> . Segundo está vem as teclas das setas do teclado podem ser o nosso cursor( *não esquecemos falamos de linhas de comando e não interface gráficas!*).

Se definimos as constantes das teclas:

**\#define teclaBaixo 80\
#define teclaCima 72\
#define teclaDirecta 77\
#define teclaEsquerda 75\
#define teclaESC 27\
#define teclaEnter 13**

Podemos dizer que temos as nossas teclas de navegação o que nos permitirá por exemplo: usando os operadores aritméticos e algum dos lógicos teremos. Por exemplo uma das implementações possíveis:

**if((posição!=0)&&(menu==75)){\
posição-=1;}\
else if((posição!=1)&&(menu==77)){\
posição+=1;}**

Chamemos assim que na primeira condição permite exibir:

**printf(“este \n\n\n\n\n \t\t \*\*continuar\*\*\t Sair\n”);**

e caso temos a segunda condição?

**printf(“este \n\n\n\n\n \t\t continuar\t \*\*Sair\*\*\n”);**

Mas como isso será possível? R: usando uma as diversa formas de limpar a tela poderemos criar uma interface verdadeiramente rica como os princípios de ***UX*** recomendam.

Agora podem perguntar e o UI fica de fora? Não necessário mente com hoje em dia a agilidade urge em programação poderemos analisar um simples caso como a criação de cabeçalhos:

***Nome: cabecalho*\
*Tipo: procedimento*\
*operação: imprime no top da tela um cabeçalho*\
*entrada : nome da tela (uma string);*\
*saida : ;*\
*processamento: imprimir na tela hospital josina machel com borda***\
**\*/**\
**void cabecalho(char nomeDaTela\[61])\
{\
int espaco_a_esquerda=0, espaco_a_directa=0, espaco=0;\
printf(“%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c\n\
%c\t\t\t Hospital Josina machel\t\t\t\t %c\n\
%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c\n\
“,201, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205,205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205,\
205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205,205, 205,205,205,205,205,205,187,186,186\
,200, 205, 205, 205, 205, 205, 203, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205, 205,205, 205,205,203,205,205,205,205,205,188);\
printf(“ %c”,186);\
espaco=60- strlen(nomeDaTela);//a calcular o número de caracteres restantes\
if((espaco%2)==0)//a ver se o\
{\
espaco_a_esquerda=espaco/2;\
espaco_a_directa=espaco/2;\
}\
else if((espaco%2)!=0)\
{\
espaco-=1;\
espaco_a_esquerda=espaco/2;\
espaco_a_directa=(espaco/2)+1;\
}\
for(espaco=0; espaco<= espaco_a_esquerda;espaco++)\
printf(“ “);\
retificarcaracteres(nomeDaTela);\
printf(“%s”,nomeDaTela);\
for(espaco=0; espaco<= espaco_a_directa ;espaco++ )\
printf(“ “);\*\***\
printf(“ %c\n\
%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c%c\n\
“,186,200,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,205,188);\
}\*\*

assim como a tabela **ASCII** mapeia as teclas de do teclado e se torna muito mais poderosa quando em linhas de comando usamos o mapeamento para exbir *“caracteres secretos na tela”… e isso torna a função auto explicativa.*