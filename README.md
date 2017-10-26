﻿## Projeto 3 Camada Física - 2017.2

Sabrina S.
Alexandre Y.

## Modulação Digital

## Frequência e Banda

A frequência utilizada é a que melhor divide o diagrama de constelação em dois polos espelhados. Dessa forma, nossa frequência foi de 2200Hz.
A banda ocupada pelo sinal é sempre o dobro da frequência, ou seja, 4400Hz.

## Funcionamento

O objetivo do projeto é fazer um chat que envia mensagens via modulação digital, e faz a conexão transmissor/receptor. Ao rodar o código em dois locais, é possível estabelecer um "chat virtual", usando o ar como meio.

Primeiramente, o usuário da imput na string desejada em uma UI, que recebe e envia tal string a um script de python dedicado a transforma-la e transmiti-la em bytes. 

Após a conversão para bytes ser feita, um terceiro programa, o GNURADIO, recebe estes bytes e os transmite como ondas sonoras.
Este mesmo programa é dedicado a receber os bytes e, com auxilio de um script (receiver.py), mapeia no mapa de constelações como explicado abaixo na subcategoria BPSK.

Este script receiver.py é gerado pelo próprio programa do GNURADIO, que possui um mapa visual do código, enquanto o .py não é recomendado para leitura pelo usuário, por ser um tanto complexo (por ser gerado por um computador). 

Este mesmo script realiza a demodulação e atribui cada byte a uma letra, fazendo a reconstrução da string original do usuário.

## BPSK

BPSK (Binary Phase Shift Keying) é um tipo de Phase Shift Keying que usa termos binários para modular digitalmente os sinais no mapa de constelações. Dessa forma, cada sinal é recebido ou como 0, ou como 1. 
Caso seja 0, o BPSK usa a equação S (t) = ± A* cos (2*pi*fc*t)
Caso seja 1, é usado S (t) = A* cos (2*pi*fc*t+pi)
Como os valores não são sempre iguais, devido à ruidos, o mapa fica com algumas divergências:


BPSK teórico|BPSK com ruído|
:-------------------------:|:-------------------------:
![](Imagens/bpsk.png)   |![](Imagens/bpskn.png)   


## Gráficos do Tx

### Frequencia do sinal não codificado

### Tempo e frequência do sinal codificado

### Tempo e frequência do sinal modulado

## Gráficos do Rx

### Sinal de áudio recebido no tempo e em frequência

### Sinal de áudio demodulado no tempo e em frequência

### Diagrama de Constelação
