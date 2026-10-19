<div align="center">

# CardLab

### Um fundo. Todas as células.

**Editor de cards em lote, direto no navegador.**  
Importe um fundo, posicione logos e informações, associe os dados automaticamente e exporte um PNG para cada célula.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Sem backend](https://img.shields.io/badge/Backend-n%C3%A3o%20necess%C3%A1rio-37664B?style=flat-square)
![Responsivo](https://img.shields.io/badge/Layout-responsivo-37664B?style=flat-square)

</div>

## Sobre o projeto

O **CardLab** foi criado para automatizar uma tarefa recorrente: produzir vários cards de divulgação de células a partir da mesma arte-base. Em vez de editar cada card manualmente, você define uma única vez onde entram a logo e as informações, importa os arquivos e gera as artes em lote.

A aplicação é desenvolvida em **HTML, CSS e JavaScript puro**, sem framework, instalação ou servidor. O processamento dos arquivos ocorre no próprio navegador.

## Prévia

![Interface do CardLab no computador](docs/screenshots/desktop.png)

<details>
<summary>Ver versão para celular</summary>

<br>

<img src="docs/screenshots/mobile.png" alt="Interface responsiva do CardLab no celular" width="320">

</details>

## Funcionalidades

- **Arte de fundo personalizada:** upload de PNG, JPG ou WEBP, com prévia instantânea.
- **Posicionamento visual:** arraste a logo e o bloco de informações, com mouse ou toque; também é possível ajustar as coordenadas em porcentagem.
- **Formatos de logo:** escolha entre **redonda** e **quadrada** e entre mostrar a imagem inteira ou preencher a área com recorte.
- **Tipografia configurável:** fontes, tamanhos e pesos independentes para dia/horário e endereço, além de cor e posição do texto.
- **Importação em lote:** carregue uma pasta contendo imagens e arquivos de informações, inclusive subpastas.
- **Associação automática:** a aplicação relaciona a logo às informações pelo nome, ignorando diferenças de letras maiúsculas, acentos e alguns termos comuns no nome do arquivo.
- **Múltiplos formatos de dados:** lista única em TXT, TXT individual por célula, CSV, JSON ou lista colada no editor.
- **Gerenciamento de células:** pesquisa, seleção, prévia e edição de informações individuais antes da exportação.
- **Exportação:** download do card selecionado em **PNG** ou de todos os cards em um **ZIP**, na resolução original do fundo.
- **Modelos reutilizáveis:** salve posições, formato da logo e configurações dos textos no navegador para usar novamente.
- **Layout responsivo:** interface adaptada para computadores e celulares.

## Como executar

**Pré-requisitos:** um navegador atualizado, como Chrome ou Edge. Não é necessário instalar Node.js, pacotes ou banco de dados.

1. Baixe ou clone este repositório.
2. Abra o arquivo `index.html` no navegador.
3. Pronto: o CardLab já pode ser utilizado.

Também existe a versão autônoma `cardlab-abrir-direto.html`, que reúne HTML, CSS e JavaScript em um único arquivo.

```bash
git clone https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git
cd SEU-REPOSITORIO
```

> Substitua `SEU-USUARIO/SEU-REPOSITORIO` pelo endereço real do seu repositório. Os exemplos de importação estão na pasta `exemplos/`.

## Fluxo de uso

1. **Escolha o fundo:** envie a imagem base, sem a logo nem as informações da célula.
2. **Configure a logo:** escolha o formato, o encaixe, o tamanho e a posição sobre a prévia.
3. **Configure os textos:** defina o local das informações, as fontes, os tamanhos, os pesos e a cor.
4. **Importe as células:** selecione as logos e os dados, juntos ou separadamente, ou cole uma lista no campo apropriado.
5. **Revise:** confira as associações automáticas e ajuste manualmente eventuais informações.
6. **Exporte:** baixe um PNG individual ou todos os cards em um ZIP.

> O posicionamento e a formatação escolhidos são compartilhados pelos cards do lote. Já os dados (nome, encontro e endereço) são específicos de cada célula.

## Como organizar os arquivos

### Opção 1 — Pasta completa

Selecione **Importar pasta completa** e indique uma pasta com imagens e textos:

```text
minhas-celulas/
├── logos/
│   ├── Testemunhas.png
│   ├── A Fonte.png
│   └── Ancora.png
└── informacoes/
    ├── Testemunhas.txt
    ├── A Fonte.txt
    └── Âncora.txt
```

O CardLab associa, por exemplo, `Ancora.png` a `Âncora.txt`, mesmo com diferença de acentuação.

### Opção 2 — Uma lista única (`Células.txt`)

Também é possível importar **um TXT com todas as células**. Cada bloco deve ter três linhas: **nome**, **dia e horário** e **endereço**, com uma linha em branco entre as células.

```text
Testemunhas
Sábado às 15:00
Rua Exemplo, 70 - Bairro

A Fonte
Quinta às 19:30
Rua das Flores, 105 - Centro

Ainda Há Lugar
Sexta às 19:30
Avenida Principal, 40 - Bairro
```

Use **Importar TXT / CSV / JSON** ou cole o conteúdo na opção **Colar lista de células**. A lista pode ser importada antes ou depois das logos; os cards são montados quando uma logo correspondente estiver disponível.

### Opção 3 — Um TXT por célula

O nome do arquivo pode servir de identificação. São aceitos tanto textos simples quanto campos identificados.

**`Testemunhas.txt`**

```text
Testemunhas
Sábado às 15:00
Rua Exemplo, 70 - Bairro
```

**`A Fonte.txt`** (formato com campos)

```text
nome: A Fonte
encontro: Quinta às 19:30
endereco: Rua das Flores, 105 - Centro
```

Se o TXT individual tiver somente as linhas de encontro e endereço, o CardLab pode usar o nome do arquivo para identificar a célula.

### Opção 4 — CSV ou JSON

**CSV** (separador `;` ou `,`, com cabeçalho):

```csv
celula;dia;horario;endereco
Testemunhas;Sábado;15:00;Rua Exemplo, 70 - Bairro
A Fonte;Quinta;19:30;Rua das Flores, 105 - Centro
```

**JSON** (lista de objetos):

```json
[
  {
    "nome": "Testemunhas",
    "encontro": "Sábado às 15:00",
    "endereco": "Rua Exemplo, 70 - Bairro"
  },
  {
    "nome": "A Fonte",
    "encontro": "Quinta às 19:30",
    "endereco": "Rua das Flores, 105 - Centro"
  }
]
```

## Estrutura do projeto

```text
CardLab/
├── index.html                  # Interface da aplicação
├── style.css                   # Layout, estilos e responsividade
├── script.js                   # Importação, editor, prévia e exportação
├── cardlab-abrir-direto.html   # Versão em arquivo único
├── README.md                   # Documentação do repositório
├── LEIA-ME.txt                 # Instruções adicionais de uso
├── docs/
│   └── screenshots/
│       ├── desktop.png
│       └── mobile.png
└── exemplos/
    ├── fundo-raizes-da-comunidade.png
    ├── logos/
    ├── informacoes/
    ├── lista-unica/
    └── pasta-pronta/
```

## Como funciona tecnicamente

- **File API e seleção de pastas:** leitura das imagens e informações fornecidas pelo usuário.
- **JavaScript:** interpretação dos dados e associação por nomes normalizados.
- **Canvas API:** composição do fundo, da logo e dos textos na resolução original da arte.
- **Blob e geração de ZIP no navegador:** criação dos downloads sem depender de um backend.
- **`localStorage`:** armazenamento local das configurações de layout salvas pelo usuário.

A aplicação **não envia as imagens ou os dados das células para um servidor**. As fontes opcionais Barlow Condensed e DM Sans são carregadas do Google Fonts quando há conexão; sem internet, o navegador utiliza fontes de fallback.

## Publicar no GitHub Pages

Por ser um projeto estático, o CardLab pode ser publicado diretamente no GitHub Pages:

1. Envie os arquivos para a raiz do repositório, mantendo o `index.html` na raiz.
2. No GitHub, acesse **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**.
4. Selecione a branch `main` e a pasta `/ (root)` e salve.
5. Quando a publicação terminar, acesse o endereço informado pelo GitHub.

Não é necessário configurar build ou backend. O upload de pastas completas depende do suporte do navegador ao seletor de diretórios; em celulares que não o oferecem, use os seletores de arquivos ou cole a lista de células.

## Observações

- O formato redondo ou quadrado da logo vale para todo o lote.
- Somente células com logo importada geram cards, mesmo quando há mais registros no TXT.
- Dados ausentes ou marcados como **“Vai Atualizar”** são sinalizados antes da exportação, e o usuário decide se deseja continuar.
- O modelo salvo é local ao navegador e não equivale a salvar as imagens e os cadastros.
- Imagens muito grandes ou muitos cards de uma vez podem exigir mais memória do dispositivo.
- Antes de tornar o repositório público, revise os arquivos de exemplo para não expor endereços ou informações que não devam ser publicados.

## Licença

Este repositório ainda **não inclui um arquivo de licença**. Defina e adicione um `LICENSE` caso deseje estabelecer permissões explícitas de uso, modificação e distribuição.

---

<div align="center">

**CardLab** · Criação em lote, sem complicação.

</div>
