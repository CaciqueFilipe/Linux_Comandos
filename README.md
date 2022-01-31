<div align="center">
  <h1>Comandos Básicos Linux no terminal:</h1>
</div>

### ------  Listar conteudo de uma Pasta ---------------

  ls

Todo comando possui possibilidade de usar parametros, eles são dados - e uma letra, ou pode usar -- e a palavra:

	ls -l  	ou 		ls --long
  
A nomenclatura do arquivo, ex:<br/>
	drwxr-xr-x 3 filipe filipe 4096 jan 29 18:46  Documentos
  ##### - o começo "drwxr-xr" é referente a permissão;
  ##### - o numero depois, indica quantas pastas tem dentro;
  ##### - Depois o usuario proprietario;
  ##### - o grupo proprietario;
  ##### - o tamanho;
  ##### - a data de criação ou operação;
  ##### - Nome da pasta.

#### Podemos usar mais de um parametro, ex:
	ls -l -h (para uma saida mais humana)

#### Para mostrar até os arquivos ocultos usa-se:
	ls -a 		ou ls --all

#### Pode-se junta os dois comandos acima com:
	ls -la ou ls -lah 

#### Para pegar lista de dentro do diretorio:
	ls /(diretorio) 

#### Para ver estrutura como arvore:
	ls -R nome_da_pasta/

###### * o ~$ indica a pasta do usuario *

### ---------- Navegar entre pastas ---------------------------

#### Para entrar e sair de pastas usa-se o comando cd:
	cd ~ (você volta para a pasta raiz)
	cd .. (Para retornar uma pasta)
	cd / (Acessa a pasta raiz)

##### * Arquivos começando com ponto ficam ocultos, 
##### * Linux diferencia todos os caracteres

#### Para ver todos os comandos do linux:
	cd /  para raiz, depois usar ls /bin

#### Para entrar em pasta especifica do diretorio:
##### * Ex: estou em ~/Documentos/Cursos/Hardware/Modulo 1/ e quero ir para Documentos:
	cd ~/Documentos

### ---------- Apagar pastas -----------------------------------
	rmdir nome_da_pasta (Acusa erro se tiver conteudo)
	rm ~/Documentos/linux/oi.txt (Remove o arquivo oi.txt)
	rm -rf Linux/ (apaga a pasta e todo seu conteudo)

### ---------- Ver informações da Cpu --------------------------

#### Para ver informações da Cpu:
  "lscpu" ou 
entrar na raiz  "cd /" e dar o comando "cat proc/cpuinfo"


### ---------- Ver conteudo do arquivo --------------------------
  #### Usa- se o cat:
	cat oi.txt

### ---------- Pegar caminho do arquivo da raiz -----------------

#### Para ver o caminho do diretorio atual use:
	pwd

---------- Pegar pegar caminho relativo (em diante)----------

#### Para pegar caminho relativo use:
	pwd


### ----------- Para criar pastas --------------------------------

#### Para criar pastas com o comando:
	mkdir "nome da pasta"

#### Ou mais de uma pasta:
	mkdir "nome da pasta" "nome da pasta" "nome da pasta"

#### Para criar subpastas dentro da criada:

	mkdir -p Cursos/Hardware/Módulo\ 1/
(o -p faz ele verificar se existe a pasta e faz o restante)
(o \ 1 faz um espaço em branco deixando a pasta como "Modulo 1")

#### Ou voce pode colocar tudo entre aspas:
	mkdir -p "Cursos/Hardware/Módulo 2/"

### ----------- Touch (editar arquivo)---------------------------
#### Para criar um arquivo na pasta criada:
	touch oi.txt

#### Para editar texto no terminal usa-se o "nano", Ex:
	nano oi.txt (sabendo que esta na pasta do arquivo)

### ---------------- Dúvidas ---------------------------

#### Duvidas voce pode usar o --help ou acessar o manual,Ex:
	ls --help
	man ls


### ----- Para listar os comando efetuados por voce --------------
	history

#### Para repetir um comando desta lista você pode colocar 
	!10 (numero do comando na lista do history)


### ---- Para criar temporariamente comandos personalizados ------
	alias rm="rm -I"
##### * Cria um atalho que pergunta na hora de excluir se vc tem certeza;
##### * Funciona somente enquanto o terminal estiver aberto.


### ---------- Referência Global ---------------------------------
ex: comando parametro argumento

	ls etc/ 

#### Para selecionar certos arquivos vc usa o argumento, ex:
	ls etc/*.conf (Tras os arquivos .conf dentro da pasta etc)

#### Para arquivos que tenham a letra x no meio do nome,ex:
	ls etc/*x*

#### Começando com a letra:
	ls etc/f*

#### Usando ? substitui apenas uma letra:
	ls /etc/?as* (Primeiro caractere não sabemos, segundo é "a", depois "s" e depois qualquer coisa)

### ----- [] usados para pegar faixa de caracteres -------------
	ls /etc/f[a-i]* (o segundo caractere pode variar do a ao i)

##### OBS: o "-" identifica intervalo, a "," separador de grupos


### ----- uso das {} Referencia a padrões ----------------------
	ls /etc/?{am,ul}* (Primeiro caractere não sei, segundo caractere am e terceiro ul, depois qualquer coisa)



### ----------- Manipulação de arquivos ------------------------

#### Para Saida de arquivos:
	cat
	ex:
	cat oi.txt
	
#### Além do cat vc tem o less, que usa paginação e vc pode usar as setas do teclado para subir ou descer no arquivo.
	less
	ex:
	less /etc/services
	
#### O tac imprime o arquivo da ultima linha para a primeira do arquivo:
	tac /etc/services


### ----------- Copiando arquivos ------------------------------
#### Para copiar arquivos usa-se o cp (comando, parametros, argumentos)
	Ex, copiando arquivos da pasta Faculdade para outra pasta:
	mkdir Faculdade
	cp aulalinux.txt Faculdade/

#### Apagar arquivos:
	rm aulalinux.txt
	
#### Para mover arquivos usa-se o mv:
	mv aulalinux.txt Linux/
	
#### Copiando arquivos .conf da pasta etc para a pasta temporario:
	cp /etc/*.conf temporario/

#### Para renomear o arquivo voce tbm usa o mv
	mv temporario/ Temp
	

## PARA PEDIR PERMISSÃO PARA REMOVER MAIS DE 3 ARQUIVOS 	

	alias em='/bin/rm -I'
	
