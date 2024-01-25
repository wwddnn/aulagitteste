
## COMANDOS DO GIT PARA SALVAR A PRIMEIRA VERSÃO:
### comandos do git: obs. os comandos abaixo sao usados dentro do GIT BASH.

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


### COMANDOS DO GIT PARA SALVAR UMA NOVA VERSÃO: 
### é você fazer uma modificação no projeto e então salvar uma nova versão.
### vamos dizer que eu alterei algo simples no meu projeto, nesse exemplo alterei algo no arquivo vendas.html

git status
para mostrar como esta o nosso projeto

git add .
para ele adicionar na área temporária essa mudança

git commit -m "Acrescentado valor das vendas"
vai registrar o nosso commit, que foi a nossa alteração

git push
agora como já não é mais a primeira vez, é só fazer o simples comando git push, que ele já envia tudo


### COMANDOS PARA VER E REGISTRAR SUA IDENTIFICAÇÃO: 
### para ver o name e email:

git config -- global user.name "seu name"
vai configurar meu nome

git config --global user.mail "seu email"
vai configurar seu email

git config --list
aparece as configurações todas 



### COMO ENXERGAR ARQUIVOS OCULTOS:

ir em menu inciar no windows, depois em desmarcar a opção 'ocultar as extensões dos tipos de arquivos conhecidos'.
e depois marcar a opção 'mostrar arquivos, pastas e unidades ocultas'


### CONFIGURAR CHAVE SSH PARA O GITHUB:
### vai cadastrar qual computador pode ser usado no seu nome.

passo a passo:
tem que gerar uma chave SSH no github.
obs buscar no google como gerar chave ssh no github.

usar o seguinte comando no gitbash:
ssh-keygen -t rsa -b 4096 -c "seu email"

pronto, agora ja foi gerada a chave ssh no computador, então eu pego essa chave que gerou que fica dentro do arquivo no seu computador...
e então copio a chave e colo la no site github em settings.


### CLONAR O PROJETO E O HISTORICO QUE ESTA NO GITHUB PARA O MEU COMPUTADOR:

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
esse comando é pra salvar as alterações no meu computador.

passo4:
git push
é pra mandar para o repositório remoto.
obs se for a primeira vez que vc atua nesse projeto, entao tem que fazer o comando 'git push -u origin main' ao inves desse comando acima que é somente o git push.

obs git log
esse comando mostra o historico de versoes do projeto.
da pra fazer varios git add . e ele vai juntando todas essas adições na area de stage, mas ainda nao fez commmit nem nada.
obs quando chamar  o git lob, e aparecer do lado do commit o texto 'origin/main, origin/HEAD' significa que ate aqui esta salvo la no github, 
mas dai pra cima é pq ainda nao esta salvo la no github.


### GIT LOG PARA VERIFICAR O HISTORICO DE VERSÕES:

git log
mostra o histórico de versões

git log --oneline
ele mostra de forma resumida o histórico de versões do projeto.


### ENTENDENDO  GIT STATUS, GIT ADD E STAGE:

### GIT STATUS
informa o status do projeto naquele momento.
obs nesse comando, pode aparecer 3 situações: 
* modified
* untracked : é quando tem arquivo novo que eu criei mas ainda não salvei na area de stage. exemplo quando crio uma pagina html nova no meu projeto. aparece no gitbash como 'untracked files'.
* deleted : é quando você deleta algum arquivo, ele diz então que isso ocorreu.

git reset
obs se quiser usar esse comando, ele tira do stage as alterações que fiz agora há pouco como comando git add .

### GIT ADD . SOBRE.HTML
### se quiser adicionar somente alguns arquivos, e não todos. nesse caso somente o arquivo 'sobre.html' que eu quis adicionar. depois na sequência só fazer um git commit -m "mensagem".

### GIT STAGE
obs onde aparece no gitbash assim... 'HEAD > main' é porque eu fiz o add . e fiz o commit, porem ainda não fiz o push então ele ainda não foi para o repositório remoto do github.


### GIT DIFF: DIFF QUER DIZER DIFERENÇA

dica usar o vscode que ele mostra as diferenças

git diff vendas.html
esse 'vendas.html' é o nome do arquivo que você quer ver a diferença, o que aconteceu com esse arquivo.

obs da pra consultar esse diff pelo vscode, fica ate melhor pra ver, basta ir no simbolo de compartilhar que fica do lado esquerdo da tela e depois em 'changes'.
entao da pra ver o que eu fiz desde o último commit até o momento de agora. fica em verde o que fiz de novo.


### GIT CHECKOUT
### vamos usar bastante! os meus arquivos são modificados temporariamente para voltar do jeito que estava antes, mas tem que colocar o código para onde você quer modificar.

git checkout f225...
faz o comando e coloca o código que deseja que ele volte para aquele commit anterior.
isso é bom se você apagou arquivos ou tinha modificado errado depois. daí ele pode voltar para a posição que desejar.

OBS atenção!!! QUANDO DER O GIT CHECKOUT NÃO É PARA MEXER AGORA NOS ARQUIVOS, NÃO ALTERAR ELES AQUI. não alterar o commit que esta abaixo do head. não é uma boa prática isso. esse git checkout é só para ver mesmo o código no commit anterior. mas caso fez alguma mudança, então usar os comandos abaixo para desfazer as mudanças:
git reset
git clean -df
git checkout -- .
esse é um checkout para limpar modificações que fez de forma equivocada.

git checkout main
obs quando a gente volta, mas depois quer retornar para o mais recente commit feito.

git checkout HEAD~1
estou voltando para o penúltimo commit.
esse '~1' que na verdade é um '~N' ele indica que pode voltar n commits.


### CODIGO DO COMMIT, HEAD

cada commit la no github tem um código. se dermos o comando no gitbash, o comando git log, da pra ver esse codigo de cada commit.
o ultimo commit feito, ele vem com o 'HEAD -> MAIN' significa que é o último commit feito ou seja esta nas cabeças.

OBS o comando git log --oneline ele lista todos os históricos na ordem, porém em 1 linha cada.


### ARQUIVO .GITIGNORE

é um arquivo que indica o que não deve ser salvo pelo git. exemplo arquivos de log, arquivos compilados, arquivos de bibliotecas externas usadas no projeto, arquivos de configuração da IDE, arquivos de configuração do sistema.

no caso então o que eu não quero salvar no git, eu tenho que colocar o .gitignore

esse arquivo fica salvo na pasta principal do repositório. 

mas dá para salvar outros arquivos .gitignore em outras subpastas.


****************************************************
## REMOVENDO ARQUIVOS DA AREA DE STAGE

git status
é sempre bom dar esse comando antes pra ver como esta 

git reset


### COMO DESFAZER MODIFICACOES NAO SALVAS
### VOCÊ APAGA AS MODIFICACOES DESDE O ULTIMO COMMIT

git status

git reset
nesse caso para tirar do stage as ultimas alteracoes

git clean -df

git checkout -- .
agora sim depois desses comandos ele voltou para o que estava antes, posso ir la no programa que vai estar do jeito que estava antes, ele reparou.


### O QUE FAZER QUANDO ABRE O EDITOR VIM
### é o editor básico do linux, ele funciona sem ter uma interface gráfica. 
### ele também esta presente no gitbash.


i
habilita para escrever dentro do vim
posso escrever o que quiser agora, pois é a msg que vem no -m "..." do commit que eu não completei antes, por isso abre esse editor vim do linux.

ESC
wq
ENTER
primeiro aperta o esc, e depois digita o wq. isso é pra salvar o commit

ESC
q!
ENTER
aqui ele não salva as alterações do commit que deixei incompleto, ele sai da tela mesmo do vim.


### DELETANDO O ÚLTIMO COMMIT SEM DELETAR MODIFICAÇÕES NO ARQUIVO
### DESFAZER O ÚLTIMO COMMIT
### nesse caso eu quero desfazer o último commit que acabei de fazer, porque eu esqueci de fazer alguma coisinha nos arquivos. então vou desfazer esse commit, mas sem mexer nas modificações que fiz no arquivo. dai agora sim, vou fazer um novo commit com as alterações que desejo.

git status

git reset --soft HEAD~1
vou dar o reset pra voltar para o útimo commit, mas vou dar o soft para não apagar as modificações.
ou seja vou voltar um commit mas sem apagar as modificações (SOFT)


### OBS A DIFERENÇA DESSE COMANDO ACIMA, PARA O COMANDO QUE VEREMOS A SEGUIR É QUE UM TEM A PALAVRA ' SOFT ' E O OUTRO TEM A PALAVRA ' HARD '


### DELETAR COMMITS E AS MODIFICAÇÕES NOS ARQUIVOS
### É DELETAR UM COMMMIT E AS ALTERAÇÕES POSTERIORES A ESSE COMMIT

git status

git reset --hard <codigo do commit>
pode colocar o código do commit aqui, e vai deletar tudo que foi feito depois desse commit! muita atenção aqui ok!
ele volta o projeto para esse commit então
está ' --hard ' então vou apagar commits e arquivos após esse código de commit que vamos colocar


obs ** AÇÃO DESTRUTIVA!!! **

exemplo:
git status
git reset --hard HEAD~1
vai destruir o ultimo commit e vai voltar para o penultimo commit

obs interessante é que nos comandos acima, ele mexe no stage e no commit, mas não mexe com o que já esta salvo
la no github.

obs se você se arrependeu de apagar algum commit local, e quer trazer de volta o que já está no github, então usa o comando
git pull origin main


### SE QUISER TRAZER TUDO QUE ESTA NO GITHUB PARA O SEU COMPUTADOR NOVAMENTE

git pull origin main
esse comando busca os arquivos que já estão salvos no github


### COMO ATUALIZAR O REPOSITÓRIO LOCAL EM RELAÇÃO AO REPOSITÓRIO REMOTO

git status

git pull <nome remoto> <nome da branch>

exemplo
git pull origin main
com esse comando ele vai trazer o que esta no remoto para o local
obs quando tem um histórico um pouco maior no github do que o local, então só fazer esse comando


### COMO RESOLVER UM PUSH REJEITADO
### É UM PROBLEMA COMUM
### NÃO É PERMITIDO ENVIAR UM PUSH SE O SEU REPOSITÓRIO LOCAL ESTA ATRASADO EM RELAÇÃO AO REMOTO
### O QUE FAZER? TENHO QUE ATUALIZAR O REPOSITÓRIO LOCAL 

git status

git log --online
vai mostrar todos os commits do projeto

git pull <nome do remoto> <nome do branch>
vai buscar no repositório e trazer para o local

exemplo
git pull origin main
vai trazer o histórico do github para o local
pode ser que abra o vim, o editor do linux. porque eu tentei fazer um commit, só que tem arquivos a mais lá no remoto
ESC
:wq
comando acima vai sair do modo edição do vim, e vai salvar o ''MERGE'' que é quando junta os dois históricos

git log --online
aparece a ordem que foi feitos os commits e como agora eu estou repeitando a ordem...

git push 
agora ele vai fazer o push para o remoto

obs nesse exemplo acima, o merge é o 'mesclar' os 2 commits, ou seja juntou o commit remoto com o commit local
obs nesse exemplo acima foi mais facil porque cada histórico mexeu em arquivos diferentes, por exemplo um mexeu no readme e o outro mexeu no vendas por exemplo


### RESOLVENDO PULL COM CONFLITO
### QUANDO QUE OCORRE UM CONFLITO ? É QUANDO VOCÊ VAI MESCLAR DOIS HISTÓRICOS DIFERENTES, MAS NO MESMO ARQUIVO. QUAL O HISTÓRICO QUE VALE ENTÃO?
### AQUI O QUE MUDA EM RELAÇÃO AO EXEMPLO ANTERIOR, É QUE AGORA AS MEXIDAS SÃO DENTRO DO MESMO ARQUIVO

no exemplo, vamos no arquivo vendas dentro do github e vamos editar o valor para 6mil.
agora vamos abrir nosso projeto que ja estava no vscode, e vamos no arquivo vendas e vamos colocar 7mil.
vamos fazer um git pull então só que dá CONFLICT (CONTENT) MERGE CONFLICT IN VENDAS
significa que deu conflito, pq tanto no github quanto no local ambos mexeram no mesmo arquivo vendas.
obs se reparar na proxima linha do git bash aparece no final da linha um (MAIN | MERGING)
eu to no meio do processo de merging
git status
ele vai mostrar que teve mudança no mesmo arquivo, então agora você pode ir no código e fazer o ajuste, pois o gitbash acabou de te avisar que o mesmo arquivo teve dois históricos diferentes
entao no vscode ele compara os 2 históricos, o do local que fiz e o do github que fiz la no github, daí em diante você acerta no vscode mesmo no código qual deseja manter e qual apagar, mas o vscode te sinaliza isso.
git status
git add .
git commit -m "Update vendas"
git push
agora o push vai dar certo! e o MAIN MERGING que fica no final da linha vai sair e vai ficar somente MAIN
git log --oneline
ele traz em 1 linha todos os históricos de modificação do projeto


### COMO SOBRESCREVER UM HISTÓRICO NO GITHUB
### SE EU QUISER IGNORAR O HISTÓRICO RECENTE QUE ESTA NO GITHUB, VAMOS DIZER QUE VOLTEI A TRABALHAR NO MEU PROJETO LOCAL HOJE, E IGNOREI A ALTERAÇÃO QUE ALGUEM FEZ NO PROJETO ONTEM, SÓ VOU CONSIDERAR O HISTÓRICO NOVO QUE TRABALHEI HOJE NA MINHA MÁQUINA

git push -f <nbome do remote> <nome do branch>
esse f é pra forçar meu histórico local para ir na marra por cima mesmo la para o github
git reset --hard <numero do commit>
exemplo:
git reset --hard 9081399
ele vai voltar no seu local, para esse commit ai que é bem mais antigo
git log --oneline
exibe o histórico
git push -f 
agora sim ele vai forçar e vai jogar para o github o projeto do jeito que esta no meu local, vai passar por cima de tudo que esta la no github

obs tem que tomar cuidado com esse ' -f ' que usamos, porque ele força mesmo, nesse caso ele vai destruir tudo que tem depois desse commit la no github, ou seja ele deleta todo o histórico a mais que tem lá no github! ATENÇÃO !!


### COMO APONTAR O PROJETO PARA OUTRO REPOSITÓRIO REMOTO
### ESSA DÚVIDA EU TIVE DESDE QUE COMECEI A USAR O GIT E GITHUB

git remote set-url origin git@git hub.com: .... 
esse codigo todo acima, copiamos ele do site github quando acabamos de criar um repositório lá
a diferença é que vamos trocar aqui a palavra add, pelas palavras set-url
ou seja eu não quero adicionar ao origin, mas sim eu quero trocar o repositório, quero que meu projeto vá para outro repositório
o que fizemos é trocar o local para onde vai o projeto, agora ele vai para o novo repositório que criamos láno github.
git remote -v
via mostrar que o projeto aponta para outro repositório que é o que acabei de criar direto lá no github novo
git push -u origin main
pra jogar o projeto lá para o github dentro do repositório novo

*******************************************
## BRANCHES E TRABALHO EM EQUIPE

para trabalhar com mais de um branch. 
dividir o histórico do mesmo projeto em mais de uma linha de histórico.


### ADICIONAR COLABORADORES AO REPOSITÓRIO REMOTO

Não posso fazer um push no projeto dos outros.

Projetos públicos no Github podem ser lidos, baixados, clonados, forkados por qualquer pessoa.

Por padrão outros usuários não tem permissão de escrita no seu repositório remoto.

Para adicionar colaboradores ao projeto, ir no site do GitHub, e depois em 'Configurações' e depois em 'Colaboradores'.
obs Sempre pede novamente a sua senha
Depois de adicionado um colaborador, a partir de agora, esse colaborador pode fazer push no projeto.


### INTRODUÇÃO AOS BRANCHES

Aprender a trabalhar com os branches.
O branch principal do projeto é a branch main.

Um branch novo, seria criar uma nova linha no tempo, a partir de um dado ponto na linha existente, onde pode salvar um outro histórico que vai seguir a linha dele.
Ou seja, a partir de certo ponto eu posso abrir uma nova branch.
A partir de uma nova feature esse projeto vai ter uma nova branch, esse pode ser um exemplo. Nova feature é uma nova característica, nova funcionalidade.

É possivel por exemplo a partir do mesmo ponto da branch main, abrir outras branches com features novas.
Nesse caso então, teríamos a branch main que é a principal, e depois outras duas branches que seriam a branch ft-login e a branch ft-pedido.

git checkout ft-login
com esse comando o git muda o histórico e os arquivos e vai para a branch ft-login.

git checkout main
e nesse comando o git muda o histórico e os arquivos e vai para a branch main

Obs Dessa forma é fácil mudar entre as visões do projeto. Consigo mudar da branch main, para a branch ft-login ou então para a branch ft-pedido.


### MANIPULANDO BRANCHES LOCALMENTE

git branches
esse comando vai listar as branches que existem

git branch nome-do-branch
esse comando vai criar uma nova branch

git branch -d nome-do-branch
esse comando vai deletar a branch (Ação Destrutiva!!)

git branch -D nome-do-branch
esse comando vai deletar a branch mesmo sem ter feito merge dele ainda (Ação Destrutiva!)
obs esse comando tem o 'D' em maiúsculo, diferente do comando anterior.

** exemplo:
Supor que estou desenvolvendo agora uma nova feature sobre login no projeto que já existe.
Então não posso desenvolver essa nova feature direto na branch main! Atenção! 
Tenho que abrir uma nova branch. 
git branch ft-login
com o comando eu criei uma nova branch
git branch
com o comando eu peço para listar as branchs
git checkout ft-login
esse comando troca para a branch ft-login, e sai da branch main
obs. observar que no final da linha do gitbash ja aparece a branch(ft-login).
obs. então tudo que eu fizer nesse projeto a partir de agora, eu vou começar a salvar dentro dessa branch ft-login, e não mais na branch main.
obs. então a branch main continua com os commits que ela já tinha, e a partir de agora o que eu salvar como commit vai para a branch ft-login.
obs. conforme vou fazendo git add . e git commit na branch ft-login, essas mudanças ficam salvas somente nessa branch, ainda não foram para a branch main.

obs. as branchs são totalmente isoladas uma da outra.

obs se eu tentar deletar a branch ft-login nesse momento, com o comando git branch -d ft-login, ele mostra que a branch não fez merge ainda, ele não esta mesclado ainda. Isso ocorre porque eu ainda não salvei isso no main, não mesclei.
Então tenho que usar o comando git branch -D ft-login
esse comando vai deletar direto a branch ft-login, ele nem me pergunta, simplesmente apaga, mesmo ainda não ter sido feito o merge.
se eu usar o git branch agora para listar as branchs, ele mostra somente a branch main, pois eu apaguei a branch ft-login.
obs caso eu já tenha feito o commit novo dentro da nova branch ft-login que criei, então tenho que apagar os commits novos com o comando git reset --soft HEAD~1
agora é apagado o útimo commit, mas mantém os arquivos na area de stage. 
então  consigo trocar de branch, com o comando git checkout main, para trocar para a branch main.
e por fim consigo apagar a branch ft-login com o comando git branch -D ft-login.


## MERGE FAST FORWARD

A operação Merge serve para mesclar o histórico de um branch de origem para um branch de destino.

Para mesclar usamos o comando 'merge'. Nesse exemplo vamos juntar a branch ft-login que foi criada a parte, com a branch principal main.

Merge fast forward é o merge que não temos problemas de conflito. Quer dizer 'avançar'.
É assim, tem um branch main, e no final dele você cria uma branch ft-login, e depois essa branch é mesclada com a branch main que é a principal.

O comando 'git pull' pode ser entendido como uma 'merge' entre o repositório remoto para o repositório local. Você traz o que esta no remoto para o seu projeto local. é praticamente uma mescla. é uma mesclagem das branchs, da branch remoto com a branch local.

O comando 'merge' deve ser feito a partir da branch de DESTINO.

** OBS O procedimento correto é fazer um merge do branch main para o branch de feature, e não o contrário. 
** Nesse exemplo eu faço o comando git merge dentro do main ok  !!

Obs Quando abandonar uma branch pra trabalhar em outra branch, é sempre bom ver no gitbash se esta tudo salvo, as alterações.

Exemplo:
git branch ft-login
crio a branch ft-login que é a branch de feature
git checkout ft-login
mudo para essa branch
<<<<<<< HEAD
obs posso usar o comando opcional aqui de já criar a branch nova e já mudar para ela, uso então 'git branch -b ft-login' , aqui usamos o '-b' para ele mudar direto para a branch nova que foi criada agora. faz tudo em um único comando.
git branch main
esse comando vai mudar para a branch main
=======
obs posso usar o comando opcional aqui de já criar a branch nova e já mudar para ela, uso então 'git checkout -b ft-login' , aqui usamos o '-b' para  mudar direto para a branch nova que foi criada agora. faz tudo em um único comando.
git status
git add .
git commit -m "Criado formulario"
git log --oneline
esse comando exibe em 1 linha as alterações no projeto e suas branchs
>>>>>>> ft-login











































































