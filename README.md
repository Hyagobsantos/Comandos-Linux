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
gedit - abre o arquivo para edição
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

## Inicio

```bash

man - Comando de Manual para comandos ex: "man ls"
su - superusuário root
sudo apt update ou sudo apt-get update- Atualiza a refência dos repositórios baixando a lista de pacotes disponiveis para download com versões mais atualizadas
sudo apt upgrade ou sudo apt-get upgrade - exibe a lista de pacotes que estão atualizados e pergunta para o usuario se quer atualizar
apt search - busca por pacotes ex apt search trezor ou sudo apt search trezor
sudo apt install - instala pacotes de programas

```
