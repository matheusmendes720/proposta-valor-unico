# Proposta de Valor Único — Matheus Mendes C. S. Santos

Documento único de candidatura à vaga de **Analista Administrativo JR (Foco em Financeiro & Operações)**,
**Wilson Sons** — Salvador-BA, presencial, Efetivo (CLT), prazo de candidatura 27/11/2026.

## O que é

Um ficheiro HTML único, autocontido, que um RH lê em 30 segundos e que depois encaminha, com o seu endosso,
à liderança de Operações e de TI. O mesmo ficheiro serve as duas profundidades de leitura.

Ficheiros nesta pasta:

| Ficheiro | O que é |
|---|---|
| `index.html` | O documento. Não depende de nada: sem JavaScript, sem rede, sem fontes externas. |
| `README.md` | Este ficheiro. |

## Como abrir

- **Offline, com duplo clique** em `index.html`. Funciona sem ligação à internet — não há `<script>`, não há
  webfonts, não há CDN, não há imagens externas. Todos os gráficos são SVG inline.
- **Em ecrã**: `Ctrl+P` imprime em A4 retrato, com o tema claro, **mostrando todas as secções** (mesmo que
  o interruptor de leitura esteja no modo "resumo").
- **Tema escuro**: o ficheiro segue a preferência do sistema (`prefers-color-scheme: dark`). Para fixar o tema
  escuro manualmente, acrescente `data-theme="black"` ao elemento `<html>`. O modo fixo nunca afeta a impressão.

## As duas profundidades de leitura

O interruptor no topo do documento é CSS puro, feito com `:target` (sem uma linha de JavaScript):

| Estado | O que aparece |
|---|---|
| **Detalhe para quem decide** (omissão) | Tudo: a camada RH, a ponte, a prova com proveniência, a interpretabilidade, a evolução, o portfólio e as perguntas. |
| **Resumo para o RH** | Fica apenas a capa e a camada RH (blocos *Financeiro · Operações · Regra e Dados* + glossário), com um link de retorno ao documento completo. |

A impressão mostra sempre o estado completo.

## A política de honestidade dos números

Esta é a parte do documento que o candidato não quis simplificar. Cada número declara a sua origem através de
uma **marca de proveniência** visível, com quatro níveis distinguíveis por cor **e** por forma (a cor sozinha
não basta):

| Marca | Significado | Forma |
|---|---|---|
| **medido em operação** | Observado numa operação real em que o trabalho esteve em uso. | Círculo cheio, borda sólida |
| **modelado por análise** | Produzido por um modelo de análise; **não** foi medido em operação. | Círculo meio cheio, borda tracejada |
| **resultado a medir** | A métrica está definida; o número ainda não existe. | Círculo vazio, borda pontilhada |
| **verificado no artefato** | Contagem que qualquer pessoa confere no ficheiro público. | Losango, borda sólida |

Regras aplicadas em todo o documento:

1. **Nenhum número inventado**, nenhum cliente inventado, nenhuma certificação inventada.
2. **Toda afirmação numérica de desempenho, volume, custo ou resultado traz marca.** Datas, anos, nomes próprios,
   identificadores de vaga e prazos de plano não são afirmações de resultado e não levam marca.
3. **Onde um número existe mas não é publicado, a linha diz isso na cara** — em vez de esconder.
4. **Os números do WorkConnect são modelados**, não medidos: são "impacto quantificado por análise de BI num
   capstone académico", e a distinção aparece num painel próprio, não numa nota de rodapé.
5. **A BYD é projeto de portfólio.** Não há contrato, não há cliente, não houve estágio. A frase do resultado
   termina sem número, e o número ausente é declarado como ausente.
6. **"Key User" é o papel da vaga**, não um título que o candidato teve. A página descreve o método que produz o
   mesmo efeito e diz isso explicitamente na capa.

## Estrutura do documento

1. **Capa** — nome, cargo alvo, promessa de uma linha, e o que é um Key User em uma frase.
2. **Leitura em 30 segundos** — três blocos (Financeiro · Operações · Regra e Dados) e o glossário dos termos do
   anúncio, sem sigla por explicar.
3. **A ponte Operações ↔ TI** — o método em cinco passos (Observação → Regra escrita → Automação → Número →
   Decisão), em SVG, com a fronteira desenhada e o retorno que fecha o ciclo.
4. **A prova, com proveniência** — cartões de evidência por organização, com o número e a marca de cada um.
5. **O que o número esconde** — para cada métrica principal: o que está por trás, o que a métrica não capta e
   o que ainda não está provado.
6. **Evolução natural** — linha do tempo de 2017 a 2026, com o eixo *operação → dado → sistema*.
7. **Portfólio** — os artefatos com link e uma linha do que cada um prova.
8. **Perguntas que eu já sei responder** — oito perguntas prováveis, com resposta curta.
9. **Rodapé** — identidade, links e a nota de proveniência do documento.

## Decisões técnicas

- **Um único ficheiro.** `index.html` não carrega nada de fora: zero `<script>`, zero `onclick`, zero
  `<link>`, zero `@import`, zero `url()`, zero `src=`. As únicas URLs são hiperligações `<a href>` para os
  artefatos do portfólio — que só são abertas se o leitor clicar, e não geram qualquer pedido ao abrir o ficheiro.
- **Tipografia de sistema** (Liberation Sans / DejaVu Sans / Arial), para renderizar igual em qualquer máquina.
- **Paleta**: os tokens do pacote de design do candidato (`--paper`, `--ink`, `--muted`, `--soft`, `--rule`,
  `--accent` `#1F4E5F`, `--steel`) e os semânticos (`--teal`, `--amber`, `--coral`, `--blue`, `--green`,
  `--violet`) com variantes `-tint`. Os valores são os do pacote, sem alterações.
  Nota: o pacote usa `--soft` como tom secundário de texto; a superfície dos cartões é o próprio `--paper` com
  filete, e os realces usam os `-tint`. Não foi criado nenhum token fora do conjunto.
- **SVG**: cada SVG redefine os tokens dentro de si próprio, para inverter com a página; as regras escuras ficam
  dentro de `@media screen`, pelo que a impressão sai sempre no tema claro.
- **Impressão**: `@page { size: A4 portrait }`, unidades em mm, `print-color-adjust: exact`, cartões sem quebra
  de página no meio.
- **Acessibilidade**: `header/main/section/footer`, hierarquia `h1`–`h3`, `role="img"` e `aria-label` nos
  três SVG, contraste AA, foco visível e link de salto ao conteúdo.
- **Responsivo**: três pontos de quebra; a linha do tempo e as grades recolhem em ecrã estreito.

## Como publicar em GitHub Pages

A publicação foi deixada de fora deste trabalho de propósito. Quando for feita:

1. Crie um repositório novo (por exemplo `proposta-valor-unico`), **público**.
2. Envie `index.html` e `README.md` para a raiz do repositório.
3. Em **Settings → Pages**, escolha *Deploy from a branch*, branche `main`, pasta `/ (root)`, e salve.
4. A página fica em `https://<utilizador>.github.io/<repositorio>/`.

Não é preciso nenhuma configuração de build: não há etapas de geração, nem dependências, nem ficheiros adicionais.
Para gerar um PDF a partir do documento, basta imprimir para PDF com o navegador (A4 retrato, escalas padrão,
"background graphics" ligado).
