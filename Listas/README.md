# Listas — Retorno bruto das buscas

Cada arquivo `.txt` contém a lista numerada de artigos retornados diretamente por uma
base de dados, antes da aplicação dos critérios de inclusão/exclusão (CI/CE). O número
de cada entrada — `(1)`, `(2)`, `(3)`... — é o identificador do artigo naquela base, usado
para referenciá-lo nas tabelas de `../Tabelas/`.

| Arquivo | Base de dados | Nº de artigos |
|---|---|---|
| `Scopus_Lista_Artigos.txt` | Scopus | 193 |
| `ScienceDirect_Lista_Artigos.txt` | Science Direct | 52 |
| `PeriodicosCAPES_Lista_Artigos.txt` | Portal de Periódicos CAPES | 14 |
| `TesesCAPES_Lista_Teses.txt` | Catálogo de Teses CAPES | 7 |
| `TesesUSP_Lista_Teses.txt` | BDTD-USP | 2 |
| `Lista de Strings.txt` | — | *strings* de busca usadas em cada base (citado no Artigo.tex) |

## Como rastrear um artigo

O número do artigo aqui (ex.: Scopus `#17`) é o mesmo número usado como chave em:

- `../Tabelas/{Base}_InclusaoExclusao*.csv` — decisão de inclusão/exclusão
- `../Tabelas/{Base}_CriteriosQualidade*.csv` — pontuação de qualidade (só para os Incluído)
- `../Tabelas/{Base}_Sintese*.csv` — análise por Questão de Pesquisa (só para os Incluído)

Bases grandes (Scopus) têm as tabelas de destino divididas em `_parte1`, `_parte2`... por
tamanho de arquivo — a numeração do artigo continua a mesma entre as partes, não reinicia.
