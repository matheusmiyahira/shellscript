# shellscript
Treinamento Shell Script na 4 Linux com *Julia Cezar Neves*

## Preparando para a Aula
mkdir /home/diurno/shell
tar xzvf /home/repositorio/EXTRAS/404/ArqsDoCursoShell /home/diurno/shell


## Variaveis

´´´
diurno@tux06:~/shell$ var = 5
bash: var: comando não encontrado
diurno@tux06:~/shell$ var=5
diurno@tux06:~/shell$ echo $var
5
diurno@tux06:~/shell$ var:=5
bash: var:=5: comando não encontrado
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ _var_=5
diurno@tux06:~/shell$ var_1=5
diurno@tux06:~/shell$ 1_var=5
bash: 1_var=5: comando não encontrado
diurno@tux06:~/shell$ ls xxx
ls: não foi possível acessar 'xxx': Arquivo ou diretório inexistente
diurno@tux06:~/shell$ ls xxx 2>&-
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 

´´´

## Iniciando
Acoes do shell
0-Atributo ou cmd?
1-Redirecionador
2-Substituicao de chaves
3-Substituicao de variaveis


### Redirecionadores
#### ´>´ ou ´1>´
> ´>´ muito mais rápido que ´touch´

´´´
diurno@tux06:~/shell$ time for ((i=1;i>200;i++))
> touch arq200
bash: erro de sintaxe próximo ao token inesperado `touch'
diurno@tux06:~/shell$ time for ((i=1;i>200;i++)); { touch arq200; }

real	0m0,000s
user	0m0,000s
sys	0m0,000s
diurno@tux06:~/shell$ time for ((i=1;i>200;i++)); { touch arq200; }^C
diurno@tux06:~/shell$ time for ((i=1; i<200;i++))
> {
> touch arq200
> }

real	0m0,201s
user	0m0,164s
sys	0m0,051s
diurno@tux06:~/shell$ ^C
diurno@tux06:~/shell$ time for ((i=1;i<200;i++)); { touch arq200;}

real	0m0,206s
user	0m0,159s
sys	0m0,061s
diurno@tux06:~/shell$ time for ((i=1;i<200;i++)); { > arq200;}

real	0m0,007s
user	0m0,001s
sys	0m0,006s
diurno@tux06:~/shell$ 

´´´

> 'cat' short for contatenate
cat vai redirecionar primeiro e apagar o arquivo
´´´
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ echo uma linha > arq200
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cat arq200
uma linha
diurno@tux06:~/shell$ cat arq200 > arq200
diurno@tux06:~/shell$ cat arq200
diurno@tux06:~/shell$ 
´´´

#### ´<´ ou ´1<´
Antes de usar ´|´ tente usar ´<´, pois o ´|´ cria subshells
´´´
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ wc -l add
7 add
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cat add | wc -l
7
diurno@tux06:~/shell$ wc -l < add
7
diurno@tux06:~/shell$ 
´´´
´´´
diurno@tux06:~/shell$ mail meu@amor.com 0< mala

´´´

#### ´>>´ ou ´1>>´
Acrescenta ao inves de substituir



### Substituicao de chaves
´´´
diurno@tux06:~/shell$ echo {19..3}
19 18 17 16 15 14 13 12 11 10 9 8 7 6 5 4 3
diurno@tux06:~/shell$ echo {19..03}
19 18 17 16 15 14 13 12 11 10 09 08 07 06 05 04 03
diurno@tux06:~/shell$ echo {19..03..2}
19 17 15 13 11 09 07 05 03
diurno@tux06:~/shell$ echo {b..x}
b c d e f g h i j k l m n o p q r s t u v w x
diurno@tux06:~/shell$ echo {b..x..2}
b d f h j l n p r t v x
diurno@tux06:~/shell$ echo pe{itu,la,ga}da
peituda pelada pegada
diurno@tux06:~/shell$ 

´´´
Crianto tres pastas 1, 2 e 3 --> ´diurno@tux06:~/shell$ mkdir /home/{1,2,3}´



### Substituicao de variaveis

Neste exemplo abaixo o shell substituiu as chaves antes de substituir a variavel. Para consertar a operacao usa-se ´eval´.
´´´
diurno@tux06:~/shell$ var=19
diurno@tux06:~/shell$ echo {$var..3}
{19..3}
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ eval echo {$var..3}
19 18 17 16 15 14 13 12 11 10 9 8 7 6 5 4 3
diurno@tux06:~/shell$ 

´´´

> Nunca deixe caracteres coringas para o shell (*,?,)
´´´
diurno@tux06:~/shell$ mkdir lixo
diurno@tux06:~/shell$ cd lixo
diurno@tux06:~/shell/lixo$ touch arq{1..12}
diurno@tux06:~/shell/lixo$ ls
arq1  arq10  arq11  arq12  arq2  arq3  arq4  arq5  arq6  arq7  arq8  arq9
diurno@tux06:~/shell/lixo$ touch arq{1..12}.{sh,py}
diurno@tux06:~/shell/lixo$ ls
arq1      arq11.py  arq1.py  arq3     arq4.sh  arq6.py  arq8     arq9.sh
arq10     arq11.sh  arq1.sh  arq3.py  arq5     arq6.sh  arq8.py
arq10.py  arq12     arq2     arq3.sh  arq5.py  arq7     arq8.sh
arq10.sh  arq12.py  arq2.py  arq4     arq5.sh  arq7.py  arq9
arq11     arq12.sh  arq2.sh  arq4.py  arq6     arq7.sh  arq9.py
diurno@tux06:~/shell/lixo$ rm touch arq{1..12}.{sh,py}
rm: não foi possível remover 'touch': Arquivo ou diretório inexistente
diurno@tux06:~/shell/lixo$ rm  arq{1..12}.{sh,py}
rm: não foi possível remover 'arq1.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq1.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq2.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq2.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq3.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq3.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq4.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq4.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq5.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq5.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq6.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq6.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq7.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq7.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq8.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq8.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq9.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq9.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq10.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq10.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq11.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq11.py': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq12.sh': Arquivo ou diretório inexistente
rm: não foi possível remover 'arq12.py': Arquivo ou diretório inexistente
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ ls
arq1  arq10  arq11  arq12  arq2  arq3  arq4  arq5  arq6  arq7  arq8  arq9
diurno@tux06:~/shell/lixo$  
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ >arq
diurno@tux06:~/shell/lixo$ ls arq*
arq  arq1  arq10  arq11  arq12  arq2  arq3  arq4  arq5  arq6  arq7  arq8  arq9
diurno@tux06:~/shell/lixo$ echo arq? | wc -l
1
diurno@tux06:~/shell/lixo$ ls arq? | wc -l
9
diurno@tux06:~/shell/lixo$ ls arq?
arq1  arq2  arq3  arq4  arq5  arq6  arq7  arq8  arq9
diurno@tux06:~/shell/lixo$ 
´´´
O exemplo abaixo mostrara somente o aquivo 1. Pois nao existe de 3 a 1, restando somente o 1.
´´´
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ ls arq[3-11]
arq1
diurno@tux06:~/shell/lixo$ 
´´´
Outro exemplo.
´´´
diurno@tux06:~/shell/lixo$ ls arq[!357]?
arq10  arq11  arq12
diurno@tux06:~/shell/lixo$ 

´´´



### 
´´´

´´´
### 
´´´

´´´





