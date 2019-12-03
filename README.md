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


