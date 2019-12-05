# shellscript
Treinamento Shell Script na 4 Linux com _**Julio Cezar Neves**_

# Aula 1 - 02/Dez/2019

## Novos Comandos
Bash `Ctr+R` --> (reverse-i-search)


## Preparando para a Aula
mkdir /home/diurno/shell \
tar xzvf /home/repositorio/EXTRAS/404/ArqsDoCursoShell /home/diurno/shell


## Iniciando

### Variaveis

```
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
```
### Variáveis de sistema
> Variaveis de sistema sao maicusculas. Entao, nunca use letras mai[usculas em suas variaveis.
```
diurno@tux06:~/shell/lixo$ env | more
SHELL=/bin/bash
WINDOWID=23068675
QT_ACCESSIBILITY=1
COLORTERM=truecolor
LANGUAGE=pt_BR:pt:en
SSH_AUTH_SOCK=/tmp/ssh-1eHwm4WzP0YL/agent.945
SSH_AGENT_PID=968
XDG_SEAT=seat0
PWD=/home/diurno/shell/lixo
LOGNAME=diurno
XDG_SESSION_TYPE=x11
GPG_AGENT_INFO=/run/user/1004/gnupg/S.gpg-agent:0:1
WINDOWPATH=7
HOME=/home/diurno
LANG=pt_BR.UTF-8
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd
=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;4
4:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;
31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7
z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo
=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.
tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;3
1:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=
01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.j
pg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=0
1;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.t
iff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;
35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.m
p4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35
:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=0
1;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf
=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*
.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;
36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
VTE_VERSION=5402
XDG_SESSION_CLASS=user
TERM=xterm-256color
USER=diurno
DISPLAY=:0
SHLVL=0
XDG_VTNR=7
XDG_SESSION_ID=1
XDG_RUNTIME_DIR=/run/user/1004
PATH=/usr/local/bin:/usr/bin:/bin:/usr/games
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1004/bus
OLDPWD=/home/diurno/shell
_=/usr/bin/env
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ export |more
declare -x COLORTERM="truecolor"
declare -x DBUS_SESSION_BUS_ADDRESS="unix:path=/run/user/1004/bus"
declare -x DISPLAY=":0"
declare -x GPG_AGENT_INFO="/run/user/1004/gnupg/S.gpg-agent:0:1"
declare -x HOME="/home/diurno"
declare -x LANG="pt_BR.UTF-8"
declare -x LANGUAGE="pt_BR:pt:en"
declare -x LOGNAME="diurno"
declare -x LS_COLORS="rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd
=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=3
4;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;
31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tz
o=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz
=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.
tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;3
1:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio
=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.e
sd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=0
1;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.t
if=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;
35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.o
gm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35
:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=0
1;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm
=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*
.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00
;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:"
declare -x OLDPWD="/home/diurno/shell"
declare -x PATH="/usr/local/bin:/usr/bin:/bin:/usr/games"
declare -x PWD="/home/diurno/shell/lixo"
declare -x QT_ACCESSIBILITY="1"
declare -x SHELL="/bin/bash"
declare -x SHLVL="1"
declare -x SSH_AGENT_PID="968"
declare -x SSH_AUTH_SOCK="/tmp/ssh-1eHwm4WzP0YL/agent.945"
declare -x TERM="xterm-256color"
declare -x USER="diurno"
declare -x VTE_VERSION="5402"
declare -x WINDOWID="23068675"
declare -x WINDOWPATH="7"
declare -x XDG_RUNTIME_DIR="/run/user/1004"
declare -x XDG_SEAT="seat0"
declare -x XDG_SESSION_CLASS="user"
declare -x XDG_SESSION_ID="1"
declare -x XDG_SESSION_TYPE="x11"
declare -x XDG_VTNR="7"
diurno@tux06:~/shell/lixo$  
```


### Apostrofo, aspas simples ou plic ('), aspas duplas ("), contra barra (\) e crase (\`)
```
diurno@tux06:~/shell/lixo$ var="x    x"
diurno@tux06:~/shell/lixo$ echo `$var`
bash: x: comando não encontrado

diurno@tux06:~/shell/lixo$ echo '$var'
$var
diurno@tux06:~/shell/lixo$ echo "$var"
x    x
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ od -h <<< "$IFS"
0000000 0920 0a0a
0000004
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo -n $IFS | od -h
0000000
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo -n ¨$IFS¨ | od -h
0000000 a8c2 c220 00a8
0000005
diurno@tux06:~/shell/lixo$ echo -n '$IFS' | od -h
0000000 4924 5346
0000004
diurno@tux06:~/shell/lixo$ echo -n "$IFS" | od -h
0000000 0920 000a
0000003
diurno@tux06:~/shell/lixo$ od -h <<< $IFS
0000000 0920 0a0a
0000004
diurno@tux06:~/shell/lixo$
```
```
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo `$var`
bash: x: comando não encontrado

diurno@tux06:~/shell/lixo$ var="x    x"
diurno@tux06:~/shell/lixo$ echo `$var`
bash: x: comando não encontrado

diurno@tux06:~/shell/lixo$ echo '$var'
$var
diurno@tux06:~/shell/lixo$ echo "$var"
x    x
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo 'PATH=$PATH:.' >> ~/.bashrc
diurno@tux06:~/shell/lixo$ . ~/.bashrc
(reverse-i-search)`': ^C
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ source ~/.bashrc
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ alias rm=rm\ -i
diurno@tux06:~/shell/lixo$ rm arq12
rm: remover arquivo comum vazio 'arq12'? n
diurno@tux06:~/shell/lixo$ \rm arq12
diurno@tux06:~/shell/lixo$ r\m arq11
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$
```


#### aspas duplas (")
```
diurno@tux06:~/shell/lixo$ var=$(ls -l)
diurno@tux06:~/shell/lixo$ echo var
var
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo $var
total 0 -rw-r--r-- 1 diurno diurno 0 dez 2 11:15 arq -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq1 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq10 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq2 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq3 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq4 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq5 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq6 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq7 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq8 -rw-r--r-- 1 diurno diurno 0 dez 2 11:13 arq9
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ ls -l
total 0
-rw-r--r-- 1 diurno diurno 0 dez  2 11:15 arq
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq1
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq10
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq2
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq3
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq4
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq5
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq6
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq7
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq8
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq9
diurno@tux06:~/shell/lixo$ alias ls
alias ls='ls --color=auto'
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo "$var"
total 0
-rw-r--r-- 1 diurno diurno 0 dez  2 11:15 arq
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq1
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq10
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq2
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq3
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq4
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq5
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq6
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq7
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq8
-rw-r--r-- 1 diurno diurno 0 dez  2 11:13 arq9
diurno@tux06:~/shell/lixo$ 
```

#### contra barra (\)
```
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo escrevi uma linha \
> muito grade
escrevi uma linha muito grade
diurno@tux06:~/shell/lixo$
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo "escrevi uma linha
> muito grade"
escrevi uma linha
muito grade
diurno@tux06:~/shell/lixo$ 

```

#### crase (\`)
Shell executa linearmente, ou seja, de cima para baixo e direita para esquerta
```
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ uname -n
tux06
diurno@tux06:~/shell/lixo$ echo o nome da maquina e uname -n
o nome da maquina e uname -n
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo o nome da maquina e `uname -n`
o nome da maquina e tux06
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo o nome da maquina e $(uname -n)
o nome da maquina e tux06
diurno@tux06:~/shell/lixo$ 
```




## Acoes do shell
0-Atributo ou cmd? \
1-Redirecionador \
2-Substituicao de chaves \
3-Substituicao de variaveis \
4-Resolucao de Curingas \


### Redirecionadores
#### `>` ou `1>`
> `>` muito mais rápido que `touch`

```
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

```

Outro exemplo de melhoria de performance com alguns comandos
```
diurno@tux06:~/shell/lixo$ time for ((i=1 ;i<200;i++))
> {
> expr 2 + 2 >/dev/null
> }

real	0m0,217s
user	0m0,167s
sys	0m0,065s
diurno@tux06:~/shell/lixo$ time for ((i=1 ;i<200;i++))
> {
> echo $((2+2)) >/dev/null
> }

real	0m0,006s
user	0m0,004s
sys	0m0,002s
diurno@tux06:~/shell/lixo$ 

```



> 'cat' short for contatenate
cat vai redirecionar primeiro e apagar o arquivo
```
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
```

#### `<` ou `1<`
Antes de usar `|` tente usar `<`, pois o `|` cria subshells
```
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ wc -l add
7 add
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cat add | wc -l
7
diurno@tux06:~/shell$ wc -l < add
7
diurno@tux06:~/shell$ 
```
```
diurno@tux06:~/shell$ mail meu@amor.com 0< mala
```

#### `>>` ou `1>>`
Acrescenta ao inves de substituir


#### `<<`
```
diurno@tux06:~/shell/lixo$ var=5
diurno@tux06:~/shell/lixo$ python << fim
> print $var
> fim
5
diurno@tux06:~/shell/lixo$ var=julio
diurno@tux06:~/shell/lixo$ python << fim
print $var
fim
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'julio' is not defined
diurno@tux06:~/shell/lixo$ python << fim
print "$var"
fim
julio
diurno@tux06:~/shell/lixo$ 
```

#### Pipe `|`
Saida primaria de um comando para saida do outro criando uma subshell
> E o unico que nao e direcionador de arquivo.

> Nunca use _comando_ | _funcao_ utilize _funcao_ <<< (recebe) _comando_

```
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ echo abacaxi | tr a x
xbxcxxi
diurno@tux06:~/shell/lixo$ tr a x <<< abacaxi
xbxcxxi
diurno@tux06:~/shell/lixo$ 
```
> Cuidao com as variaveis na criacao do subshell (o pipe cria uma subshell), pois as variaveis do shell serao enviadas ao subshell, porem as variaveis do subshell nao serao enviadas ao shell.
```
diurno@tux06:~/shell/lixo$ a=3; (echo 1$a;a=5;echo 2$a); echo 3$a
13
25
33
diurno@tux06:~/shell/lixo$
diurno@tux06:~/shell/lixo$ a=3; (echo 1$a;a=5;b=x;echo 2$a); echo 3$a; echo $b
13
25
33

diurno@tux06:~/shell/lixo$ 
```


### Substituicao de chaves
```
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

```
Crianto tres pastas 1, 2 e 3 --> `diurno@tux06:~/shell$ mkdir /home/{1,2,3}`



### Substituicao de variaveis

Neste exemplo abaixo o shell substituiu as chaves antes de substituir a variavel. Para consertar a operacao usa-se `eval`.
```
diurno@tux06:~/shell$ var=19
diurno@tux06:~/shell$ echo {$var..3}
{19..3}
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ eval echo {$var..3}
19 18 17 16 15 14 13 12 11 10 9 8 7 6 5 4 3
diurno@tux06:~/shell$
```

### Resolucao de Curingas
> Nunca deixe caracteres coringas para o shell (*,?,)
```
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
```
O exemplo abaixo mostrara somente o aquivo 1. Pois nao existe de 3 a 1, restando somente o 1.
```
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ ls arq[3-11]
arq1
diurno@tux06:~/shell/lixo$ 
```
Outro exemplo.
```
diurno@tux06:~/shell/lixo$ ls arq[!357]?
arq10  arq11  arq12
diurno@tux06:~/shell/lixo$ 
```



## Expressao Regurar

### Classe POSIX
```
diurno@tux06:~/shell/lixo$ grep -o '[[:lower:]]' <<< ação
a
ç
ã
o
diurno@tux06:~/shell/lixo$ grep -o '[a-z]' <<< ação
a
ç
ã   
o
diurno@tux06:~/shell/lixo$ echo $LANG
pt_BR.UTF-8
diurno@tux06:~/shell/lixo$ LANG=C grep -o '[a-z]' <<< ação
a
o
diurno@tux06:~/shell/lixo$ 

```
### Escape
`\s` casa espacos em branco \


`\S` é negacao do `\s`. Casa o que nao for espaco em branco \
`\w` casa letras, dígitos , ou \'\_\' \
`\W` negacao do \w \
`\d` casa numeros \
`\D` negacao `\d` 

### Borda
`\b` casa com \[A-Za-z0-9_] \
`\B` nao casa com \[A-Za-z0-9_] \
`\< >\` casa com \[A-Za-z0-9_]

`\bave\b` ave, acestruz, ave-do-paraiso, ~~trave~~ \
`\<ave>\` ave, acestruz, ave-do-paraiso, ~~trave~~


### Outros Metacaracteres
**Escape (`\`)** \
--> CEP `[0-9]{2}\.[0-9]{3}-[0-9]{2}` ou `[0-9]{2}[.][0-9]{3}-[0-9]{2}` \
**Ou (`|`)** \
--> boa-(tarde|noite) --> casa com boa-tarde, boa-noite \
**Grupo** \
--> (meta)?caractere --> casa com caractere, metacaractere \
--> (mini|(su|hi)per)?mercado --> casa com mercado, supermercado, hipermercado, minimercado \
**Retrovisor ou _Back-reference_** \
--> (lenta)(mente) é \2 \1  lentamente é mente lenta \
--> ((band)eira)nte \1 \2a  bandeirante bandeira banda \
--> in(d)ol(or) é sem \1\2  indolor é sem dor \
--> ((((a)b)c)d)-1 = \1,\2,\3,\4    abcd-1 = abcd,abc,ab,a \
conte somente os parênteses que abrem, da esquerda para a direita. \
```
diurno@tux06:~/shell/lixo$ cat ../quero
batebate
bate-bate
bate-bateria
bole--bole
comecome
come come
come  come
come-come
hoje-joia
queroquero
quero quero
quero-quero
rebate-bate
rebate-bateria
diurno@tux06:~/shell/lixo$ grep -E '([a-z]+)-\1' ../quero
bate-bate
bate-bateria
come-come
quero-quero
rebate-bate
rebate-bateria
diurno@tux06:~/shell/lixo$ grep -E '^([a-z]+)-\1$' ../quero
bate-bate
come-come
quero-quero
diurno@tux06:~/shell/lixo$ grep -E '\b([a-z]+)-\1\b' ../quero
bate-bate
come-come
quero-quero
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ grep -E '\b([a-z]+)( |-)\1\b' ../quero
bate-bate
come come
come-come
quero quero
quero-quero
diurno@tux06:~/shell/lixo$ grep -E '\b([a-z]+)[ -]\1\b' ../quero
bate-bate
come come
come-come
quero quero
quero-quero
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ grep -E '\b([a-z]+)[ -]?\1\b' ../quero
batebate
bate-bate
comecome
come come
come-come
queroquero
quero quero
quero-quero
diurno@tux06:~/shell/lixo$ 
```
### Dates
```
diurno@tux06:~/shell/lixo$ Hoje=$(date '+%d/%m/%Y')
diurno@tux06:~/shell/lixo$ echo $(Hoje)
bash: Hoje: comando não encontrado

diurno@tux06:~/shell/lixo$ echo $Hoje
02/12/2019
diurno@tux06:~/shell/lixo$ echo $hoje

diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ sed -r 's|([0-9]{2})/([0-9]{2})/([0-9]{4})|\3-\2-\1|' <<< $Hoje
2019-12-02
diurno@tux06:~/shell/lixo$ 
```
> sed -r --> expandir o sed


### Regex Cross­word
[https://regexcrossword.com/](https://regexcrossword.com/)



# Aula 2 - 03/Dez/2019

## **`grep`**
grep  searches  for PATTERNS in each FILE.  PATTERNS is one or patterns
       separated by newline characters, and grep prints each line that matches
       a pattern.
       
       
grep --> global regular expression print \
grep -E --> grep para expressoes regulares expandidas (ex. ?, {}, etc) \
grep -v palavra --> exclui palavra \
grep -v ^$ --> exclui linha em branco, que comeca e termina \
grep -o --> --only-match \
grep -f -->  \

> Todo comando do shell se estrutura **instrucao + opcao + comando + arquivos**

### `grep -i` 
grep -i --> ignore case sensitive
```
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cat telefones
Ciro Grippi	(021)555-1234
Claudia Marcia	(021)555-2112
Enio Cardoso	(023)232-3423
Juliana Duarte	(024)622-2876
Luiz Carlos	(021)767-2124
Ney Garrafas	(021)988-3398
Ney Gerhardt	(024)543-4321
Paula Duarte	(011)449-0219
diurno@tux06:~/shell$ grep ney telefones
diurno@tux06:~/shell$ grep -i ney telefones
Ney Garrafas	(021)988-3398
Ney Gerhardt	(024)543-4321
```

### `grep -c` **CUIDADO**
Conta linha e nao arquivos 
```
diurno@tux06:~/shell$ grep -C ' de ' quequeisso
grep:  de : argumento inválido para comprimento do contexto
diurno@tux06:~/shell$ grep -c ' de ' quequeisso
7
diurno@tux06:~/shell$ grep -o ' de ' quequeisso
 de 
 de 
 de 
 de 
 de 
 de 
 de 
 de 
diurno@tux06:~/shell$ grep -o ' de ' quequeisso | wc -l
8
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ grep -c a <<< abacate
1
diurno@tux06:~/shell$ grep -o a <<< abacate | wc -l
3
diurno@tux06:~/shell$ 
```

### `grep -A`
Busca e inclui linhas apos a busca
```
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ grep -A2 Luiz telefones
Luiz Carlos	(021)767-2124
Ney Garrafas	(021)988-3398
Ney Gerhardt	(024)543-4321
diurno@tux06:~/shell$ 
```

### `grep -q`
??????


### `grep -l`
-l, --files-with-matches
              Suppress normal output; instead print the  name  of  each  input
              file  from  which  output would normally have been printed.  The
              scanning will stop on the first match.

```
diurno@tux06:~/shell$ grep date *
ArteAscii1.sh:Ano=$[$(date +%j)>365/2?$(date +%Y)+1:$(date +%Y)]
c3e3:Data=`date "+%b %e"`
c4e1:hh=`date "+%H"`      #  Horas em hh
c4e1:mm=`date "+%M"`      #  Minutos em mm
c4e3:Hora=`date +%H`
confusao:cd $HOME;pwd;date;ls -la;echo $LOGNAME x${SHELL}x
hora:Hora=`date | cut -f4 -d" " | cut -f1 -d:`
hora:Resto=`date | cut -f4 -d" " | cut -f2- -d:`
grep: lixo: É um diretório
NatalComNeve.sh:Ano=$(($(date +%m) < 10 ? $(date +%Y) : $(date +%Y) + 1))
natal.sh:echo "E UM PROSPERO $((($(date +%Y)+1)))"
grep: nautilus-scripts: É um diretório
reldig.sh:    HrAtu=$(date +%H%M%S)
rotinas.sh:    DFim=`date +%d`
rotinas.sh:    MFim=`date +%m`
rotinas.sh:    AFim=`date +%Y`
velha.sh:	Seg=`date "+%S"`
diurno@tux06:~/shell$ grep -l date *
ArteAscii1.sh
c3e3
c4e1
c4e3
confusao
hora
grep: lixo: É um diretório
NatalComNeve.sh
natal.sh
grep: nautilus-scripts: É um diretório
reldig.sh
rotinas.sh
velha.sh
diurno@tux06:~/shell$ 

```

### `grep -vf`

-v, --invert-match
              Invert the sense of matching, to select non-matching lines.

-f FILE, --file=FILE
              Obtain patterns from FILE, one per line.  If this option is used
              multiple times or is combined with  the  -e  (--regexp)  option,
              search  for  all  patterns  given.  The empty file contains zero
              patterns, and therefore matches nothing.

```
diurno@tux06:~/shell$ ip a | grep -oE '([0-9]{1,3}\.){3}[0-9]{1,3}'
127.0.0.1
192.168.203.6
192.168.203.255
diurno@tux06:~/shell$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp3s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:1a:64:1f:5e:e6 brd ff:ff:ff:ff:ff:ff
    inet 192.168.203.6/24 brd 192.168.203.255 scope global dynamic enp3s0
       valid_lft 4121sec preferred_lft 4121sec
    inet6 fe80::21a:64ff:fe1f:5ee6/64 scope link 
       valid_lft forever preferred_lft forever
diurno@tux06:~/shell$ ip a | grep -oE '([0-9]{1,3}\.){3}[0-9]{1,3}' > arqip
diurno@tux06:~/shell$ sed 's/^/\b/; s/$/\b/' arqip
b127.0.0.1b
b192.168.203.6b
b192.168.203.255b
diurno@tux06:~/shell$ sed 's/^/\\b/; s/$/\\b/' arqip
\b127.0.0.1\b
\b192.168.203.6\b
\b192.168.203.255\b
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ sed 's/^/\\b/; s/$/\\b/' arqip > arqip1
arqip1
diurno@tux06:~/shell$ cat arqip1
\b127.0.0.1\b
\b192.168.203.6\b
\b192.168.203.255\b
diurno@tux06:~/shell$ 
```


---

## **`sed`**
Sed  is a stream editor.  A stream editor is used to perform basic text
       transformations on an input stream (a file or input from  a  pipeline).
       While  in  some  ways similar to an editor which permits scripted edits
       (such as ed), sed works by making only one pass over the input(s),  and
       is consequently more efficient.  But it is sed's ability to filter text
       in a pipeline which particularly distinguishes it from other  types  of
       editors.
       
### `sed '/ / , / /d '`
```
diurno@tux06:~/shell$ seq 20
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
diurno@tux06:~/shell$ seq 2 20
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
diurno@tux06:~/shell$ seq 2 2 20
2
4
6
8
10
12
14
16
18
20
diurno@tux06:~/shell$ man sed
diurno@tux06:~/shell$ seq 2 2 20 | sed '2,4p'
2
4
4
6
6
8
8
10
12
14
16
18
20
diurno@tux06:~/shell$ seq 2 2 20 | sed -n '2,4p'
4
6
8
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ seq 2 2 20 | sed -n '2,4p'
4
6
8
```
Evite usar o -n com o p
```
diurno@tux06:~/shell$ seq 2 2 20 | sed -n '2,4p;s/4/x/p'
4
x
6
8
1x
diurno@tux06:~/shell$

```
Use o !d ao inves
```
diurno@tux06:~/shell$ seq 2 2 20 | sed '2,4!d;s/4/x/'
x
6
8
diurno@tux06:~/shell$
```
```
diurno@tux06:~/shell$ seq 2 2 20 | sed '/^2$/,/4/d'
6
8
10
12
14
16
18
20
diurno@tux06:~/shell$ seq 2 2 20 | sed '/2$/,/4/d'
6
8
10
16
18
20
diurno@tux06:~/shell$
```

#### Deletando `sed '/de/,/ate/d' file`
```
diurno@tux06:~/shell$ cat -n quequeisso
     1	ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
     2	EH UMA LAVAGEM CEREBRAL!!!
     3	O Shell alem de analisar cada dado entrado a partir do prompt do UNIX,
     4	interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
     5	Interpretador de comandos;
     6	Controle do ambiente UNIX;
     7	Redirecionamento de entrada e saida;
     8	Substituicao de nomes de arquivos;
     9	Concatenacao de pipe;
    10	Execucao de programas;
    11	Poderosa linguagem de programacao.
diurno@tux06:~/shell$ sed '/ de /,/UNIX/d'
^C
diurno@tux06:~/shell$ sed '/UNIX/,/ de /d' quequeisso 
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ sed '/ de /,/I/d' quequeisso 
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
Controle do ambiente UNIX;
diurno@tux06:~/shell$ 
```

### `sed 'a'` ou `sed '/ /a'` append
Inseri apos a linha
```
diurno@tux06:~/shell$ seq 2 2 20 | sed '2aNovo'
2
4
Novo
6
8
10
12
14
16
18
20
diurno@tux06:~/shell$
```
### `sed '/ /c'` ou `sed '/ /c'` change a linha existente
```
diurno@tux06:~/shell$ seq 2 2 20 | sed '2cNovo'
2
Novo
6
8
10
12
14
16
18
20
diurno@tux06:~/shell$
```
### `sed '/ /i'` ou `sed '/ /i'` insere uma linha nova
Inseri na linha
```
diurno@tux06:~/shell$ seq 2 2 20 | sed '2iNovo'
2
Novo
4
6
8
10
12
14
16
18
20
diurno@tux06:~/shell$
```
### `sed 's/ / /I'` ou `sed 's/ / /i'` --> substituir com `I` ignora o case sensitive.
```
diurno@tux06:~/shell$ sed 's/unix/LINUX/' quequeisso
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
O Shell alem de analisar cada dado entrado a partir do prompt do UNIX,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
Interpretador de comandos;
Controle do ambiente UNIX;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ sed 's/unix/LINUX/i' quequeisso
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
O Shell alem de analisar cada dado entrado a partir do prompt do LINUX,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
Interpretador de comandos;
Controle do ambiente LINUX;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$
```

### `sed 's/ / /g'` --> substituir todas.
```
diurno@tux06:~/shell$ sed 's/a/X/' <<< abracadabra
Xbracadabra
diurno@tux06:~/shell$ sed 's/a/X/5' <<< abracadabra
abracadabrX
diurno@tux06:~/shell$ sed 's/a/X/g' <<< abracadabra
XbrXcXdXbrX
diurno@tux06:~/shell$ sed 's/a/X/2g' <<< abracadabra
abrXcXdXbrX
diurno@tux06:~/shell$ 
```

### `sed 's/ .*//'` --> substituir todas que comecam com branco por nada.
```
diurno@tux06:~/shell$ sed 's/ .*//' quequeisso
ATENCAO,
EH
O
interfaceando
Interpretador
Controle
Redirecionamento
Substituicao
Concatenacao
Execucao
Poderosa
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cat quequeisso
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
O Shell alem de analisar cada dado entrado a partir do prompt do UNIX,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
Interpretador de comandos;
Controle do ambiente UNIX;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ 
```

### `sed 's/ .*//'` --> manipular case.
```
diurno@tux06:~/shell$ sed -r 's/\b([[:alpha:]]+)\b/\L\u\1/g' <<< BOTELHO\ PINTO
Botelho Pinto
diurno@tux06:~/shell$ 
```


### `sed 's/x //'`, `'s/d //'`, `'s/o .*//'`, `'s/c //'` --> base numericas
> consulte a tabela ASCII com `man ascii`
``` 
diurno@tux06:~/shell$ cat -et DOS.txt
Este arquivo^M$
foi gerado pelo^M$
DOS/rwin e foi^M$
baixado por um^M$
ftp mal feito.^M$
diurno@tux06:~/shell$ sed 's/\x0d//' DOS.txt | cat -et
Este arquivo$
foi gerado pelo$
DOS/rwin e foi$
baixado por um$
ftp mal feito.$
diurno@tux06:~/shell$ sed 's/\d13//' DOS.txt | cat -et
Este arquivo$
foi gerado pelo$
DOS/rwin e foi$
baixado por um$
ftp mal feito.$
diurno@tux06:~/shell$ sed 's/\o15//' DOS.txt | cat -et
Este arquivo$
foi gerado pelo$
DOS/rwin e foi$
baixado por um$
ftp mal feito.$
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ sed 's/\cM//' DOS.txt | cat -et
Este arquivo$
foi gerado pelo$
DOS/rwin e foi$
baixado por um$
ftp mal feito.$
diurno@tux06:~/shell$ 
```

### `sed '//=' arquivo` --> buscando valores no arquivo
``` 
diurno@tux06:~/shell$ sed = quequeisso
1
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
2
EH UMA LAVAGEM CEREBRAL!!!
3
O Shell alem de analisar cada dado entrado a partir do prompt do UNIX,
4
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
5
Interpretador de comandos;
6
Controle do ambiente UNIX;
7
Redirecionamento de entrada e saida;
8
Substituicao de nomes de arquivos;
9
Concatenacao de pipe;
10
Execucao de programas;
11
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ sed '/UNIX/=' quequeisso
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
3
O Shell alem de analisar cada dado entrado a partir do prompt do UNIX,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
Interpretador de comandos;
6
Controle do ambiente UNIX;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ sed -n '/UNIX/=' quequeisso
3
6
diurno@tux06:~/shell$ sed -n '$=' quequeisso
11
diurno@tux06:~/shell$
diurno@tux06:~/shell$ sed '/5,$/=' quequeisso
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
O Shell alem de analisar cada dado entrado a partir do prompt do UNIX,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
Interpretador de comandos;
Controle do ambiente UNIX;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ 

```

### `sed 'N;s//' arquivo` --> 
```
diurno@tux06:~/shell$ seq 8 | sed 'N;p'
1
2
1
2
3
4
3
4
5
6
5
6
7
8
7
8
diurno@tux06:~/shell$ seq 8 | sed 'N;s/\n/\t/'
1	2
3	4
5	6
7	8
diurno@tux06:~/shell$ sed = frutas | sed 'N;s/\n/\t/'
1	abacate
2	maçã
3	morango
4	pera
5	tangerina
6	uva
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ paste <(seq 6) frutas
1	abacate
2	maçã
3	morango
4	pera
5	tangerina
6	uva
diurno@tux06:~/shell$ 
```

### `sed - i` --> 
-i[SUFIXO], --in-place[=SUFIXO]
                 edita o arquivo original (faz backup se usado SUFIXO)

> O comando `$ sed -i.veio 's/[[:upper:]]/[[:lower:]]/g' quequeisso` #esta incorreto, pois a sintaxe do `sed` e O s/REGEX/STR/
```
diurno@tux06:~/shell$ sed -i.veio 's/[[:upper:]]/[[:lower:]]/g' quequeisso
diurno@tux06:~/shell$ cat quequeisso
[[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]], [[:lower:]] [[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]] [[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]] [[:lower:]][[:lower:]][[:lower:]] [[:lower:]][[:lower:]] [[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]],
[[:lower:]][[:lower:]] [[:lower:]][[:lower:]][[:lower:]] [[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]] [[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]][[:lower:]]!!!
[[:lower:]] [[:lower:]]hell alem de analisar cada dado entrado a partir do prompt do [[:lower:]][[:lower:]][[:lower:]][[:lower:]],
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
[[:lower:]]nterpretador de comandos;
[[:lower:]]ontrole do ambiente [[:lower:]][[:lower:]][[:lower:]][[:lower:]];
[[:lower:]]edirecionamento de entrada e saida;
[[:lower:]]ubstituicao de nomes de arquivos;
[[:lower:]]oncatenacao de pipe;
[[:lower:]]xecucao de programas;
[[:lower:]]oderosa linguagem de programacao.
diurno@tux06:~/shell$ cat quequeisso.veio
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
O Shell alem de analisar cada dado entrado a partir do prompt do UNIX,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
Interpretador de comandos;
Controle do ambiente UNIX;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ mv quequeisso.veio quequeisso
```

### `sed 's/ /\L&/' arquivo` --> retrovisor com &
Uso muito restrito
```
diurno@tux06:~/shell$ sed 's/.*/\L&/' quequeisso
atencao, o texto abaixo nao eh treinamento,
eh uma lavagem cerebral!!!
o shell alem de analisar cada dado entrado a partir do prompt do unix,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
interpretador de comandos;
controle do ambiente unix;
redirecionamento de entrada e saida;
substituicao de nomes de arquivos;
concatenacao de pipe;
execucao de programas;
poderosa linguagem de programacao.
diurno@tux06:~/shell$ sed 's/UNIX/\L&/' quequeisso
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
O Shell alem de analisar cada dado entrado a partir do prompt do unix,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
Interpretador de comandos;
Controle do ambiente unix;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
Execucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$
diurno@tux06:~/shell$ sed -r 's/[0-9]{2}/&12/' <<< 15/05/1024
1512/05/1024
diurno@tux06:~/shell$ sed -r 's/[0-9]{2}/&12/g' <<< 15/05/1024
1512/0512/10122412
diurno@tux06:~/shell$ sed 's/[0-9]{2}/&12/g' <<< 15/05/1024
15/05/1024
diurno@tux06:~/shell$ sed 's/[0-9]\{2\}/&12/g' <<< 15/05/1024
1512/0512/10122412
diurno@tux06:~/shell$ 
```

### `sed 'y/ / /' arquivo`
Como o `s/ / /` porem literalmente, sintaxe y/STR/STR/
```
diurno@tux06:~/shell$ sed 'y/aeiou/xyzwk/' quequeisso
ATENCAO, O TEXTO ABAIXO NAO EH TREINAMENTO,
EH UMA LAVAGEM CEREBRAL!!!
O Shyll xlym dy xnxlzsxr cxdx dxdw yntrxdw x pxrtzr dw prwmpt dw UNIX,
zntyrfxcyxndw cwm ws kskxrzws, tym txmbym xs sygkzntys xtrzbkzcwys:
Intyrprytxdwr dy cwmxndws;
Cwntrwly dw xmbzynty UNIX;
Rydzryczwnxmyntw dy yntrxdx y sxzdx;
Skbstztkzcxw dy nwmys dy xrqkzvws;
Cwncxtynxcxw dy pzpy;
Exyckcxw dy prwgrxmxs;
Pwdyrwsx lzngkxgym dy prwgrxmxcxw.
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ sed 'y/OIZEASGTB/012345678/' quequeisso
473NC40, 0 73X70 4841X0 N40 3H 7R31N4M3N70,
3H UM4 L4V463M C3R38R4L!!!
0 5hell alem de analisar cada dado entrado a partir do prompt do UN1X,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
1nterpretador de comandos;
Controle do ambiente UN1X;
Redirecionamento de entrada e saida;
5ubstituicao de nomes de arquivos;
Concatenacao de pipe;
3xecucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ sed 'y/\cm/ / DOS.txt | car -et
> ^C
diurno@tux06:~/shell$ sed 'y/\cm/ /' DOS.txt | car -et
bash: car: comando não encontrado
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ sed 'y/\cm/ /' DOS.txt | cat -et
Este arquivo $
foi gerado pelo $
DOS/rwin e foi $
baixado por um $
ftp mal feito. $
diurno@tux06:~/shell$ sed 'y/\cM/ /' DOS.txt | cat -et
Este arquivo $
foi gerado pelo $
DOS/rwin e foi $
baixado por um $
ftp mal feito. $
diurno@tux06:~/shell$ 
```



## `cut`
```
diurno@tux06:~/shell$ who -l
LOGIN    tty1         2019-12-02 09:29               564 id=tty1
diurno@tux06:~/shell$ who -l | cut -c -8
LOGIN   
diurno@tux06:~/shell$ who -l | cut -c1-8
LOGIN   
diurno@tux06:~/shell$ who -l | cut -c -8, 40-60
cut: posições de byte/caractere são numeradas a partir do número 1
Tente "cut --help" para mais informações.
diurno@tux06:~/shell$ who -l | cut -c -8,40-60
LOGIN                 564 id=
diurno@tux06:~/shell$ who -l | cut -c -8,20-40
LOGIN      2019-12-02 09:29  
diurno@tux06:~/shell$ who -l | cut -c -8,20-40,60-
LOGIN      2019-12-02 09:29  =tty1
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ who -l | cut -f1 -d' '
LOGIN
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cut -f1 telefones
Ciro Grippi
Claudia Marcia
Enio Cardoso
Juliana Duarte
Luiz Carlos
Ney Garrafas
Ney Gerhardt
Paula Duarte
diurno@tux06:~/shell$ cat -et telefones
Ciro Grippi^I(021)555-1234$
Claudia Marcia^I(021)555-2112$
Enio Cardoso^I(023)232-3423$
Juliana Duarte^I(024)622-2876$
Luiz Carlos^I(021)767-2124$
Ney Garrafas^I(021)988-3398$
Ney Gerhardt^I(024)543-4321$
Paula Duarte^I(011)449-0219$
diurno@tux06:~/shell$ cat quequeisso ^C
diurno@tux06:~/shell$ 

```



## `cut | sort | uniq`
```
diurno@tux06:~/shell$ ls | cut -f2- -d.
yad
add
alfa
aluado
sh
sh
aniv
sh
Arq
arq200
DOS
arqip
arqip1
ArqOLs
sh
sh
ave
bb
bdb
txt
bronze
c3e1
c3e2
c3e3
c4e1
c4e2
c4e3
c5e1
c6e1
c6e2
c7e1
c7e2
1
c8e1
c8e2
camba
pdf
carros
sh
sh
sh
confusao
awk
sh
sh
sh
sh
sh
sh
sh
creditos
sed
sh
d
debitos
sed
sh
div
txt
func
DuLoren
empregado
erreeme
exclui
awk
for.awk
frutas
funcionario
funcionarios
func
sh
grepr
yad
yad
hora
awk
sed
kadeo
sh
lematric
awk
listdir
listdir1
lixo
lt
sh
medieval
misto
sh
sh
sh
sh
sh
sh
nautilus-scripts
sh
txt
yad
nums
sh
sh
pdf
sh
param1
param2
param3
param4
param5
param6
param7
tmp
pedi
pp
awk
txt
quequeisso
quero
pdf
sh
rem
restaura
sh
awk
sh
talogado
tavazio
sh
telef
telefones
teles
sh
testa_sed
testchar
teste
testsex
sh
toca
tputcup
tr
sh
tst_exec
tstmatr
sh
usus
variando
variando1
VelEcon
sh
vira
diurno@tux06:~/shell$ ls | cut -f2- -sd.
yad
sh
sh
sh
DOS
sh
sh
txt
1
pdf
sh
sh
sh
awk
sh
sh
sh
sh
sh
sh
sh
sed
sh
sed
sh
txt
func
awk
for.awk
func
sh
yad
yad
awk
sed
sh
awk
sh
sh
sh
sh
sh
sh
sh
sh
txt
yad
sh
sh
pdf
sh
tmp
awk
txt
pdf
sh
sh
awk
sh
sh
sh
sh
sh
sh
sh
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ ls | cut -f2- -sd. | sort
1
awk
awk
awk
awk
awk
awk
DOS
for.awk
func
func
pdf
pdf
pdf
sed
sed
sed
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
sh
tmp
txt
txt
txt
txt
yad
yad
yad
yad
diurno@tux06:~/shell$ ls | cut -f2- -sd. | sort | UNIQ
bash: UNIQ: comando não encontrado
diurno@tux06:~/shell$ ls | cut -f2- -sd. | sort | uniq
1
awk
DOS
for.awk
func
pdf
sed
sh
tmp
txt
yad
diurno@tux06:~/shell$ ls | cut -f2- -sd. | sort | uniq -C
uniq: opção inválida -- “C”
Tente "uniq --help" para mais informações.
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ ls | cut -f2- -sd. | sort | uniq -c
      1 1
      6 awk
      1 DOS
      1 for.awk
      2 func
      3 pdf
      3 sed
     39 sh
      1 tmp
      4 txt
      4 yad
diurno@tux06:~/shell$ 

```


```
diurno@tux06:~/shell$ cut -f2 -d\( telefones
021)555-1234
021)555-2112
023)232-3423
024)622-2876
021)767-2124
021)988-3398
024)543-4321
011)449-0219
diurno@tux06:~/shell$ cut -f2 -d\( | cut -f1 -d\) telefones
Ciro Grippi	(021
Claudia Marcia	(021
Enio Cardoso	(023
Juliana Duarte	(024
Luiz Carlos	(021
Ney Garrafas	(021
Ney Gerhardt	(024
Paula Duarte	(011
^[[A^C
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cut -f2 -d\( telefones | cut -f1 -d\)
021
021
023
024
021
021
024
011
diurno@tux06:~/shell$ cut -f2 -d\( telefones | cut -f2 -d\-
1234
2112
3423
2876
2124
3398
4321
0219
diurno@tux06:~/shell$ cut -f2 -d\( telefones | cut -f1 -d\-
021)555
021)555
023)232
024)622
021)767
021)988
024)543
011)449
diurno@tux06:~/shell$ cut -f2 -d\( telefones | cut -f1 -d\-
021)555
021)555
023)232
024)622
021)767
021)988
024)543
011)449
diurno@tux06:~/shell$ cut -f2 -d\) telefones | cut -f1 -d\-
555
555
232
622
767
988
543
449
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cut -f2 -d' ' telefones | cut -f1
Grippi
Marcia
Cardoso
Duarte
Carlos
Garrafas
Gerhardt
Duarte
diurno@tux06:~/shell$ 
```

> Crtl+V + Tab
> ```
> diurno@tux06:~/shell$ echo "    " | cat -et
> ^I$
> diurno@tux06:~/shell$ 
> ```

### Outros `cut`
```
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ seq -s: 10
1:2:3:4:5:6:7:8:9:10
diurno@tux06:~/shell$ seq -s: 10 | cut -f4-7 -d:
4:5:6:7
diurno@tux06:~/shell$ seq -s: 10 | cut -f4-7 -d: --complement
1:2:3:8:9:10
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ seq -s: 10 | cut -f4-7 -d: --complement --output-delimiter $'\n'
1
2
3
8
9
10
diurno@tux06:~/shell$ seq -s: 10 | cut -f4-7 -d: --complement --output-delimiter $' sep '
1 sep 2 sep 3 sep 8 sep 9 sep 10
diurno@tux06:~/shell$ 

```

## `past`
###
```
diurno@tux06:~/shell$ seq 1 2 9 > impar
diurno@tux06:~/shell$ seq 2 2 10 > par
diurno@tux06:~/shell$ paste impar par
1	2
3	4
5	6
7	8
9	10
diurno@tux06:~/shell$ paste impar par > nums
```
### `paste -d`
```
diurno@tux06:~/shell$ paste impar par -d+
1+2
3+4
5+6
7+8
9+10
diurno@tux06:~/shell$ paste impar par -d+ | bc
bash: bc: comando não encontrado
diurno@tux06:~/shell$ 

``` 
### `paste -s`
-s, --serial            cola um arquivo por vez em de todos em paralelo

```
diurno@tux06:~/shell$ paste par
2
4
6
8
10
diurno@tux06:~/shell$ paste -s par
2	4	6	8	10
diurno@tux06:~/shell$
```

### `paste -d`

```
diurno@tux06:~/shell$ seq 6
1
2
3
4
5
6
diurno@tux06:~/shell$ seq 6 | paste -sd*
1*2*3*4*5*6
diurno@tux06:~/shell$ echo $(($(seq 6 | paste -sd*)))
720
diurno@tux06:~/shell$ 
```
Nao se deixa metacaracter `*` para o shell, pois acontece isso
```
diurno@tux06:~/shell$ seq -s* 6
1*2*3*4*5*6
diurno@tux06:~/shell$ > -sifu
diurno@tux06:~/shell$ seq -s* 6
1ifu2ifu3ifu4ifu5ifu6
diurno@tux06:~/shell$ seq -s* 6
1ifu2ifu3ifu4ifu5ifu6
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ rm -sifu
rm: opção inválida -- “s”
Tente "rm ./-sifu" para remover o arquivo '-sifu'.
Tente "rm --help" para mais informações.
```
Neste caso o `--` significa fim das opcoes
```
diurno@tux06:~/shell$ rm -i -- -sifu
rm: remover arquivo comum vazio '-sifu'? sim
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ seq -s* 6
1*2*3*4*5*6
diurno@tux06:~/shell$
```


## `cat`
Neste caso o `-` e um placeholder para a entrada primaria
```
diurno@tux06:~/shell$ echo -e 'impar\tpar\n=====\t===' | cat - nums
impar	par
=====	===
1	2
3	4
5	6
7	8
9	10
diurno@tux06:~/shell$ ^C
diurno@tux06:~/shell$ 
```

## `tr`
tr - translate or delete characters
```
diurno@tux06:~/shell$ tr A-Z a-z < quequeisso
atencao, o texto abaixo nao eh treinamento,
eh uma lavagem cerebral!!!
o shell alem de analisar cada dado entrado a partir do prompt do unix,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
interpretador de comandos;
controle do ambiente unix;
redirecionamento de entrada e saida;
substituicao de nomes de arquivos;
concatenacao de pipe;
execucao de programas;
poderosa linguagem de programacao.
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ tr AEIOU xyz < quequeisso
xTyNCxz, z TyXTz xBxzXz Nxz yH TRyzNxMyNTz,
yH zMx LxVxGyM CyRyBRxL!!!
z Shell alem de analisar cada dado entrado a partir do prompt do zNzX,
interfaceando com os usuarios, tem tambem as seguintes atribuicoes:
znterpretador de comandos;
Controle do ambiente zNzX;
Redirecionamento de entrada e saida;
Substituicao de nomes de arquivos;
Concatenacao de pipe;
yxecucao de programas;
Poderosa linguagem de programacao.
diurno@tux06:~/shell$ 
```
```
diurno@tux06:~/shell$ tr '[:lower:]' '[:upper:]' <<< ação
AçãO
diurno@tux06:~/shell$
```

## `tr -s`
-s, --squeeze-repeats   substitui cada sequência de um caractere repetido
                            que está listado no último CONJUNTO especificado,
                            com uma única ocorrência daquele caractere
```
diurno@tux06:~/shell$ ls -l
total 4424
-rwxr-xr-x 1 diurno diurno    1831 ago  6 23:34 acpi-note.yad
-rwxr-xr-x 1 diurno diurno     114 out  7  1997 add
-rwxr-xr-x 1 diurno diurno      13 jun 17  2013 alfa
-rwxr-xr-x 1 diurno diurno      83 jun 15  2013 aluado
-rwxr-xr-x 1 diurno diurno     737 jan 16  2010 anilhas.sh
-rwxr-xr-x 1 diurno diurno     621 dez 31  2009 animal.sh
-rwxr-xr-x 1 diurno diurno     127 set 25  2017 aniv

diurno@tux06:~/shell$ ls -l | tr -s ' '
total 4424
-rwxr-xr-x 1 diurno diurno 1831 ago 6 23:34 acpi-note.yad
-rwxr-xr-x 1 diurno diurno 114 out 7 1997 add
-rwxr-xr-x 1 diurno diurno 13 jun 17 2013 alfa
-rwxr-xr-x 1 diurno diurno 83 jun 15 2013 aluado

diurno@tux06:~/shell$ ls -l | tr -s ' ' '\t' | cut -f5,9

1831	acpi-note.yad
114	add
13	alfa
83	aluado
737	anilhas.sh


diurno@tux06:~/shell$ ls -l | tr -s ' ' '\t' | cut -f5,9 | sort -rn
1883200	RegExpNew.pdf
1560738	OneLiners.pdf
461755	Canivete_Suíço_do_Shell.pdf
9673	velha.sh
6595	rotinas.sh
4237	ArteAscii2.sh
4168	AnoNovo.sh
4096	nautilus-scripts
4096	lixo

```

### `tr -d`
-d, --delete            apaga os caracteres do CONJUNTO1, não traduz

```
diurno@tux06:~/shell$ tr -d '\r' < DOS.txt | cat -et
Este arquivo$
foi gerado pelo$
DOS/rwin e foi$
baixado por um$
ftp mal feito.$
diurno@tux06:~/shell$
```
Use o comando `$ tr '\n' ' '` para serializar um arquivo em linhas para uma unica linha.



### `((  ))` --> operador matematico
Para prioriza-lo utiliza-se o `$` na frente
```
diurno@tux06:~/shell$ expr 3 * 5
expr: erro de sintaxe: argumento inesperado “acpi-note.yad”
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ expr 3 '*' 5
15
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ expr 3 '*' 5
15
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ echo $((3*5))
15
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ num=8
diurno@tux06:~/shell$ echo $((num*10))
80
diurno@tux06:~/shell$
diurno@tux06:~/shell$ echo $((tudo++))
0
diurno@tux06:~/shell$ echo $((tudo++))
1
diurno@tux06:~/shell$ echo $((tudo++))
2
diurno@tux06:~/shell$ echo $((tudo++))
3
diurno@tux06:~/shell$ echo $((tudo++))
4
diurno@tux06:~/shell$ echo $((tudo++))
5
diurno@tux06:~/shell$ echo $((tudo++))
diurno@tux06:~/shell$ echo $((tudo+=3))
9
diurno@tux06:~/shell$ echo $((tudo+=3))
12
diurno@tux06:~/shell$ echo $((tudo+=3))
15
diurno@tux06:~/shell$ 
```
Trabalhando com bases
```
diurno@tux06:~/shell$ echo $((2**3))
8
diurno@tux06:~/shell$ echo $((2#1011))
11
diurno@tux06:~/shell$
diurno@tux06:~/shell$ echo $((2#1011+8#13+10#11+11#10+16#b))
55
diurno@tux06:~/shell$
diurno@tux06:~/shell$ dia=08
diurno@tux06:~/shell$ echo $((dia+1))
bash: 08: valor muito grande para esta base de numeração (token de erro é "08")
diurno@tux06:~/shell$ echo $((10#dia+1))
bash: 10#dia: valor muito grande para esta base de numeração (token de erro é "10#dia")
diurno@tux06:~/shell$ echo $((10#$dia+1))
9
diurno@tux06:~/shell$ 

```

### Comparando `(( ))` com `expr`
```
diurno@tux06:~/shell$ time for ((i=1;i<200;i++))
> {
> expr 2 + 2 > /dev/null
> }

real	0m0,232s
user	0m0,166s
sys	0m0,080s
diurno@tux06:~/shell$
diurno@tux06:~/shell$ time for ((i=1;i<200;i++)); { echo $((2+2)) > /dev/null; } 
real	0m0,006s
user	0m0,006s
sys	0m0,000s
diurno@tux06:~/shell$ 

```

### `for`
Consultar `$man bash` e buscar por `/ for \(\(`.
```
diurno@tux06:~/shell$ for ((i=10;i>0;i--))
> {
> echo $i
> }
10
9
8
7
6
5
4
3
2
1
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ for ((i=10;i>0;i-=2)); { echo $i; }
10
8
6
4
2
diurno@tux06:~/shell$
```


### Operador ternario
```
diurno@tux06:~/shell$ num=40
diurno@tux06:~/shell$ num=$((num>50?num-40:num+40));echo $num
80
diurno@tux06:~/shell$ num=$((num>50?num-40:num+40));echo $num
40
diurno@tux06:~/shell$ num=$((num>50?num-40:num+40));echo $num
80
diurno@tux06:~/shell$ 
```

## `for` outra sintaxe
```
diurno@tux06:~/shell$ mai=
diurno@tux06:~/shell$ for num in 2 5 4 7
> do
> mai=$((mai>num?mai:num))
> echo -e "mai = $mai\tnum = $num"
> done
mai = 2	num = 2
mai = 5	num = 5
mai = 5	num = 4
mai = 7	num = 7
diurno@tux06:~/shell$
```


# Aula 3 - 04/Dez/2019

## `set`
${ } --> expansao de parametro
```
diurno@tux06:~$ set {a..k}
diurno@tux06:~$ echo $1
a
diurno@tux06:~$ echo $2
b
diurno@tux06:~$ echo $3
c
diurno@tux06:~$ echo $10
a0
diurno@tux06:~$ echo ${10}
j
diurno@tux06:~$ 
diurno@tux06:~$ echo $0
/bin/bash
diurno@tux06:~$ 
```


### `expr`
expr - evaluate expressions
```
diurno@tux06:~$ var=cadeia
diurno@tux06:~$ expr length $var
6
diurno@tux06:~$ echo ${#var}
6
diurno@tux06:~$ wc -c <<< $var
7
diurno@tux06:~$ echo -n $var | wc -c
6
diurno@tux06:~$ var=ação
diurno@tux06:~$ echo ${#var}
4
diurno@tux06:~$ echo -n $var | wc -c
6
diurno@tux06:~$ echo -n $var | wc -m
4
diurno@tux06:~$ 
diurno@tux06:~/shell$ var=cadeia
diurno@tux06:~/shell$ expr substr $var 3 3
dei
diurno@tux06:~/shell$ echo ${var:2:3}
dei
diurno@tux06:~/shell$ echo ${var:2}
deia
diurno@tux06:~/shell$ echo ${var:2:1}
d
diurno@tux06:~/shell$ echo ${var:2:2}
de
diurno@tux06:~/shell$ echo ${var:2:-1}
dei
diurno@tux06:~/shell$ echo ${var:2:-2}
de
diurno@tux06:~/shell$ echo ${var:2:(-2)}
de
diurno@tux06:~/shell$ echo ${var:2:(-1)}
dei
diurno@tux06:~/shell$
```
> Como visto acima, cuidado com o **`wc`**

> Dica `wc`para lista maior linha do arquivo
```shell
diurno@tux06:~/shell$ wc -L quequeisso
70 quequeisso
diurno@tux06:~/shell$ 
```

### `expr index`
```shell
diurno@tux06:~/shell$ expr index 123456 5
5
diurno@tux06:~/shell$ expr index 123456 46
4
diurno@tux06:~/shell$ expr index 123456 64
4
diurno@tux06:~/shell$ 
```

> Dica: colocando o ./ no PATH usando `echo 'PATH=$PATH:.'>>~/.bashrc`
> Este comando se aplicara no proximo login. Para validar agora `source ~/bashrc` 

## Passagem de parametros
```shell
diurno@tux06:~/shell$ cat param1
echo $1
echo $2
echo $11
diurno@tux06:~/shell$ param1 {a..k}
a
b
a1
diurno@tux06:~/shell$ cat param2
echo $0
echo $2
echo ${11}
diurno@tux06:~/shell$ param2 {a..k}
./param2
b
k
diurno@tux06:~/shell$
diurno@tux06:~/shell$ cat param3
echo O programa $0 Recebeu $# Parametros
echo $1
echo $2
echo ${11}
diurno@tux06:~/shell$ param3
O programa ./param3 Recebeu 0 Parametros



diurno@tux06:~/shell$ param3 {a..z}
O programa ./param3 Recebeu 26 Parametros
a
b
k
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cat param4
echo O Programa $0 Recebeu $# Parametros Listados Abaixo:
echo $*
diurno@tux06:~/shell$ param4 {a..k}
O Programa ./param4 Recebeu 11 Parametros Listados Abaixo:
a b c d e f g h i j k
diurno@tux06:~/shell$
```

> Dica: para criar arquivos use `>` ao inves de ~~`touch`~~. ex. `> arquivo`


## `find`
find - search for files in a directory hierarchy
SYNOPSIS Basica --> find [starting-point...] [arg. pesq] [acao]

Importante
- sempre recursivo
- `-type f` ou `-type d` --> file ou directory
- `-name` ou `-iname`
- `-size 1000c` --> contagem de blocos de 512k (c=caracteres, k=1000, K=1024, ...)
- `-a` `-c` `-m` `time` --> time a=acessado, c=creation, m=modification do arquivo
- `grep -l` --> listar sem as sugeiras


```
diurno@tux06:~/shell/lixo$ touch {a..f}
diurno@tux06:~/shell/lixo$ cd -
/home/diurno/shell
diurno@tux06:~/shell$
diurno@tux06:~/shell$ find . -name ?
./d
./lixo/d
diurno@tux06:~/shell$ find . -name \?
.
./d
./lixo/e
./lixo/a
./lixo/c
./lixo/b
./lixo/d
./lixo/f
diurno@tux06:~/shell$ 
```
```
diurno@tux06:~/shell$ find . -type f | wc -l
290
diurno@tux06:~/shell$ find . | wc -l
304
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ ls | wc -l
151
diurno@tux06:~/shell$ ls -a | wc -l
153
diurno@tux06:~/shell$ find . -type d | wc -l
14
diurno@tux06:~/shell$ 
```
```
diurno@tux06:~/shell$ find . -type d
.
./nautilus-scripts
./nautilus-scripts/RootScripts
./nautilus-scripts/TratamentoImagem
./nautilus-scripts/Varios
./nautilus-scripts/Varios/FileInfo
./nautilus-scripts/Varios/SystemConfiguration
./nautilus-scripts/Varios/FileProcessing
./nautilus-scripts/Varios/FileSystemManagement
./nautilus-scripts/Varios/Archiving
./nautilus-scripts/Varios/Execute
./nautilus-scripts/Varios/Obsolete
./nautilus-scripts/Varios/Multimedia
./lixo
diurno@tux06:~/shell$ 
```




## `xargs`
- tudo o que recebe na entrada primaria ele botara atras do outro
- importa para o seu proprio shell
rm nao recebe dados da entrada primaria
```
diurno@tux06:~/shell$ cd lixo
diurno@tux06:~/shell/lixo$ > arq
diurno@tux06:~/shell/lixo$ alias rm=rm\ -i
diurno@tux06:~/shell/lixo$ ls | rm
rm: falta operando
Tente "rm --help" para mais informações.
diurno@tux06:~/shell/lixo$ ls | xargs rm
diurno@tux06:~/shell/lixo$ 
```
```
diurno@tux06:~/shell$ seq 20 | xargs echo linha
linha 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
diurno@tux06:~/shell$ seq 20 | xargs -n1 echo linha
linha 1
linha 2
linha 3
linha 4
linha 5
linha 6
linha 7
linha 8
linha 9
linha 10
linha 11
linha 12
linha 13
linha 14
linha 15
linha 16
linha 17
linha 18
linha 19
linha 20
diurno@tux06:~/shell$ seq 20 | xargs -n1 echo linha > tst
diurno@tux06:~/shell$ cat tst | xargs -n1
linha
1
linha
2
linha
3
linha
4
linha
5
linha
6
linha
7
linha
8
linha
9
linha
10
linha
11
linha
12
linha
13
linha
14
linha
15
linha
16
linha
17
linha
18
linha
19
linha
20
diurno@tux06:~/shell$ cat tst | xargs -L2
linha 1 linha 2
linha 3 linha 4
linha 5 linha 6
linha 7 linha 8
linha 9 linha 10
linha 11 linha 12
linha 13 linha 14
linha 15 linha 16
linha 17 linha 18
linha 19 linha 20
diurno@tux06:~/shell$
```
```
diurno@tux06:~/shell$ cd lixo/
diurno@tux06:~/shell/lixo$ ls
 a   arq   b   c   d   e   f  'nome ruim'
diurno@tux06:~/shell/lixo$ rm -f *
diurno@tux06:~/shell/lixo$ ls
diurno@tux06:~/shell/lixo$ touch arq{a..e}.{ok,err}
diurno@tux06:~/shell/lixo$ ls
arqa.err  arqb.err  arqc.err  arqd.err  arqe.err
arqa.ok   arqb.ok   arqc.ok   arqd.ok   arqe.ok
diurno@tux06:~/shell/lixo$ rm -f *
diurno@tux06:~/shell/lixo$ eval \>arp{a..e}.{ok,err}
diurno@tux06:~/shell/lixo$ ls
arpa.err  arpb.err  arpc.err  arpd.err  arpe.err
arpa.ok   arpb.ok   arpc.ok   arpd.ok   arpe.ok
diurno@tux06:~/shell/lixo$ ls | xargs -L2
arpa.err arpa.ok
arpb.err arpb.ok
arpc.err arpc.ok
arpd.err arpd.ok
arpe.err arpe.ok
diurno@tux06:~/shell/lixo$ ls | xargs -L2 diff
diurno@tux06:~/shell/lixo$ echo x > arqa.ok
diurno@tux06:~/shell/lixo$ ls | xargs -L2 diff
diff: faltando operando após "arqa.ok"
diff: Tente "diff --help" para mais informações.
diurno@tux06:~/shell/lixo$ ls | xargs -tL2 diff
diff arpa.err arpa.ok 
diff arpb.err arpb.ok 
diff arpc.err arpc.ok 
diff arpd.err arpd.ok 
diff arpe.err arpe.ok 
diff arqa.ok 
diff: faltando operando após "arqa.ok"
diff: Tente "diff --help" para mais informações.
diurno@tux06:~/shell/lixo$ 
```

### `xargs -i`
```
diurno@tux06:~/shell/lixo$ mkdir dir
diurno@tux06:~/shell/lixo$ ls arq?.ok | xargs -i bash -c 'mv {} dir; echo movi {}'
movi arqa.ok
diurno@tux06:~/shell/lixo$ ls
arpa.err  arpb.err  arpc.err  arpd.err  arpe.err  dir
arpa.ok   arpb.ok   arpc.ok   arpd.ok   arpe.ok
diurno@tux06:~/shell/lixo$ ls arp?.ok | xargs -i bash -c 'mv {} dir; echo movi {}'
movi arpa.ok
movi arpb.ok
movi arpc.ok
movi arpd.ok
movi arpe.ok
diurno@tux06:~/shell/lixo$ 
```




## `find` vs `xargs`
```
diurno@tux06:~/shell$ find . -type f -exec grep -l date {} \;
./nautilus-scripts/Varios/FileInfo/Show_MD5_Sum
./nautilus-scripts/Varios/SystemConfiguration/archiver-config
./nautilus-scripts/Varios/SystemConfiguration/RPM-tools
./nautilus-scripts/Varios/SystemConfiguration/RPM-install-update
./nautilus-scripts/Varios/FileProcessing/pixdir2html.pl
./nautilus-scripts/Varios/FileProcessing/dos2unix
./nautilus-scripts/Varios/Archiving/archiver-unarchiver
./nautilus-scripts/Varios/Execute/root-nautilus-here
./nautilus-scripts/Varios/Obsolete/RPM-install-update
./nautilus-scripts/Varios/Multimedia/rotate_jpg_right
./nautilus-scripts/Varios/Multimedia/mirror_jpg
./nautilus-scripts/Varios/Multimedia/rotate_jpg_left
./nautilus-scripts/Varios/Multimedia/rotate
./nautilus-scripts/Varios/Multimedia/Naudilus
./c3e3
./c4e1
./ArteAscii1.sh
./velha.sh
./natal.sh
./c4e3
./NatalComNeve.sh
./reldig.sh
./confusao
./rotinas.sh
./hora
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ find . -type f | xargs grep -l date
./nautilus-scripts/Varios/FileInfo/Show_MD5_Sum
./nautilus-scripts/Varios/SystemConfiguration/archiver-config
./nautilus-scripts/Varios/SystemConfiguration/RPM-tools
./nautilus-scripts/Varios/SystemConfiguration/RPM-install-update
./nautilus-scripts/Varios/FileProcessing/pixdir2html.pl
./nautilus-scripts/Varios/FileProcessing/dos2unix
./nautilus-scripts/Varios/Archiving/archiver-unarchiver
./nautilus-scripts/Varios/Execute/root-nautilus-here
./nautilus-scripts/Varios/Obsolete/RPM-install-update
./nautilus-scripts/Varios/Multimedia/rotate_jpg_right
./nautilus-scripts/Varios/Multimedia/mirror_jpg
./nautilus-scripts/Varios/Multimedia/rotate_jpg_left
./nautilus-scripts/Varios/Multimedia/rotate
./nautilus-scripts/Varios/Multimedia/Naudilus
./c3e3
./c4e1
./ArteAscii1.sh
./velha.sh
./natal.sh
./c4e3
./NatalComNeve.sh
./reldig.sh
./confusao
./rotinas.sh
./hora
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ find . -type f -exec grep -l date {} +
./nautilus-scripts/Varios/FileInfo/Show_MD5_Sum
./nautilus-scripts/Varios/SystemConfiguration/archiver-config
./nautilus-scripts/Varios/SystemConfiguration/RPM-tools
./nautilus-scripts/Varios/SystemConfiguration/RPM-install-update
./nautilus-scripts/Varios/FileProcessing/pixdir2html.pl
./nautilus-scripts/Varios/FileProcessing/dos2unix
./nautilus-scripts/Varios/Archiving/archiver-unarchiver
./nautilus-scripts/Varios/Execute/root-nautilus-here
./nautilus-scripts/Varios/Obsolete/RPM-install-update
./nautilus-scripts/Varios/Multimedia/rotate_jpg_right
./nautilus-scripts/Varios/Multimedia/mirror_jpg
./nautilus-scripts/Varios/Multimedia/rotate_jpg_left
./nautilus-scripts/Varios/Multimedia/rotate
./nautilus-scripts/Varios/Multimedia/Naudilus
./c3e3
./c4e1
./ArteAscii1.sh
./velha.sh
./natal.sh
./c4e3
./NatalComNeve.sh
./reldig.sh
./confusao
./rotinas.sh
./hora
diurno@tux06:~/shell$ 
```

## `shift 1`
apaga primeira variavel
```
iurno@tux06:~/shell/lixo$ set {a..d}
diurno@tux06:~/shell/lixo$ echo $1
a
diurno@tux06:~/shell/lixo$ echo $#
4diurno@tux06:~/shell$ 
diurno@tux06:~/shell/lixo$ 
diurno@tux06:~/shell/lixo$ shift
diurno@tux06:~/shell/lixo$ echo $1
b
diurno@tux06:~/shell/lixo$ shift 2
diurno@tux06:~/shell/lixo$ echo $1
d
diurno@tux06:~/shell/lixo$ echo $*
d
diurno@tux06:~/shell/lixo$ 
```


## `if`

```
diurno@tux06:~/shell/lixo$ ls xxx
ls: não foi possível acessar 'xxx': Arquivo ou diretório inexistente
diurno@tux06:~/shell/lixo$ echo $?
2
diurno@tux06:~/shell/lixo$ grep pqp /etc/passwd
diurno@tux06:~/shell/lixo$ echo $?
1
diurno@tux06:~/shell/lixo$ grep root /etc/passwd
root:x:0:0:root:/root:/bin/bash
diurno@tux06:~/shell/lixo$ echo $?
0
diurno@tux06:~/shell/lixo$ ls add
ls: não foi possível acessar 'add': Arquivo ou diretório inexistente
diurno@tux06:~/shell/lixo$ echo $?
2
diurno@tux06:~/shell/lixo$ ls ../add
../add
diurno@tux06:~/shell/lixo$ echo $?
0
diurno@tux06:~/shell/lixo$ 
```

## SCRIPTS

&& --> then
|| --> else

### Scritp: verificando usuario no passwd
```
diurno@tux06:~/shell/lixo$ if grep -q $1 $2
> then
> echo achei
> else
> echo nao achei
> fi
^C
nao achei
diurno@tux06:~/shell/lixo$ set root /etc/passwd
diurno@tux06:~/shell/lixo$ if grep -q $1 $2; then echo achei; else echo nao achei; fi
achei
diurno@tux06:~/shell/lixo$ set balb /etc/passwd
diurno@tux06:~/shell/lixo$ if grep -q $1 $2; then echo achei; else echo nao achei; fi
nao achei
diurno@tux06:~/shell/lixo$ set -o vi
diurno@tux06:~/shell/lixo$ if grep -q $1 $2; then echo achei; else echo nao achei; fi
if grep -q $1 $2; then echo achei; else echo nao achei; fi
nao achei
diurno@tux06:~/shell/lixo$ set -o emacs
diurno@tux06:~/shell/lixo$ chmod +x script1
diurno@tux06:~/shell/lixo$ script1 root /etc/passwd
achei
diurno@tux06:~/shell/lixo$ 

```
> Dica para Salvar script do prompt no arquivo
> `set -o vi`
> Esc+k v
> Salva arquivo

```
diurno@tux06:~/shell/lixo$ [ 01 = 1 ]; echo $?
1
diurno@tux06:~/shell/lixo$ [ 01 -eq 1 ]; echo $?
0
diurno@tux06:~/shell/lixo$
```


### Script: criando pasta dir
Encontre o arquivo `/shell/mmCreateDir`


### Script: validando hora
```
diurno@tux06:~/shell$ h=15:30
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ if [[ $h == [01][0-9]:[0-5][0-9] || $h == 2[0-3]:[0-5][0-9] ]]
> then
> echo hora ok
> else
> echo hora nok
> fi
hora ok
diurno@tux06:~/shell$
iurno@tux06:~/shell$ h=31:80
diurno@tux06:~/shell$ if [[ $h == [01][0-9]:[0-5][0-9] || $h == 2[0-3]:[0-5][0-9] ]]; then echo hora ok; else echo hora nok; fi
hora nok
diurno@tux06:~/shell$
```
Refactoring
```
diurno@tux06:~/shell$ if [[ $h =~ ([01][0-9]|2[0-3]):[0-5][0-9] ]]; then echo hora ok; else echo hora nok; fi
hora nok
diurno@tux06:~/shell$ h=15:30
diurno@tux06:~/shell$ if [[ $h =~ ([01][0-9]|2[0-3]):[0-5][0-9] ]]; then echo hora ok; else echo hora nok; fi
hora ok
diurno@tux06:~/shell$
```
Utilizando bordas e retrovisores
```
diurno@tux06:~/shell$ h=415:329
diurno@tux06:~/shell$ if [[ $h =~ ([01][0-9]|2[0-3]):[0-5][0-9] ]]; then echo hora ok; else echo hora nok; fi
hora ok
diurno@tux06:~/shell$
diurno@tux06:~/shell$ echo ${BASH_REMATCH[*]}
15:32 15
diurno@tux06:~/shell$ if [[ $h =~ ([01][0-9]|2[0-3]):([0-5][0-9]) ]]; then echo hora ok; else echo hora nok; fi
hora ok
diurno@tux06:~/shell$ echo ${BASH_REMATCH[*]}
15:32 15 32
diurno@tux06:~/shell$ if [[ $h =~ ^([01][0-9]|2[0-3]):([0-5][0-9])$ ]]; then echo hora ok; else echo hora nok; fi
hora nok
diurno@tux06:~/shell$ echo ${BASH_REMATCH[*]}

diurno@tux06:~/shell$ h=15:30
diurno@tux06:~/shell$ if [[ $h =~ ^([01][0-9]|2[0-3]):([0-5][0-9])$ ]]; then echo hora ok; else echo hora nok; fi
hora ok
diurno@tux06:~/shell$ echo ${BASH_REMATCH[*]}
15:30 15 30
diurno@tux06:~/shell$
```

### Script: utilizando operacao matematica
```
diurno@tux06:~/shell$ var=20
diurno@tux06:~/shell$ ((var > 10))&& echo maior
maior
diurno@tux06:~/shell$
```
A operacao `--` diminuira o valor da variavel, parecido com o `for (i--)`.
```
diurno@tux06:~/shell$ ((--var > 10))&& echo maior
maior
diurno@tux06:~/shell$
```

### Script: debug de 10 em 10 linhas
```
diurno@tux06:~/shell$ for ((i=1;i<100;)); { echo linha $i; ((i++ % 10 == 0)) && read -p "de enter"; }
linha 1
linha 2
linha 3
linha 4
linha 5
linha 6
linha 7
linha 8
linha 9
linha 10
de enter
linha 11
...

```

### Script: verificando usuario no passwd 2
Encontre o arquivo `/shell/mmVerificaUsuario`
```
diurno@tux06:~/shell$ vim mmVerificaUsuario
diurno@tux06:~/shell$ chmod +x mmVerificaUsuario 
diurno@tux06:~/shell$ mmVerificaUsuario root
root:x:0:0:root:/root:/bin/bash
diurno@tux06:~/shell$ mmVerificaUsuario mat
usuaio nao existe
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ echo $?
8
diurno@tux06:~/shell$
```

Logando erros
```
diurno@tux06:~/shell$ mmVerificaUsuario fafas >/dev/null
diurno@tux06:~/shell$ mmVerificaUsuario fafas 2>/dev/null
usuaio nao existe
diurno@tux06:~/shell$ echo $1
balb
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ vi mmVerificaUsuario 
diurno@tux06:~/shell$ mmVerificaUsuario fafas
usuaio nao existe
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ mmVerificaUsuario fafas 2>/dev/null
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ cat mmVerificaUsuario
reg=$(grep "^$1\>" /etc/passwd)||{
  echo usuaio nao existe >&2
  exit 8
}
echo $reg
diurno@tux06:~/shell$
```
> bacalho 2>> log.err



## `case`
Sintaxe:
  case $var in
    para1)
      ______
      ______;;
    para1)
      ______
      ______;;
    para1)
      ______
      ______      
  esac
  
  
```
```
### Script: case
Encontre o arquivo `/shell/mmCase`


### Exercicio

hora=$(date +%H)
minuto=$(date +%M)

```
diurno@tux06:~/shell$ date "+data: %d/%m/%Y%nhora: %H:%M"
data: 04/12/2019
hora: 17:49
diurno@tux06:~/shell$ 
```


# Aula4

## Exercicio 1 pag.252
h=$(date +%H)
m=$(date +%M)
ap=am
((h>12))&&{
  let h-=12
  ap=pm
}
echo $h:$m $ap

## Exercicio 2 pag.252
h=$(date +%H)
case $h in
  0[0-9]|1[01]) echo 'bom dia'
  1[2-7]) echo 'boa tarde'
  \*) echo 'boa noite'
esac


# `for`
For processa comparacoes
## `for ((i=1;i<10;i++))`
```
diurno@tux06:~$ for ((i=1;i<10;i++)); { echo $i; }
1
2
3
4
5
6
7
8
9
diurno@tux06:~$ for ((;i<20;i++)); { echo $i; }
10
11
12
13
14
15
16
17
18
19
diurno@tux06:~$ for ((;i<10;)); { echo $((++i); }
> 
> ^C
diurno@tux06:~$ for ((;i<10;)); { echo $((++i)); }
diurno@tux06:~$ for ((;i<30;)); { echo $((++i)); }
21
22
23
24
25
26
27
28
29
30
diurno@tux06:~$ for ((;;)); { echo $((++i)); ((i==40)) && break; }
31
32
33
34
35
36
37
38
39
40
diurno@tux06:~$ 
```


## `for arq in *; do echo $arq; done`
```
diurno@tux06:~$ for arq in *
> do
> echo $((++k)) $arq
> done
1 Desktop
2 Documentos
3 Downloads
4 shell
diurno@tux06:~$
```
Convertendo em listas usando o IFS para substituir caracteres por branco
```
diurno@tux06:~/shell$ reg=$(grep ^root: /etc/passwd)
diurno@tux06:~/shell$ echo $reg
root:x:0:0:root:/root:/bin/bash
diurno@tux06:~/shell$ ifs=:
diurno@tux06:~/shell$ IFS=:
diurno@tux06:~/shell$ echo $reg
root x 0 0 root /root /bin/bash
diurno@tux06:~/shell$ for pedaco in $reg
> {
> echo $((++x)) $pedaco
> }
1 root
2 x
3 0
4 0
5 root
6 /root
7 /bin/bash
diurno@tux06:~/shell$
diurno@tux06:~/shell$ set $reg
diurno@tux06:~/shell$ echo $1
root
diurno@tux06:~/shell$ echo $2
x
diurno@tux06:~/shell$ echo $3
0
diurno@tux06:~/shell$
```
Para o shell náo ver o IFS, proteja a variavel
```
diurno@tux06:~/shell$ echo "$reg"
root:x:0:0:root:/root:/bin/bash
diurno@tux06:~/shell$ 
```

### `for` usando o IFS
Alterando lingua para um comando. Poderiamos alterar o IFS somente para um comando, geralmente o `read`
```
diurno@tux06:~/shell$ LANG=C date
Thu Dec  5 10:33:57 -03 2019
diurno@tux06:~/shell$ date
qui dez  5 10:34:27 -03 2019
diurno@tux06:~/shell$ 
```
```
diurno@tux06:~/shell$ IFS=-^
diurno@tux06:~/shell$ for num in $(cat arq20)
> do
> echo $((++m)) $num
> done
1 1
2 2
3 3

4
4 5
5 6
7
6 8
7 9
diurno@tux06:~/shell$ IFS=-^$'\n'
diurno@tux06:~/shell$ m=0
diurno@tux06:~/shell$ for num in $(cat arq20); do echo $((++m)) $num; done
1 1
2 2
3 3
4 4
5 5
6 6
7 7
8 8
9 9
diurno@tux06:~/shell$ 
```


### `for` sem `in`
quando voce nao especifica o parametro, o shell utiliza o que voce enviou a ele, atraves do ex.`set $reg`
```
diurno@tux06:~/shell$ 
diurno@tux06:~/shell$ for pedaco
> do
> echo $((++w)) $pedaco
> done
1 root
2 x
3 0
4 0
5 root
6 /root
7 /bin/bash
diurno@tux06:~/shell$ 
```


## `while`
while processa somente intrucoes
```
diurno@tux06:~/shell$ while who | grep -q Ciro
> do
> sleep 30
> done; echo O Ciro deu exit. Nao hesite, ligue para ele.
O Ciro deu exit. Nao hesite, ligue para ele.
diurno@tux06:~/shell$ 

```
## `until`
Oposto do `while`,  
```
diurno@tux06:~/shell$ until who | grep -q Ciro; do sleep 30; done; echo O Ciro ta na area.
diurno@tux06:~/shell$
```


## Exercicio Pag. 273

Fixing IFS
```
diurno@tux06:~/shell$ IFS=' '$'\t\n'
diurno@tux06:~/shell$
diurno@tux06:~/shell$ od -h <<< "$IFS"
0000000 0920 0a0a
0000004
diurno@tux06:~/shell$
```
Resolucao
Encontre o arquivo `/shell/mmex8`
Encontre o arquivo `/shell/mmex9`



