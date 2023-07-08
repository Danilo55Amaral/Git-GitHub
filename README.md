<h1>
     <img align="center" width="40px" src="https://seeklogo.com/images/G/github-logo-2E3852456C-seeklogo.com.png">
    <span> Versionamento de Código com Git e GitHub</span>
</h1>

#### Criando um Repositório Local
Acesse a pasta que deseja criar um repositório Git através do terminal ou clique botão direito do mouse no atalho em “Git Bash Here”:
1. Inicialize um repositório Git no diretório escolhido:
    ```bash
    $ git init
    ```
2. Conecte o repositório local com o repositório remoto:
    ```bash
    $ git remote add origin https://github.com/username/nome-do-repositorio.git
    ```
##

### Checando o status dos arquivos a serem commitados
Comando que checa o status dos arquivos no repositório
 ```bash
  $ git status
  ```
##

### Salvando Alterações no Repositório Local
Para criar um commit adicione os arquivos para serem comitados ou utilize . para adicionar 
todos os arquivos novos ou modificados.
```bash
$ git add nome-do-arquivo
```
```bash
$ git add .
```
Crie um commit e para isso insira uma mensagem descritiva uma boa sugestão é pesquisar sobre
commits semânticos e utilizar esse padrão.
```bash
$ git commit -m "descrição semântica do commit"
```

##

### Desfazendo Alterações no Repositório Local
Como alterar a mensagem do último commit
```bash
$ git commit --amend
```
Alterando a mensagem sem abrir o editor:  
```bash
$ git commit --amend –m"nova mensagem"
```
##

#### Como desfazer um commit
```bash
$ git reset
```
```bash
$ git reset --soft
```
```bash
$ git reset --mixed
```
```bash
$ git reset --hard
```
##

### Enviando Alterações para o Repositório Remoto
Como enviar as alterações do repositório local para o remoto:
  ```bash
  $ git push
  ```
Enviando para a Branche main
  ```bash
  $ git push origin main
  ```
Puxando alterações de um repositório remoto para o local ele faz a busca e mescla.
   ```bash
  $ git pull
  ```
   ```bash
  $ git pull origin main
  ```
##

### Trabalhando com Branches
Podemos traduzir uma Branch como Ramo, que é uma ramificação do projeto.
Um ponteiro para um commit na linha do tempo de commits do repositório
quando uma nova Branch é criada a partir de outra que já existe, essa 
nova Branch apontará para o mesmo commit da Branch da qual ela foi ramificada.
Checando as Branchs existentes
 ```bash
  $ git branch
  ```
Troca a Branch criando uma nova e trocando a atual pela nova
 ```bash
  $ git checkout -b nova-branch
  ```
Apenas trocando de Branch
 ```bash
  $ git checkout nome-da-branch
  ```
Apagando uma Branch
 ```bash
  $ git branch -d nome-da-branch
  ```
Checando o último commit de cada Branch
 ```bash
  $ git branch -v
  ```
Checando qual commit é apontado pela Branch
 ```bash
  $ git log
  ```
Mesclando as Branchs utilizamos o merge e colocamos o nome da branch que queremos mesclar com a main (Principal)
 ```bash
  $ git merge nome-da-Branch
  ```
##

### Trabalhando com Conflitos nas Branchs
Quando existem alterações no reporitório remoto que ainda não existem no repositório local
e tentamos dar um push para enviar atualizações o git irá gerar um erro, isso por que ele 
vai detectar que eixtem conflitos com o repositório remoto.

Utilizamos o seguinte comando abaixo e o git irá mostrar o conflito, podemos decidir quais alterações 
podem serem feitas
 ```bash
  $ git pull
  ```
ou
 ```bash
  $ git pull origin main
  ```
Após isso podemos commitar novamente os arquivos em um novo commit e dar um push.

## Entendendo mais a Fundo
Esse comando git pull é a junção dos comandos git fetch + git merge 

Para baixar alterações que estejam no repositório remoto mais ainda não existem
no repositório local, porém sem mesclar com o repositório local para isso 
podemos utilizar o comando fetch
 ```bash
  $ git fetch origin main
  ```
O comando abaixo podemos ver a diferença entre as branchs local e remota
 ```bash
  $ git diff main origin/main
  ```
Para trazer essas alterações do repositório remoto para o reporitório local após
ter utilizando o fetch, util quando queremos apenas baixar conteúdo da branch remota
para a local sem mesclar
 ```bash
  $ git merge origin/main
  ```
Vamos supor que queremos clonar apenas uma Branch específica de um repositório remoto
vamos na parte de Code e copiamos o Codigo HTTPS ou SSH, em seguida utilizamos o comando
git clone passando o link e a flag --branch indicando o nome da branch que queremos clonar, 
a flag --single-branch indica que queremos clonar apenas essa Branch especifica.
 ```bash
  $ git clone link-do-HTTPS --branch nome-da-branch --single-branch
  ```
##

### Clonando um Repositório
Para clonar um repositório acesseo do GitHub e em seguida na parte de Code
cópie o código HTTPS ou SSH isso depende de como sua conta esteja autenticada
em seguida abra o GitBash e utilize o comando git clone passando o código 
que foi copiado do repositório.
 ```bash
  $ git clone link-contento-HTTPS-ou-SSH
  ```
