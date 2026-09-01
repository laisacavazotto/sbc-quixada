# Tabelas — Pipeline de triagem e análise da RSL

Cada artigo passa por até 3 etapas, uma tabela por etapa e por base de dados. O número do
artigo (coluna `Artigo` / `n. do estudo`) é o mesmo da lista bruta em `../Listas/` — veja o
README de lá para o retorno inicial de cada base.

Todas as tabelas das 3 etapas têm uma coluna **"Título do Artigo (conforme Lista de
origem)"** logo após o número do artigo, com o texto real da Lista de origem (autores +
título + venue). Isso evita depender só do número (ou de rótulos de citação, que podem
estar desatualizados) para saber a qual estudo uma linha se refere — basta olhar essa
coluna.

## Etapas

1. **`{Base}_InclusaoExclusao*.csv`** — aplica os critérios de inclusão/exclusão a cada
   artigo da Lista, marcando `Incluído` ou `Excluído`. Colunas `a`-`q` marcam qual critério
   levou à decisão — ver mapeamento completo abaixo.
2. **`{Base}_CriteriosQualidade*.csv`** — só para os artigos `Incluído`. Pontua de 0 a 3
   quantos dos temas principais da pesquisa (legibilidade, agência, negociabilidade /
   cidades inteligentes / gestão de dados) o artigo cobre.
3. **`{Base}_Sintese*.csv`** — só para os artigos `Incluído`. Traz a análise qualitativa
   completa do artigo, respondendo QP1-QP5 e QPS1-QPS4. A coluna `Citação (Autor et al.,
   Ano)` traz um rótulo de citação — use a coluna de título para conferir se ele bate com
   o estudo certo (essa coluna se chamava "Artigo" antes, nome corrigido por confundir com
   o próprio artigo).

## Legenda das colunas a-q (Inclusão/Exclusão)

As 17 colunas `a`-`q` correspondem aos critérios de inclusão (CI1-CI8) e exclusão
(CE1-CE9) definidos na dissertação original ("Quem controla seus dados?") e na Tabela de
Critérios de Inclusão e Exclusão do Artigo.tex, na mesma ordem e com os mesmos códigos.

| Col | Código | Critério |
|---|---|---|
| a | CI1 | Propõe, define ou aprimora princípios teóricos/fundamentais da IHD |
| b | CI2 | Formulação ou aplicação prática de *frameworks* baseados nesses princípios |
| c | CI3 | Desenvolvimento, aplicação ou validação de métricas/métodos de avaliação em IHD |
| d | CI4 | Resultados empíricos sobre eficácia/usabilidade de soluções ou *frameworks* de IHD |
| e | CI5 | Modelo teórico validado por evidências concretas (estudo de caso, experimento) |
| f | CI6 | Revisão sistemática/mapeamento com contribuição original ou consolidação teórica |
| g | CI7 | Publicação revisada por pares (conferência indexada ou periódico) |
| h | CI8 | Publicado no período 2014-2024 |
| i | CE1 | Metodologia não replicável / sem descrição clara e rigorosa dos procedimentos |
| j | CE2 | Menção tangencial ou superficial à IHD, sem aprofundar princípios/*frameworks*/métricas |
| k | CE3 | Foco exclusivo em visualização de dados, sem componente ativo de interação humana |
| l | CE4 | Termo/sigla IHD em contexto não correlato (hardware, interação de baixo nível) |
| m | CE5 | Publicado antes de 2014 |
| n | CE6 | Disponível só como resumo expandido/abstract, sem texto completo |
| o | CE7 | Texto integral indisponível gratuitamente (restrito a paywall) |
| p | CE8 | Área médica/clínica estrita, fora do escopo sociotécnico e urbano da pesquisa |
| q | CE9 | Registro duplicado entre bases (mantida só a versão mais completa/prioritária) |

## Arquivos por base

| Base | Inclusão/Exclusão | Critérios de Qualidade | Síntese |
|---|---|---|---|
| Scopus | `Scopus_InclusaoExclusao_parte1..5.csv` | `Scopus_CriteriosQualidade_parte1..3.csv` | `Scopus_Sintese_parte1..3.csv` |
| Science Direct | `ScienceDirect_InclusaoExclusao.csv` | `ScienceDirect_CriteriosQualidade.csv` | `ScienceDirect_Sintese.csv` |
| Portal Periódicos CAPES | `PeriodicosCAPES_InclusaoExclusao.csv` | — (0 incluídos) | — (0 incluídos) |
| Teses CAPES | `TesesCAPES_InclusaoExclusao.csv` | `TesesCAPES_CriteriosQualidade.csv` | `TesesCAPES_Sintese.csv` |
| BDTD-USP | `TesesUSP_InclusaoExclusao.csv` | — (0 incluídos) | — (0 incluídos) |

As tabelas do Scopus são divididas em partes só por tamanho de arquivo — a numeração do
artigo é contínua entre as partes (`parte1` = artigos 1-40, `parte2` = 41-80, etc.), não
reinicia a cada arquivo.

## Estado atual (resumo)

| Base | Incluído | Excluído | Total |
|---|---|---|---|
| Scopus | 81 | 112 | 193 |
| Science Direct | 14 | 38 | 52 |
| Periódicos CAPES | 0 | 14 | 14 |
| Teses CAPES | 3 | 4 | 7 |
| BDTD-USP | 0 | 2 | 2 |
| **Total** | **98** | **170** | **268** |

As contagens de Inclusão/Exclusão, Critérios de Qualidade e Síntese são idênticas para
cada base (auditado — nenhum artigo pontuado/sintetizado que não esteja `Incluído`, e
nenhum `Incluído` sem pontuação/síntese). Toda referência citada no `referencias.bib`
correspondente a um artigo `Incluído` tem entrada verificada.
