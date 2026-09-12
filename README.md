# Proposta de Capítulo 1 do RPAS — projeto LaTeX para Overleaf

Este projeto é uma **proposta/modelo** (template), em português, para o
Capítulo 1 ("A Instalação") de um Relatório Preliminar de Análise de
Segurança (RPAS), no estilo editorial dos documentos do U.S. NRC.

## Como abrir no Overleaf

1. Compacte esta pasta inteira em `.zip` (se ainda não estiver) e faça
   upload em **Overleaf → New Project → Upload Project**.
2. Compilador: **pdfLaTeX** (já é o padrão do Overleaf). O documento usa
   `bibtex` para a bibliografia — o Overleaf detecta isso automaticamente
   pelo `\bibliography{references}` em `main.tex`; não é necessário nenhum
   ajuste manual.
3. Arquivo raiz: `main.tex`.

Se preferir compilar localmente: `pdflatex main`, `bibtex main`,
`pdflatex main`, `pdflatex main` (nessa ordem; duas passagens finais do
pdflatex são necessárias para o índice e as referências cruzadas
assentarem).

## Estrutura de arquivos

```
main.tex                 documento mestre (capa, sumário, capítulo, bibliografia)
sty/nureg-style.sty       estilo visual (numeração de página por capítulo, tabelas
                          em grade, caixas de nota, cabeçalho/rodapé, fonte/espaçamento)
content/capa.tex          página de rosto
content/cap1.tex          conteúdo do Capítulo 1 (Seções 1.1 a 1.8)
content/anexo.tex         dois anexos: (1) metodologia — mapeia cada seção à
                          NUREG-1537, Parte 1 e Parte 2, sinalizando o que é
                          síntese própria; (2) estratégia de licenciamento
                          faseado (escopo inicial limitado ao prédio do
                          reator, deixando as instalações de irradiação para
                          uma fase posterior)
references.bib            bibliografia em BibTeX
figures/                  pasta vazia para as figuras que você for inserindo
                          (plantas, cortes — referenciadas na Seção 1.3)
```

## Do que se trata este documento

* A **estrutura de seções 1.1 a 1.8** segue integralmente a NUREG-1537,
  Parte 1 ("Format and Content") e Parte 2 ("Standard Review Plan and
  Acceptance Criteria") — os dois PDFs que você enviou. Essa norma é
  específica para **reatores não-de-potência** (pesquisa/multipropósito),
  licenciados sob 10 CFR Parte 50.
* O documento é enquadrado como um pedido de **licença de construção**
  (permissão de construção + licença de operação, 10 CFR Parte 50), que
  é exatamente o escopo da NUREG-1537 — essa é a leitura correta para um
  reator não-de-potência/multipropósito como o RMB. A seção sobre
  tópicos de Certificação de Projeto (10 CFR Parte 52) foi removida do
  capítulo — o documento não trata mais dessa via alternativa.
* **Cada seção (1.1–1.8)** traz: o texto corrido em português (estilo
  NUREG/SAR traduzido), uma **tabela de requisitos de aceitação**
  (extraída/adaptada da NUREG-1537, Parte 2), uma **tabela-resumo dos
  pontos mais importantes**, e uma **tabela de apêndices/referências
  cruzadas a verificar**. O texto original em inglês foi removido a
  pedido — ficam em inglês apenas os títulos oficiais dos documentos
  citados entre aspas (ex.: *"Standard Format and Content..."*), porque
  são o nome próprio da publicação, e siglas/termos técnicos sem
  tradução consagrada (NUREG, ITAAC, COL, Tier 1/2/2*, PSAR).
* O documento tem trechos entre colchetes `[...]` — são os pontos a
  preencher com os dados reais da instalação/projeto (nome do
  requerente, potência, tipo de reator, site, etc.). Isso é proposital:
  o pedido foi por uma "proposta" de Capítulo 1, então entreguei um
  modelo completo e pronto para preencher, não um capítulo fictício com
  dados inventados.

## Uma ressalva importante (Seção 1.7)

A Seção 1.7 da NUREG-1537 trata exclusivamente da conformidade com a
*Nuclear Waste Policy Act* de 1982 dos EUA (contrato com o DOE para
destinação de combustível irradiado). **Isso não se aplica, como está
escrito, a um projeto fora dos Estados Unidos.** Deixei isso sinalizado
no próprio documento (caixa "NOTA REGULATÓRIA") e mantive a estrutura
apenas como referência de formato — o conteúdo normativo dessa seção
específica precisa ser reescrito para o arcabouço nacional aplicável
(no Brasil, tipicamente envolvendo a CNEN).

## Escolhas de layout que fiz (sem instrução explícita sua)

* **Numeração de página por capítulo** (1-1, 1-2, ..., 1-13...) — é a
  convenção usada pela própria NUREG-1537 e por FSAR/DCD em geral.
* **Tabelas em grade** (linhas e colunas com bordas completas), mais
  próximas da aparência de tabelas do NRC/DCD do que o estilo minimalista
  (`booktabs`) comum em artigos acadêmicos.
* Fonte serifada estilo Times (`mathptmx`), corpo 14pt (classe `extbook`,
  do pacote `extsizes`, que recalcula corretamente `\small`, `\large`
  etc. para tamanhos fora do padrão 10/11/12pt do `book`), com
  espaçamento de linha maior que o padrão (fator 1,32, via pacote
  `setspace`) para leitura mais confortável em texto corrido longo; uma
  fonte sem serifa (Helvetica-like) é usada para títulos/cabeçalhos —
  combinação comum em relatórios técnicos regulatórios. A página de
  rosto usa espaçamento simples (`\singlespacing`) para caber em uma
  única página. O título "Referências Bibliográficas" usa o mesmo
  estilo de régua+título do banner do Capítulo 1 (grande e em negrito).

Se qualquer uma dessas escolhas não for o que você tinha em mente, é só
pedir o ajuste.

## Compilação verificada

O projeto foi compilado localmente (pdflatex + bibtex, 3 passagens) sem
erros e sem avisos relevantes antes do envio.
