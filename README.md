# Como Montar um README Moderno

Guia prático de estrutura para o arquivo **README** de um projeto — com exemplos de Markdown, quando usar HTML, e como gerar o seu com ajuda de um agente de IA.

## Sumário

- [Por que o README importa](#por-que-o-readme-importa)
- [Markdown básico](#markdown-básico)
- [Estrutura recomendada](#estrutura-recomendada)
  1. [Título e badges](#1-título-e-badges)
  2. [Descrição](#2-descrição)
  3. [Sumário](#3-sumário)
  4. [Demonstração](#4-demonstração)
  5. [Pré-requisitos](#5-pré-requisitos)
  6. [Instalação](#6-instalação)
  7. [Uso](#7-uso)
  8. [Contribuição](#8-contribuição)
  9. [Licença](#9-licença)
- [Quando usar HTML no README](#quando-usar-html-no-readme)
- [Exemplo de uso misto (Markdown + HTML)](#exemplo-de-uso-misto-markdown--html)
- [Monte seu README com IA](#monte-seu-readme-com-ia)
- [Recursos adicionais](#recursos-adicionais)
- [Considerações finais](#considerações-finais)

---

## Por que o README importa

Em um projeto de software, o **README** é mais do que um documento — é a porta de entrada para quem chega pela primeira vez: desenvolvedores avaliando se vale contribuir, usuários tentando instalar, colegas revisando seu trabalho.

No GitHub, o README é a vitrine do projeto. É muitas vezes o primeiro (e às vezes único) contato que alguém tem com o que você construiu, e molda a decisão de se envolver ou não.

Este guia explora uma estrutura técnica, com exemplos práticos em Markdown, para organizar essa vitrine de forma clara e navegável.

## Markdown básico

Markdown é uma linguagem de marcação leve, feita para ser legível mesmo em sua forma bruta — sem a complexidade de HTML puro.

| Recurso | Sintaxe | Resultado |
|---|---|---|
| Títulos | `# H1`, `## H2`, `### H3` | tamanhos de cabeçalho |
| Ênfase | `*itálico*`, `**negrito**` | *itálico*, **negrito** |
| Lista ordenada | `1. Item` | 1. Item |
| Lista não ordenada | `- Item` | - Item |
| Link | `[texto](url)` | link clicável |
| Imagem | `![alt](url)` | imagem embutida |
| Código inline | `` `código` `` | `código` |
| Citação | `> texto` | bloco de citação |

Para um bloco de código com sintaxe destacada, cerque o trecho com três crases e o nome da linguagem:

````markdown
```python
def ola():
    print("olá, mundo")
```
````

Markdown converte direto para HTML, o que o torna a escolha padrão para READMEs, documentação e posts — mas nem tudo precisa (ou deve) ser feito só com ele; veja [Quando usar HTML](#quando-usar-html-no-readme).

## Estrutura recomendada

### 1. Título e badges

O título é a primeira informação que alguém vê — deve ser claro sobre o que o projeto é. Badges (shields.io, por exemplo) comunicam status, versão e licença num relance, sem precisar ler nada.

```markdown
# Nome do Projeto

![versão](https://img.shields.io/badge/versão-1.0-blue)
![licença](https://img.shields.io/badge/licença-MIT-green)
```

### 2. Descrição

Sucinta, mas completa: o que o projeto faz, para quem, e qual problema resolve. Evite ambiguidade.

```markdown
## Descrição

Sistema de controle de LEDs para Arduino Uno. Acende, apaga e ajusta o
brilho via comandos seriais — ideal para projetos educacionais e de
automação básica.
```

### 3. Sumário

Em READMEs longos, um índice com links âncora poupa o leitor de rolar a página inteira.

```markdown
## Sumário

1. [Descrição](#descrição)
2. [Instalação](#instalação)
3. [Uso](#uso)
4. [Licença](#licença)
```

### 4. Demonstração

Uma captura de tela, GIF ou diagrama vale mais que um parágrafo de descrição de UI. É o que mais separa um README "moderno" de um puramente textual.

```markdown
## Demonstração

![demo do projeto](docs/demo.gif)
```

### 5. Pré-requisitos

Liste dependências, versões e ambiente necessários — a clareza aqui evita "na minha máquina funciona".

```markdown
## Pré-requisitos

- IDE Arduino 1.8.13+
- Placa Arduino Uno
- Biblioteca `LiquidCrystal`
- Windows 10 ou Ubuntu 20.04
```

### 6. Instalação

Passo a passo, com comandos copiáveis. Numeração ajuda a seguir em ordem.

````markdown
## Instalação

1. Clone o repositório:
   ```sh
   git clone https://github.com/usuario/projeto.git
   ```
2. Instale as dependências e abra no ambiente indicado nos pré-requisitos.
````

### 7. Uso

Exemplos concretos de como usar o projeto depois de instalado — comandos, trechos de código, ou uma captura de tela do resultado esperado.

### 8. Contribuição

Diretrizes para quem quer colaborar: fluxo de branch, padrão de commit, processo de revisão. Pode apontar para um `CONTRIBUTING.md` separado em projetos maiores.

````markdown
## Contribuição

1. Faça um fork do repositório.
2. Crie uma branch:
   ```sh
   git checkout -b minha-modificacao
   ```
3. Abra um Pull Request descrevendo a mudança.
````

### 9. Licença

Qual licença rege o projeto, e um link para o texto completo.

```markdown
## Licença

Este projeto está sob a licença MIT — veja [LICENSE](LICENSE).
```

## Quando usar HTML no README

Markdown é o padrão, mas HTML embutido ajuda quando você precisa de algo que ele não cobre nativamente:

- **Layouts avançados** — tabelas complexas, colunas lado a lado, alinhamento central.
- **Controle fino de imagem** — largura/altura exatas, alinhamento.
- **Elementos interativos** — um botão estilizado, um badge customizado.

```html
<p align="center">
  <img src="docs/logo.png" alt="Logo do projeto" width="200">
</p>
```

**Cuidados**: nem toda plataforma renderiza HTML embutido do mesmo jeito — teste antes de confiar. HTML também reduz a legibilidade do arquivo em texto puro, e aumenta o custo de manutenção se você usar CSS inline extensivamente. Use com moderação, só onde Markdown puro não resolve.

## Exemplo de uso misto (Markdown + HTML)

```markdown
# Projeto do Aluno X

Bem-vindo ao **Projeto do Aluno X**! Este projeto foi desenvolvido para...

<p align="center">
  <img src="projeto.jpg" alt="Imagem do projeto" width="300">
</p>

## Funcionalidades

1. **Funcionalidade A** — descrição.
2. **Funcionalidade B** — descrição.

| Recurso | Descrição |
|---|---|
| Recurso 1 | Faz XYZ |
| Recurso 2 | Faz ABC |
```

## Monte seu README com IA

Um agente de código como o [Claude Code](https://claude.com/claude-code) consegue montar esse README por você — lendo o próprio repositório (código, dependências, scripts) e preenchendo cada seção deste guia com informação real, em vez de placeholder.

O fluxo típico:

1. Abra o Claude Code (ou outro agente equivalente) na raiz do seu projeto.
2. Peça: *"crie um README seguindo a estrutura de Como-montar-seu-README"*, ou instale a skill abaixo e rode `/readme-builder`.
3. O agente inspeciona o projeto (linguagem, dependências, scripts de instalação, testes), faz as perguntas que só você pode responder (nome, licença, público-alvo), e gera o arquivo já com seções na ordem certa.
4. Revise e ajuste o tom — a IA acerta a estrutura; a voz do projeto continua sendo sua.

### Skill pronta: `readme-builder`

Este repositório inclui uma [Claude Code Skill](https://docs.claude.com/en/docs/claude-code/skills) em [`skills/readme-builder/SKILL.md`](skills/readme-builder/SKILL.md) que aplica exatamente a estrutura deste guia. Para usar no seu próprio projeto:

```sh
mkdir -p .claude/skills
cp -r skills/readme-builder .claude/skills/readme-builder
```

Depois, dentro do Claude Code, invoque com `/readme-builder` (ou peça "monte meu README") — o agente lê o repositório, pergunta o que faltar, e escreve o arquivo seguindo as 9 seções acima.

## Recursos adicionais

- [GitHub Markup](https://github.com/github/markup#github-markup) — a biblioteca que o GitHub usa para renderizar Markdown/outros formatos de marcação.
- [Template de README da Nadia Eghbal](https://github.com/nayafia/contributing-template) — referência clássica, adaptável a qualquer projeto.
- [Shields.io](https://shields.io) — gerador de badges para status, versão, build, licença.
- [Choose a License](https://choosealicense.com) — ajuda a escolher a licença certa para o seu projeto.

## Considerações finais

Um bom README é detalhado o suficiente para alguém começar e contribuir, sem virar um livro. Documentação mais extensa pertence a uma wiki ou pasta `docs/` separada; o README continua enxuto e direto ao ponto.

**Seja conciso.** Informação demais desmotiva a leitura tanto quanto informação de menos deixa dúvida.
