# Eventos Sísmicos

## Origem dos dados

O USGS é uma fonte federal estadunidense primária de informações científicas sobre ecossistemas, uso da terra, recursos energéticos e minerais, riscos naturais, uso e disponibilidade de água, além de mapas e imagens atualizados das características da Terra, disponíveis ao público.

## Forma de Coleta de Dados

Os conjuntos de dados são divulgações de dados associadas a publicações de pesquisa de autores do USGS. Os dados listados na página da web acessada pelo botão à direita não estão associados a nenhuma publicação específica. Em vez disso, são conjuntos de dados associados a vários sistemas de monitoramento de terremotos.

Todos os [contribuidores](https://earthquake.usgs.gov/data/comcat/contributor/) que informam o USGS.

## Tipo de Dados Coletados

Os dados se referem à eventos sísmicos que aconteceram desde de 1960 e foram catalogados em todo o mundo.
Escolhemos apresentar análise sobre terremotos.

## Seleção de Janela de Tempo 

Escolhemos utilizar os dados do dataset utilizando o range de data de novembro de 2015 até atualmente.
Selecionamos também o tipo de evento sísmico, no caso utilizamos os dados de terremotos que aconteceram em todo o planeta.
Escolhemos aplicar estes filtros no dataset por encontrarmos os dados sazonais completos dentro deste range de data e por conseguirmos concentrar a análise e restringir processamento necessário para a manipulação dos dados.

## Forma de Rodar o Projeto

> O projeto foi desenvolvido em ambiente local, utilizando como sistema operacional linux ubuntu 24.04 LTS

### Requisitos Para Rodar o Projeto:

* Linux Ubuntu 24.04 LTS (WSL)
    * Ambiente de desenvolvimento:
        * Python 3.12.3 (Kernel venv)
        * redis-stack-server (instalado e rodando via systemctl)

* Visual Studio Code
    * Extensões:
        * Jupyter
        * WSL

### Rodando o projeto

Ao conectar o Visual Studio ao ambiente Linux via WSL, e clonar o repositório, crie e inicie o ambiente virtual python usando o comando:

``` bash
    python -m venv .venv
    source .venv/bin/activate
    python -m ipykernel install --user --name meu_venv --display-name "Python (meu_venv)"
``` 

Após a etapa de criação de ambiente virtual, no vscode ao abrir e conectar ao WSL, deverá aparecer uma opção de conectar ao kernel gerado com o nome "Python (meu_venv)".

Ao selecionar o kernel, inicie o notebook Jupyter utilizando o botão <button>Run All</button> na barra superior do Visual Studio.

O código irá criar um arquivo sqlite database.db no diretório assets.

Ao criar este diretório sempre que for necessário rodar novamente o notebook pode pular a execução do passo de importação de dados do projeto.

O projeto além do banco de dados local sqlite utiliza um banco de dados em memória, Redis, para utilização de estruturas de dados probabilísticas, no caso, há a implementação de Bloom Filter e MinHash.

