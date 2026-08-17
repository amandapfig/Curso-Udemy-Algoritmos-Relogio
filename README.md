# Relógio Digital com Python e Tkinter

## Sobre o projeto

Este projeto consiste em um **relógio digital desenvolvido em Python**, utilizando a biblioteca **Tkinter** para criar a interface gráfica.

O objetivo principal foi desenvolver uma aplicação simples capaz de exibir o **horário atual do computador em tempo real**, atualizando automaticamente os valores de hora, minuto e segundo.

O projeto foi desenvolvido como parte dos estudos de **Algoritmos e Lógica de Programação com Python 3**, colocando em prática conceitos como funções, importação de bibliotecas, atualização de informações, criação de interfaces gráficas e manipulação de elementos visuais.

---

## Funcionalidades

O relógio possui as seguintes funcionalidades:

* Exibe o horário atual do computador.
* Mostra horas, minutos e segundos.
* Atualiza automaticamente a cada segundo.
* Possui uma interface gráfica simples.
* Utiliza uma fonte grande para facilitar a visualização.
* Possui fundo preto.
* Utiliza uma cor azul/ciano para o horário.
* Permanece funcionando continuamente enquanto a janela estiver aberta.

O horário é apresentado no formato:

```text
HH:MM:SS
```

Por exemplo:

```text
19:30:45
```

---

## Tecnologias utilizadas

### Python 3

A linguagem principal utilizada no desenvolvimento do projeto foi o **Python 3**.

Python foi escolhido por possuir uma sintaxe simples e permitir o desenvolvimento de aplicações gráficas através de bibliotecas como o Tkinter.

### Tkinter

O **Tkinter** é uma biblioteca padrão do Python utilizada para criação de interfaces gráficas.

Neste projeto, ele foi utilizado para:

* Criar a janela principal.
* Criar o elemento que exibe o horário.
* Definir fonte e tamanho do texto.
* Definir cores.
* Posicionar o relógio na janela.
* Atualizar o conteúdo exibido.

### Time

Também foi utilizado o módulo `time` do Python, especificamente a função `strftime()`.

Ela permite obter e formatar informações relacionadas ao horário atual.

---

## Estrutura do projeto

A estrutura básica do projeto é:

```text
Relogio_Curso/
│
├── app.py
│
└── README.md
```

### `app.py`

É o arquivo principal da aplicação.

Nele estão todos os comandos responsáveis por criar a janela, configurar o relógio e atualizar o horário.

### `README.md`

Este arquivo contém a documentação do projeto, explicando seu objetivo, funcionamento, tecnologias utilizadas e instruções para execução.

---

## Como o código funciona

O programa começa importando as bibliotecas necessárias:

```python
from tkinter import *
from tkinter.ttk import *
from time import strftime
```

O `tkinter` fornece os recursos necessários para criar a interface gráfica.

O `strftime` é utilizado para obter o horário atual e formatá-lo.

---

## Criação da janela

A janela principal é criada através do comando:

```python
root = Tk()
```

Depois, o título da janela é definido:

```python
root.title("Relógio")
```

Dessa forma, o nome **"Relógio"** aparece na barra de título da aplicação.

---

## Função do relógio

A principal parte do projeto está na função `relogio()`:

```python
def relogio():
    horario = strftime("%H:%M:%S")
    label.config(text=horario)
    label.after(1000, relogio)
```

Essa função é responsável por atualizar o horário continuamente.

### Obtendo o horário

```python
horario = strftime("%H:%M:%S")
```

O `strftime()` recebe o formato:

* `%H` → hora no formato de 00 a 23.
* `%M` → minutos.
* `%S` → segundos.

Assim, o horário fica no formato:

```text
HH:MM:SS
```

---

## Atualização do texto

Depois de obter o horário atual, o programa utiliza:

```python
label.config(text=horario)
```

Esse comando altera o texto que aparece no elemento `Label`.

A cada atualização, o horário exibido na tela é substituído pelo horário atual.

---

## Atualização automática

A linha:

```python
label.after(1000, relogio)
```

é responsável por executar novamente a função depois de **1000 milissegundos**, ou seja, **1 segundo**.

Isso faz com que o relógio seja atualizado continuamente.

O funcionamento pode ser representado assim:

```text
Obtém o horário
       ↓
Atualiza o Label
       ↓
Espera 1 segundo
       ↓
Executa novamente
       ↓
Obtém o novo horário
       ↓
Atualiza o Label
       ↓
Repete continuamente
```

---

## Configuração visual

O elemento responsável por mostrar o horário é criado com:

```python
label = Label(
    root,
    font=("Helvetica", 60),
    background="#000",
    foreground="#0FF0F4"
)
```

Foram configurados alguns aspectos visuais.

### Fonte

```python
font=("Helvetica", 60)
```

Define a fonte como **Helvetica** e o tamanho como **60**.

Isso deixa o horário grande e fácil de visualizar.

### Cor de fundo

```python
background="#000"
```

Define o fundo como preto.

### Cor do texto

```python
foreground="#0FF0F4"
```

Define a cor do horário como um tom de azul/ciano.

---

## Posicionamento

O comando:

```python
label.pack(anchor="center")
```

adiciona o `Label` à janela e posiciona o conteúdo no centro.

---

## Inicialização do relógio

Depois de criar todos os elementos, a função é chamada:

```python
relogio()
```

Isso faz com que o horário seja exibido imediatamente.

Por fim:

```python
mainloop()
```

mantém a janela aberta e permite que o Tkinter continue processando os eventos e atualizações da interface.

---

## Fluxo completo da aplicação

O funcionamento do programa pode ser resumido da seguinte maneira:

```text
Início
  ↓
Importação das bibliotecas
  ↓
Criação da janela
  ↓
Configuração do título
  ↓
Criação do Label
  ↓
Configuração da aparência
  ↓
Função relogio()
  ↓
Obtém o horário atual
  ↓
Exibe o horário
  ↓
Aguarda 1 segundo
  ↓
Atualiza novamente
  ↓
Repete enquanto o programa estiver aberto
```

---

## Como executar o projeto

### 1. Instalar o Python

É necessário possuir o **Python 3** instalado no computador.

Para verificar se o Python está instalado, abra o terminal e execute:

```bash
python --version
```

ou:

```bash
python3 --version
```

---

### 2. Clonar o repositório

Para baixar o projeto utilizando Git:

```bash
git clone https://github.com/amandapfig/Curso-Udemy---Algoritmos-jogo-da-forca-.git
```

Depois, entre na pasta:

```bash
cd Curso-Udemy---Algoritmos-jogo-da-forca-
```

---

### 3. Executar o programa

Execute:

```bash
python app.py
```

Uma janela será aberta exibindo o relógio digital.

---

## Conceitos de programação utilizados

Apesar de ser um projeto simples, ele permite praticar diversos conceitos importantes de programação:

* Importação de bibliotecas.
* Funções.
* Variáveis.
* Manipulação de strings.
* Formatação de informações.
* Interfaces gráficas.
* Eventos e atualização de interface.
* Estruturas de repetição através de chamadas agendadas.
* Organização de código.
* Uso de módulos do Python.

---

## O que foi aprendido

Durante o desenvolvimento deste projeto, foram praticados conceitos importantes de **Python e lógica de programação**.

Um dos principais aprendizados foi entender como uma aplicação pode obter informações do sistema e apresentá-las em uma interface gráfica.

Também foi possível compreender como o método `after()` do Tkinter pode ser utilizado para executar uma função novamente após determinado intervalo de tempo, permitindo criar a atualização contínua do relógio sem precisar utilizar um loop infinito que poderia travar a interface.

Além disso, o projeto ajudou a praticar a criação e configuração de elementos gráficos utilizando o Tkinter.

---

## Possíveis melhorias futuras

O projeto pode ser expandido futuramente com novas funcionalidades, como:

* Adicionar a data atual.
* Permitir escolher diferentes fontes.
* Criar opções para alterar as cores.
* Adicionar modo claro e escuro.
* Permitir alterar o tamanho do relógio.
* Criar diferentes estilos de relógio.
* Adicionar suporte para diferentes formatos de horário.
* Criar uma tela de configurações.
* Adicionar uma animação visual.
* Criar um despertador.
* Adicionar cronômetro.
* Adicionar temporizador.

---

## Autor

**Amanda**

Projeto desenvolvido durante os estudos de **Algoritmos e Lógica de Programação com Python 3**.

O projeto tem como objetivo colocar em prática os conhecimentos adquiridos durante o curso e desenvolver uma aplicação simples utilizando Python e Tkinter.

---

## Licença

Este projeto foi desenvolvido para fins **educacionais e de aprendizado**.
