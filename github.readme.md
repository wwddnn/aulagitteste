
# COMANDOS DO GIT PARA SALVAR A PRIMEIRA VERSÃO:
## comandos do git: obs. os comandos abaixo sao usados dentro do GIT BASH.

ls
vai listar os arquivos da pasta que você esta.

git init
vai iniciar o repositorio do git na pasta que você esta.

git add . 
vai colocar os arquivos em um local temporário. vc coloca os arquivos que quiser nessa area temporaria. 
se nao quiser colocar todos os arquivos não precisa colocar, mas em geral se coloca sim todos os arquivos.

obs git status
ele vai mostrar pra mim o status do projeto. posso usar esse comando se eu quiser, depois por exemplo de fazer o git add. acima

git commit -m "mensagem que voce quiser"
vou colocar entre aspas uma mensagem explicativa com o que eu fiz ate o momento.
mas nesse momento ele ainda não enviou isso para o github, isso vai ser feito com o comando push mais abaixo

obs git status
posso agora novamente dar um git status, que vai mostrar o commit que eu acabei de fazer

git branch -M main
github usa o nome main para salvar o historico de commits. antigamente usava o comando master. 
ideal é que seja o comando main. então para garantir que seja usado o comando main, fazemos esse codigo git branch -M main

obs agora o ideal é ir no site do GITHUB e criar um novo projeto vazio por lá. 
### **obs escolher o SSH (por isso que o link começará com git@github.com:wwddnn ... )
o próximo passo então é voltar para o GIT BASH e então vamos usar o comando abaixo, para ele associar esse projeto do meu computador com o repositório que acabei de criar la no github site.

### obs dica: para limpar o terminal do GIT BASH usar o comando clear

git remote add origin git@github.comseuusuario/seuprojeto.git
esse comando inteiro acima, que é um comando grande, você pode pegar direto na página do GITHUB site do repositório que acabei de criar
agora sim, nesse momento o meu repositório local esta associado com o meu repositório no site do GITHUB

git push -u origin main
pronto, agora é só enviar para o repositório do GITHUB!!!!


# COMANDOS DO GIT PARA SALVAR UMA NOVA VERSÃO: 
## é você fazer uma modificação no projeto e então salvar uma nova versão.
## vamos dizer que eu alterei algo simples no meu projeto, nesse exemplo alterei algo no arquivo vendas.html

git status
para mostrar como esta o nosso projeto

git add .
para ele adicionar na área temporária essa mudança

git commit -m "Acrescentado valor das vendas"
vai registrar o nosso commit, que foi a nossa alteração

git push
agora como já não é mais a primeira vez, é só fazer o simples comando git push, que ele já envia tudo

******************************************************************************************

# COMANDOS PARA VER E REGISTRAR SUA IDENTIFICAÇÃO: 
## para ver o name e email:

git config -- global user.name "seu name"
vai configurar meu nome

git config --global user.mail "seu email"
vai configurar seu email

git config --list
aparece as configurações todas 

**********************************************************************************
# COMO ENXERGAR ARQUIVOS OCULTOS:

ir em menu inciar no windows, depois em desmarcar a opção 'ocultar as extensões dos tipos de arquivos conhecidos'.
e depois marcar a opção 'mostrar arquivos, pastas e unidades ocultas'

**********************************************************************************
# CONFIGURAR CHAVE SSH PARA O GITHUB:
## vai cadastrar qual computador pode ser usado no seu nome.

passo a passo:
tem que gerar uma chave SSH no github.
obs buscar no google como gerar chave ssh no github.

usar o seguinte comando no gitbash:
ssh-keygen -t rsa -b 4096 -c "seu email"

pronto, agora ja foi gerada a chave ssh no computador, então eu pego essa chave que gerou que fica dentro do arquivo no seu computador...
e então copio a chave e colo la no site github em settings.

**********************************************************************************
# CLONAR O PROJETO E O HISTORICO QUE ESTA NO GITHUB PARA O MEU COMPUTADOR:

passo1: 
git clone git@github.com...
vou copiar atraves do clone o projeto que esta la no github, para o meu computador.
obs. vai clicar no botao que tem o endereco do projeto, pq ele vai trazer para o clone o historico de versoes.
obs copiar o link no formato SSH
atencao nao vai clicar em fazer download nao, pq aqui ele nao traz o historico de versoes.
### obs se precisar trocar de pasta dentro do git bash, basta usar o comando 'cd' e depois o nome da pasta que voce quer ir.
### obs se quiser abrir o vscode dentro do git bash é só usar o comando 'code . '

passo2:
git add .
vou adicionar os arquivos na minha area stage.

passo3:
git commit -m "mensagem explicativa"

passo4:
git push

obs git log
esse comando mostra o historico de versoes do projeto.
da pra fazer varios git add . e ele vai juntando todas essas adições na area de stage, mas ainda nao fez commmit nem nada.












