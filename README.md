# Docker do básico ao avançado. 

André Iacono - Udemy Início 19-10-24 


## Pré-Requisitos

###  Instalando o Docker localmente:

- [Instalando o docker](https://docs.docker.com/desktop/) via desktop do Windows/Mac/Linux (Para Linux é necessario escolher a distribuição(Ubuntu,Debian e etc)). 

- [Download do docker](https://www.docker.com/products/docker-desktop/)


## Linux 

Podemos pegar do Docker Hub e rodar na nossa máquina rodando um container.

Dentro do Docker Hub eu tenho a imagem da minha escolha

Acesse o [Hub.docker.com](https://hub.docker.com/)
Localize a imagem da sua escolha e rode o comando
Ou é possível rodar uma imagem temporárioa (interativa)s

Para para rodar uma imagem interativa:

1. Acesse seu prompt e digite o comando 
```
docker ps

```
Mas para verificar quais container ativos eu tenho na minha máquina eu utilizo o comando. 
```
docker ps -a 

```
2. Para baixar o docker de modo geral utilizamos o comando:

```
docker pull ubuntu

```
Mas, para rodar o docker de forma interativa eu rodo o seguinte comando:

```
docker run -it

```
Dica, o meu de primeira não rodou, então via orientação do prompt utilizei o comando:

```
docker pull --help 

```
em seguida:

```
docker pull 

```
3. Verifique se o root@ aparece na tela, isso indica que você realizou o download neste caso do Ubuntu.

4. Para visualizar o meu usuário eu utilizo o comando:
```
whoami 

```
5. Para inserir algo na tela utilizo o comando bash
```
echo escrevaaquioseutexto 

```
Será retornado na tela o meu texto

6. Para localizar o qual pasta(path) eu estou eu utilizo o comando:
```
echo e$0

```
7. Para visualizar o histórico dos últimos comandos realizados no prompt, eu posso utilizar
    - as setas do teclado para cima;
    - o comando:
        ```
        history

        ``` 

## Instalando pacotes no Linux

Listando quais pacotes eu tenho atualmente dentro da minha distribuição Linux:


1. Utilize o comando **apt(advanced packed to)**. Onde será mostrado no prompt a listagem de itens instalados na minha imagem linux

```
apt list

```
2. Porém o ideal é realzar uma atualização no linux.
```
apt update

```
Para visualizar os itens atualizados, rode novamente o *apt list*

**exemplo**

Vamos instalar um pacote de edição de texto(nano):
```
apt install nano

```
Para testar se está ok, digite o comando novamente e será exibida uma nova tela, onde podemos criar um texto:
```
nano

```
```
nano helloword.txt

```

dentro da tela eu posso escrever um texto da minha preferência

```
hi docker

```
Atenção para os atalhos da tela, para utilizá-los eu uso o comando

crtl + aletradaminha preferência


## Sistema de Arquivos

Lembrando que diferente do Windows, no Linux a barra é invertida 

Dica: Consulte uma documentação referente à estrutura de pastas do Linux como [Linux Directory Structure](https://www.geeksforgeeks.org/linux-directory-structure/)


## Navegando no Linux

1. O comando para listar: ls

Geralmente quando listamos algo, as informaçõe serão apresentadas na horizontal.

Ao utilizar o comando, a estrtura será listada na horizontal:
```
ls -1

```

2. Para ter informações detalhadas sobre o que se contra dentro do diretório utilize o comando:
```
ls -l 

```

3. Para acessar um diretório, utilize o comando **cd ( Command Change Directory)**
```
cd 

```
**Exemplo**
Acessando um diretório de exemplo etc
```
cd/etc

```
Dentro do diretório etc, temos a pasta **pwd**

```
pwc/etc

```
demos um **ls** para listar o conteúdo da pasta 
```
ls

```
Dica: Para completar o nome de uma pasta eu posso utilizar o inicio do nome da pasta + a tecla **TAB**

Para retornar para um diretório anterior utilize o comando 
```
cd ..

```

## Criando diretórios e arquivos

Escolha o diretório de sua escolha e utilze o comando
```
cd ~

```
A tela voltará para a pasta raiz principal exibindo a mensagem : root@8344c4fddd0b:~# 

Para retornar à pasta da nossa escolha utilize o comando 
```
cd / root/NOMEDOMEUDIRETORIODEESCOLHA

```

Para criar um arquivo novo utilize o comando **move**
```
cd / root/NOMEDOMEUDIRETORIODEESCOLHA

```

## Criando arquivos

Você pode criar um arquivo utilizando o ***touch***
```
touch ana.txt

``` 
a seguir :
```
ls

```
Será listado os arquivos que se encontram no diretório, inclusive o arquivo de exemplo 

> **ana.txt**  bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

Posso criar mais de um arquivo utilizando o ***touch*** 

```
touch ana1.txt ana2.txt ana3.txt 

```
listando: 
```
ls

```
ou 
```
ls -1

```

>  **ana.txt**   **ana2.txt**  bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
**ana1.txt**  **ana3.txt**  boot  etc  lib   media  opt  root  sbin  sys  usr

## Removendo arquivos

Utilizamos o remove, comando ***rm***, mais o nome(s) do(s) arquivo(s) da minha escolha
```
rm ana.txt

```

Ou posso utlizar o remove, mais os arquivos que iniciam com o mesmo/letra
```
rm ana*

```

> bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

todo os arquivos ana.txt foram removidos.


## Editando arquivos

Para criar um arquivo posso utilizar o touch, porém se eu quiser criar e edita eu posso criar via nano:

```
nano ana.txt

```
Utilize os comando indicados no prompt de texto para salvar e sair.

Para visualizar o conteúdo do arquivo sem precisar entrar no mesmo, utiliz o comando  concatenate (concatenar) ***cat***

```
cat ana.txt

```

É possível utilizar o comando ***more** também, o porém é que ele aparece resultados debaixo pra cima, sendo necessário utilizar a barra de rolagem para acessar o conteúdo da página.

Há o comando ***less*** também 



## Redirecionamentos no Linux

Podemos redirecionar um conteúdo existente em um arquivo txt para outro arquivo **concatenando** as informacoes. 

1. Consulte as informações do arquivo
```
cat ana.txt

```
> root@56a774d9b506:/# cat **ana.txt**
Ana Laura


Agora vamos duplicar esse conteúdo em um novo arquivo, neste caso nomeado o segundo arquivo como  **teste.txt**

```
cat ana.txt > teste.txt 

```
vamos listar para verificar se o arquivo teste foi criado 

```
ls

```

>  **ana.txt**       bin    dev   home   lib64   mnt   proc   run    srv   **teste.txt**  usr
'ana.txt md'   boot   etc   lib    media   opt   root   sbin   sys   tmp         var


Para conferir se o conteúdo é o mesmo agora utilizamos o comando cat no arquivo teste.txt

```
cat teste.txt 

```
> root@56a774d9b506:/# cat **teste.txt**
Ana Laura**

Podemos também concatenar dois arquivos em um novo único arquivo:

```
cat teste.txt ana.txt > novoarquivo.txt

```
> root@56a774d9b506:/# ls
 **ana.txt**       bin    dev   home   lib64   mnt               opt    root   sbin   sys         tmp   var
'ana.txt md'   boot   etc   lib    media   **novoarquivo.txt**   proc   run    srv    **teste.txt**   usr

Consultando o arquivo:

> root@56a774d9b506:/# cat novoarquivo.txt
Ana Laura
Ana Laura

as informações foram concatenadas em um único arquivo. 

