# Sobre-Linux

Repositório Criado com a iniciativa de conter exemplos de comandos linux para consultas futuras

> Comandos Linux são sensitive Case

## Comandos Monstrado Em Curso Alura e Testes

```bash

pwd - mostra o diretório atual
echo - Imprime na Tela um ou mais paramentros
nano - abre,edita o arquivo
vi - um editor de texto no terminal {
    tecla i = entra em modo de edicao esc para sair
    tecla x = apaga um caractere
    tecla dd = apaga uma linha inteiro
    tecla G = vai para a ultima linha {
        para ir pra primeira linha 0G
        para navegar entre as linha numero_da_linha + G
        para ir pro final da linha atual $
        para ir pro inicio da linha atual 0
    }
    tecla / = tecla usanda para buscar um termo ex /buscav
    tecla n and N = para mudar para a proxima ocorrencia buscada com /
    tecla yy para copiar uma linha
    tecla p para colar
    :w salva
    :q sai
    :wq salva e sai
    :q! sai e não salva
}
> - cria um arquivo
>> - adciona se o arquivo existir concatena
cat - abre o arquivo no terminal {
    cat -n texto.txt = monstra o arquivo e o numero de linha desse arquivo
}
gedit - abre o arquivo para edição se não passar o arquivo ele abre o bloco de notas em branco e se o arquivo nao existir ele cria
clear ou ctrl + L - limpa o terminal
ls -l - monstra mais informações sobre arquivos e diretorios
ls -la - monstra todas as informações sobre arquivos e diretorios visiveis e ocultos
ls * - monstra as pastas dentro do diretorio e o que tem dentro de cada diretorio
whoami - nome do usuario no linux
cd - change directory = mudar de diretorio
mkdir - cria um novo repositorio
rmdir - exclui um directorio
rm - exclui um arquivo
rm -r - apaga recursivamente um diretorio e consequentemente tudo dentro
cp - cria uma copia do arquivo ex cp mensagem.txt bemvindo.txt
cp -r - cria uma copia de um diretorio
mv - move e renomea um arquivo ex de renomeação mv mensagem.txt bemvindo2.txt
zip - para compactar um arquivo ex zip work.zip workspace/ - primeiro paramentro é o nome do zip segundo é a pasta que quer compactar
zip -r compacta de forma recursiva geralmente usando para um diretorio
unzip - descompacta
unzip -l visualiza o que tem dentro de um zip
unzip -q descompacta sem mostrar log de informações
tar - serve para compactar e desconpactar{
    compactar - tar -cz workspace > work.tar.gz
    descompactar - tar -xz < work.tar.gz

    compactar - tar -czf work.tar.gz workspace
    desconpactar tar -xzf work.tar.gz

    compactar - tar -cjf work.tar.bz2 workspace/
    descompactar tar -xjf work.tar.bz2
}

touch - apenas toca o arquivo para mudar a data da sua uttima atualização
date - apresenta a data tem varios paramentro com formatos de datas diferentes, date --help ex- date "+%d/%m/%Y"
head - monstra apenas o inicio de um texto ex head -n 3 google.txt
tail - monstra apenas o final de um texto ex tail -n 3 google.txt
less - abre e te dá a possibilidade de usar as setas do teclado ex less google.txt

```

## Parte 2 de Comandos Linux -

```bash
ps - comandos exibe os progressos sistema
ps -e - exibe todos os processos
ps -ef - exibe varias outras informações dos processos
ps -ef | grep + termo pesquisado - comando usado para buscar um processo
grep - em geral o grep pode ser usado para buscar outras coisas como um termo em um arquivo sempre precedido por |
kill - comando que mata um processo ex kill + pid {
    kill -STOP 11163 - para um processo
    kill -CONT 11163 - continua um processo
    kill -TERM 11269 - termina o processo sem força-lo de forma suave
    kill -9 11364 - mata o processos imediatamente
}
killall + paramentro ex killall top
top - comando para monstar os processos da cpu
top -u - monstra os processos de um determinado usuario ex - top -u lucas
pstree - monstra os processos em arvore de processos
jobs - monstra os trabalhos que estão rodando no bash
bg - comando usando para jogar os processos que estão rodando no bash para background
fg - para trazer os processos para foreground que é o contrario de background
para abrir um processo direto no backgroud eu chamo o processo e coloco o & na frente ex: firefox &
sh - comando bash serve para executar um script
permissoẽs linux {
    r = ler
    w = escrever
    x = executar
    d = diretorio
}
chmod {
    definição - troca as permissões de arquivos para usuario/grupo ou para qualquer usuario ex adicionando uma permissao chmod + x ex retirando uma permissão chmod -x

    trocando permissões {
        - para grupo ex - chmod g-xr pedro
        - para usuario ex - chmod u-xr pedro
        - para outros ex - chmod o-xr pedro
    }

} 

~ - representa o diretorio o de usuario
locate - busca arquivos ou programas em todo a extensão de hd
updatedb - faz uma atualização no banco de dados inteno de sistema para atualizar a busca com locate ex: sudo updatedb
which - procura qual é o arquivo que eu vou executar se eu digitar nesse comando ex witch firefox
sudo - comando que vai na frente de um comando no qual eu quero executar com adm
passwd - comando para mudar a senha de usuario 
sudo passwd - troca a senha de usuario root 
su root - para fazer login como root 
adduser - comando para add um usuriario ex: adduser pedro
env - monstra as variaveis de ambiente
PATH - {
    add um novo diretorio ao PATH d.o Sistema
    PATH=$PATH: + diretorio ou pasta ex PATH=$PATH:/home/guilherme/workspace

    cofigurar PATH em .bashrc 
}

wc -w - conta o numero de paravras que tem dentro de um arquivo
total de processos - ps -e | wc -l
apt - gerenciador de pacotes
apt-cache search - busca progremas para instalar 
sudo apt-get remove - comando para remover um arquivo
dpkg {
    - .deb 
    instalando programa ex sudo dpkg -i + arquvivo
    removendo programa ex sudo dpkg -r + nome do pacote
}

service {
    -comando para parar ou startar um programa sem matar ele 
    ex - sudo service + serviço + stop
    exemplo pratico - sudo service vsftpd stop
    exemplo pratico - sudo service vsftpd start  
    /etc/init.d - programas que serão executados ao iniciar a maquina
}

instalar-programa-atraves-script {
    1- extrair o arquivo .tar.gz ex tar -xzf arquivo.tar.gz
    2 - abrir o diretorio e se tiver um script configure executa-lo
    3 - dar o comando make para buildar o programa e verificar se está tudo certo nas dependencia 
    4 - dar o comando sudo make install para instalar o programa
}

ssh {
    instalar como cliente o ssh
        sudo apt-get install ssh-client
    instalar como server o ssh
        sudo apt-get install ssh-server
    instalr como cliente e servidor ssh
        sudo apt-get install ssh

    conectando remotamente com ssh
        ssh nomeDoUsuario@ip ex ssh jose@localhost
    
    conectando com ssh em modo grafico 
        ssh -x nomeDoUsario@ip ex ssh -x jose@localhost

    copiando arquivos para maquina remota
        scp nomeDoArquivo nomeDoUsario@ip:Diretorio 
        ex scp -r  work.zip jose@localhost:~/
}
# usermod -aG sudo hpoyatos - adcionando sudo ao usuario hypoyatos no sistema


```

SOUACADEMY20

## Inicio

```bash

man - Comando de Manual para comandos ex: "man ls"
su - superusuário root
sudo apt update ou sudo apt-get update- Atualiza a refência dos repositórios baixando a lista de pacotes disponiveis para download com versões mais atualizadas
sudo apt upgrade ou sudo apt-get upgrade - exibe a lista de pacotes que estão atualizados e pergunta para o usuario se quer atualizar
apt search - busca por pacotes ex apt search trezor ou sudo apt search trezor
sudo apt install - instala pacotes de programas

```

## EXERCICIOS PRATICOS PART I

**1**. Utilize o comando necessário para exibir, no terminal, a mensagem "Bem vindo ao curso de Linux da Alura".
   Agora escreva a mensagem acima em um arquivo chamado bemvindo.txt, utilizando o comando necessário. Aproveite para verificar se o arquivo foi criado, utilizando o comando ls.

**2**. Dentro do diretório Desktop do seu usuário, utilize o comando echo para criar o arquivo musicas-favoritas.txt, com a palavra "Faithless".

Execute o comando necessário para escrever a palavra "REM" no arquivo musicas-favoritas.txt de forma que o conteúdo antigo do arquivo seja mantido.

Utilize o cat para verificar se o conteúdo do arquivo está correto.

**3**. Crie um diretório chamado workspace dentro do diretório base do usuário. Acesse o diretório workspace.

Dentro da pasta workspace, aproveite para criar as pastas: projetos-java e projetos-php.

Crie também os arquivos: arquivo1.txt, arquivo2.txt e arquivo3.txt, todos com o conteúdo: "meu primeiro teste".

Por fim, retorne para o diretório em que workspace se encontra.

**4**. Crie um novo arquivo dentro do diretório workspace: Execute o comando necessário para ler todos os arquivos que contenham apenas um caractere após o nome "arquivo" e antes da extensão ".txt".

**5**. Execute o comando necessário para excluir o arquivo arquivo3.txt. E se quisermos excluir o diretório workspace, como podemos fazer? Execute o comando necessário.

**6**. Crie novamente a pasta workspace dentro do diretório base do usuário.

Dentro do diretório workspace, crie um arquivo chamado mensagem.txt com a mensagem "bem vindo". Copie o arquivo mensagem.txt para o arquivo bemvindo.txt.

Aproveite para renomear o arquivo mensagem.txt para bemvindo2.txt.

Crie agora, dentro de workspace os subdiretórios projetos-java e projetos-php.

Mova o arquivo bemvindo.txt para o diretório projetos-java, mantendo o mesmo nome. Após mover, copie agora o bemvindo2.txt para o arquivo bemvindo.txt.

Por fim, copie o diretório projetos-java para o diretório projetos-c#.

**7**. Liste os arquivos que começam com o nome bemvindo, dentro de workspace.

Execute apenas o comando ls e depois execute ls \*. Reflita sobre as diferenças entre eles.

**8**. Vamos agora sair do diretório workspace e trabalhar no seu diretório pai, que é o diretório base do usuário: Utilize o comando necessário para compactar todos os arquivos e diretórios que estão dentro de workspace para o arquivo work.zip.

Por fim, remova o diretório workspace e descompacte o arquivo work.zip.

**9**. Como visto no capítulo, crie um arquivo chamado google.txt dentro do seu diretório workspace. Acesse o artigo da Wikipedia sobre o Google: https://en.wikipedia.org/wiki/Google. Copie uma parte significativa do texto e cole no arquivo google.txt.

**10**. Vamos agora utilizar o vi e abrir o arquivo google.txt:
    Na segunda linha do arquivo, insira o seguinte texto: Da wikipedia, Da wikipedia, a enciclopédia aberta Apague o texto "Da wikipedia, ". Faça isso com um único comando. Por fim, remova a linha que você acabou de inserir, salve as alterações e saia do editor.

**11**. Vamos agora utilizar o vi e abrir o arquivo google.txt: Utilize o comando necessário para navegar até a linha 30. Pesquise pelo termo "Yahoo!". Navegue nas ocorrências, utilizando também o comando necessário para voltar até uma ocorrência anterior.

**12**. Vamos agora utilizar o vi e abrir o arquivo google.txt: Copie as três primeiras linhas do arquivo, salte para a linha 40 do arquivo e cole cinco vezes o conteúdo que foi copiado.

## EXERCICIOS PRATICOS PART II

**1**. Abra o navegador web Firefox. Agora faça o que é necessário para que no terminal você consiga listar apenas os processos que tiverem ligação com o programa firefox.

**2**. Abra algum programa do seu Linux, como o navegador web firefox ou o editor gedit.

Execute o comando necessário, passando as informações que ele necessita para encerrar o processo do programa de uma forma que ele consiga decidir se será realmente encerrado.

Abra novamente o programa e agora utilize o comando necessário para encerrá-lo de forma que você tenha certeza que o programa não irá se recuperar e será de fato encerrado.

**3**. crie um diretório chamado scripts, dentro do diretório do seu usuário. O script realizabackup deverá ser criado dentro desse diretório.

Abra o editor de textos gedit de forma que ele seja executado no background. Crie um arquivo chamado realizabackup. O arquivo deverá ter o seguinte conteúdo:
zip backup.zip -qr ~/workspace/
echo "Backup realizado com sucesso"COPIAR CÓDIGO

Vamos utilizar o comando zip para criar um arquivo compactado. A opção -q, indica que queremos fazer isso de maneira silenciosa, sem imprimir muitas informações no terminal. A opção -r indica que desejamos fazer a operação de forma recursiva, compactando o diretório workspace e subdiretórios também.

O ~ em ~/workspace/ é um atalho para representar o diretório do usuário. Sempre que quisermos nos referir ao diretório do usuário (/home/nome_do_usuario/), podemos utilizar o ~. Dessa forma independente de qual seja o nosso diretório atual, o comando zip saberá onde o diretório workspace se encontra.

Por fim, vamos imprimir uma mensagem informando que o backup foi concluído com sucesso.

Teste o script e veja se o arquivo .zip é gerado da forma correta.

**4**. Utilize o comando necessário para que seja adicionada a permissão de execução ao script realizabackup, fazendo com que ele possa ser executado sem utilizar o comando sh.

Aproveite para testar a execução do script.

Após executar o script, realize um teste: remova a permissão de escrita do arquivo. Tente abrir o script no editor de texto e perceba que se fizer alguma modificação no arquivo, não conseguirá salvar, pois no momento não possui permissão para escrita.









