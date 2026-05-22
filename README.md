# CVLI-MS - Crimes Violentos Letais Intencionais (SEJUSP/MS)

Documentação do repositório para organização, versionamento e análise dos dados públicos de **CVLI - Crimes Violentos Letais Intencionais** do Estado de Mato Grosso do Sul, disponibilizados no Portal de Dados Abertos do Governo de MS.

> **Período de referência:** 2016 a 2026, com 2026 parcial.  
> **Observação do arquivo analisado:** o CSV recebido contém registros de **01/01/2016 a 28/04/2026**. Portanto, embora a coleta/documentação esteja marcada como parcial de maio de 2026, não foram identificados registros datados de maio no arquivo local analisado.  
> **Total de registros no CSV analisado:** 5.152 ocorrências.  
> **Abrangência territorial:** Mato Grosso do Sul, com 79 municípios identificados.  
> **Unidade federativa:** MS.  
> **Fonte oficial:** Portal de Dados Abertos de Mato Grosso do Sul / SEJUSP-MS.  

---

## 1. Sobre o conjunto de dados

Este repositório armazena e documenta dados de **Crimes Violentos Letais Intencionais (CVLI)** no Mato Grosso do Sul, com informações sobre número/ano da ocorrência, classificação do fato, data, hora, município, código IBGE e bairro.

O objetivo é apoiar análises exploratórias, séries temporais, visualizações geográficas, estudos de segurança pública e projetos de ciência de dados voltados à compreensão da dinâmica territorial e temporal dos crimes letais intencionais no estado.

---

## 2. Fonte dos dados

Página do recurso no Portal de Dados Abertos:

```text
https://www.dados.ms.gov.br/dataset/crimes-violentos-letais-intencionais-sejusp/resource/crimes-violentos-letais-intencionais-sejusp
```

URL base para download pelo datastore:

```text
https://www.dados.ms.gov.br/datastore/dump/crimes-violentos-letais-intencionais-sejusp
```

Formatos indicados pelo portal:

```text
CSV
TSV
JSON
XML
```

Links sugeridos para download direto:

| Formato | URL |
|---|---|
| CSV | `https://www.dados.ms.gov.br/datastore/dump/crimes-violentos-letais-intencionais-sejusp?format=csv` |
| TSV | `https://www.dados.ms.gov.br/datastore/dump/crimes-violentos-letais-intencionais-sejusp?format=tsv` |
| JSON | `https://www.dados.ms.gov.br/datastore/dump/crimes-violentos-letais-intencionais-sejusp?format=json` |
| XML | `https://www.dados.ms.gov.br/datastore/dump/crimes-violentos-letais-intencionais-sejusp?format=xml` |

---

## 3. Metadados do recurso

| Campo | Valor |
|---|---|
| Título | CVLI - Crimes Violentos Letais Intencionais |
| Órgão/Fonte | SEJUSP/MS - Secretaria de Estado de Justiça e Segurança Pública de Mato Grosso do Sul |
| Portal | Dados Abertos MS |
| Identificador do recurso | `crimes-violentos-letais-intencionais-sejusp` |
| Formato principal | CSV |
| Datastore ativo | Sim |
| Visualizações no portal | Não há visões criadas para o recurso |
| Licença informada | Nenhuma licença fornecida |
| Data de criação indicada no portal | 18/08/2025 |
| Última atualização dos dados indicada no portal | 18/08/2025 |
| Última atualização dos metadados indicada no portal | 29/04/2026 |
| Data da consulta/documentação | 21/05/2026 |

> **Nota:** recomenda-se verificar periodicamente a página oficial, pois o metadado de atualização pode não refletir integralmente os registros mais recentes presentes no arquivo baixado.

---

## 4. Escopo temporal do arquivo analisado

| Ano | Registros |
|---:|---:|
| 2016 | 628 |
| 2017 | 584 |
| 2018 | 498 |
| 2019 | 455 |
| 2020 | 478 |
| 2021 | 486 |
| 2022 | 490 |
| 2023 | 466 |
| 2024 | 452 |
| 2025 | 468 |
| 2026 | 147 |

Resumo temporal:

```text
Data mínima identificada: 01/01/2016
Data máxima identificada: 28/04/2026
Ano de 2026: parcial
Registros em 2026 no arquivo analisado: 147
```

Distribuição parcial de 2026 no arquivo analisado:

| Mês de 2026 | Registros |
|---:|---:|
| Janeiro | 41 |
| Fevereiro | 26 |
| Março | 46 |
| Abril | 34 |
| Maio | 0 |

---

## 5. Estrutura sugerida do repositório

```text
cvli-ms/
├── README.md
├── LICENSE
├── data/
│   ├── raw/
│   │   ├── crimes_violentos_letais_intencionais_sejusp_ms.csv
│   │   ├── crimes_violentos_letais_intencionais_sejusp_ms.tsv
│   │   ├── crimes_violentos_letais_intencionais_sejusp_ms.json
│   │   └── crimes_violentos_letais_intencionais_sejusp_ms.xml
│   ├── processed/
│   │   ├── cvli_ms_normalizado.csv
│   │   └── cvli_ms_por_ano_municipio.csv
│   └── dictionary/
│       └── dicionario_dados_cvli_ms.csv
├── notebooks/
│   └── 01_analise_exploratoria_cvli_ms.ipynb
├── scripts/
│   ├── download_data.py
│   ├── convert_formats.py
│   └── validate_schema.py
├── outputs/
│   ├── figures/
│   ├── tables/
│   └── reports/
└── docs/
    └── fonte_portal_dados_abertos_ms.pdf
```

---

## 6. Dicionário de dados

| Coluna | Tipo no portal | Descrição |
|---|---|---|
| `_id` | inteiro | Identificador sequencial do registro no datastore. |
| `Nº/ANO` | texto | Número e ano da ocorrência/procedimento, geralmente acompanhado da unidade policial. |
| `FATO` | texto | Descrição jurídica ou administrativa do fato registrado. |
| `FATO AGRUPADO` | texto | Classificação agrupada do fato, incluindo categorias analíticas associadas a CVLI. |
| `DATA DO FATO` | texto/data | Data da ocorrência. Recomenda-se converter para formato `datetime`. |
| `HORA DO FATO` | texto/hora | Hora registrada da ocorrência. |
| `UF` | texto | Unidade federativa. No arquivo analisado, todos os registros pertencem a `MS`. |
| `MUNICÍPIO` | texto | Município de ocorrência do fato. |
| `CÓDIGO IBGE` | texto/inteiro | Código IBGE do município. Recomenda-se tratar como texto para preservar integridade. |
| `BAIRRO` | texto | Bairro informado no registro. Pode conter valores ausentes. |

---

## 7. Qualidade e observações sobre os dados

Principais observações do CSV analisado:

- O arquivo possui **5.152 registros** e **10 colunas originais**.
- A coluna `BAIRRO` possui **1.348 valores ausentes**, aproximadamente **26.16%** do total.
- Foram identificados **79 municípios** e **737 bairros** preenchidos.
- A coluna `UF` possui apenas o valor `MS`.
- As colunas de data e hora são fornecidas como texto e devem ser normalizadas antes da análise.
- A coluna `FATO` possui descrições extensas, compostas e com variações textuais; recomenda-se padronização para análises agregadas.
- A coluna `FATO AGRUPADO` pode conter múltiplas categorias concatenadas; recomenda-se tratamento específico caso seja usada para classificação.

---

## 8. Como baixar os dados com Python

```python
import pandas as pd

url = "https://www.dados.ms.gov.br/datastore/dump/crimes-violentos-letais-intencionais-sejusp?format=csv"

df = pd.read_csv(url, dtype=str)

df.to_csv(
    "data/raw/crimes_violentos_letais_intencionais_sejusp_ms.csv",
    index=False,
    encoding="utf-8-sig"
)

print(df.shape)
print(df.head())
```

---

## 9. Como converter para CSV, TSV, JSON e XML

```python
import pandas as pd
from pathlib import Path

input_file = Path("data/raw/crimes_violentos_letais_intencionais_sejusp_ms.csv")
output_dir = Path("data/raw")
output_dir.mkdir(parents=True, exist_ok=True)

df = pd.read_csv(input_file, dtype=str)

df.to_csv(output_dir / "crimes_violentos_letais_intencionais_sejusp_ms.csv", index=False, encoding="utf-8-sig")
df.to_csv(output_dir / "crimes_violentos_letais_intencionais_sejusp_ms.tsv", index=False, sep="\t", encoding="utf-8-sig")
df.to_json(output_dir / "crimes_violentos_letais_intencionais_sejusp_ms.json", orient="records", force_ascii=False, indent=2)
df.to_xml(output_dir / "crimes_violentos_letais_intencionais_sejusp_ms.xml", index=False, root_name="cvli_ms", row_name="registro")
```

---

## 10. Normalização mínima recomendada

```python
import pandas as pd

df = pd.read_csv(
    "data/raw/crimes_violentos_letais_intencionais_sejusp_ms.csv",
    dtype=str
)

df.columns = (
    df.columns
    .str.strip()
    .str.lower()
    .str.normalize("NFKD")
    .str.encode("ascii", errors="ignore")
    .str.decode("utf-8")
    .str.replace(" ", "_")
    .str.replace("/", "_")
)

df["data_do_fato"] = pd.to_datetime(df["data_do_fato"], format="%d/%m/%Y", errors="coerce")
df["ano"] = df["data_do_fato"].dt.year
df["mes"] = df["data_do_fato"].dt.month
df["dia"] = df["data_do_fato"].dt.day

df["municipio"] = df["municipio"].str.strip().str.upper()
df["bairro"] = df["bairro"].fillna("NAO INFORMADO").str.strip().str.upper()
df["uf"] = df["uf"].str.strip().str.upper()

df.to_csv("data/processed/cvli_ms_normalizado.csv", index=False, encoding="utf-8-sig")
```

---

## 11. Exemplos de análises possíveis

Algumas análises recomendadas para este conjunto de dados:

1. Série histórica anual de CVLI no Mato Grosso do Sul.
2. Distribuição mensal e sazonal das ocorrências.
3. Ranking de municípios com maior número absoluto de registros.
4. Taxa por 100 mil habitantes, quando integrada a dados populacionais do IBGE.
5. Mapa coroplético por município, usando `CÓDIGO IBGE`.
6. Análise de concentração territorial por bairro nos municípios com maior incidência.
7. Comparação entre categorias de `FATO` e `FATO AGRUPADO`.
8. Modelagem temporal para detecção de tendência e sazonalidade.
9. Painéis interativos com filtros por ano, município, fato e bairro.
10. Integração com bases complementares, como população, renda, vulnerabilidade social, policiamento, indicadores educacionais e infraestrutura urbana.

---

## 12. Exemplo de agregação por ano e município

```python
import pandas as pd

df = pd.read_csv("data/processed/cvli_ms_normalizado.csv", dtype=str)
df["data_do_fato"] = pd.to_datetime(df["data_do_fato"], errors="coerce")
df["ano"] = df["data_do_fato"].dt.year

agrupado = (
    df.groupby(["ano", "municipio"], dropna=False)
    .size()
    .reset_index(name="total_cvli")
    .sort_values(["ano", "total_cvli"], ascending=[True, False])
)

agrupado.to_csv("data/processed/cvli_ms_por_ano_municipio.csv", index=False, encoding="utf-8-sig")

print(agrupado.head(20))
```

---

## 13. Exemplo de visualização rápida

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("data/processed/cvli_ms_normalizado.csv")
df["data_do_fato"] = pd.to_datetime(df["data_do_fato"], errors="coerce")
df["ano"] = df["data_do_fato"].dt.year

serie = df.groupby("ano").size()

plt.figure(figsize=(10, 5))
serie.plot(kind="bar")
plt.title("CVLI por ano - Mato Grosso do Sul")
plt.xlabel("Ano")
plt.ylabel("Número de registros")
plt.tight_layout()
plt.show()
```

---

## 14. Cuidados metodológicos

- Os registros representam dados administrativos de segurança pública e podem sofrer revisão, reclassificação ou atualização posterior.
- O ano de 2026 deve ser tratado como **parcial**, não sendo diretamente comparável aos anos fechados.
- O campo `BAIRRO` apresenta ausência relevante de preenchimento; análises intramunicipais devem considerar essa limitação.
- O campo `FATO` contém descrições jurídicas longas e heterogêneas; recomenda-se criar categorias padronizadas antes de aplicar mineração de texto ou aprendizado de máquina.
- Comparações entre municípios devem ser preferencialmente normalizadas por população.
- Para análises espaciais, recomenda-se validar o `CÓDIGO IBGE` com malhas territoriais oficiais do IBGE.
- Como a licença aparece como não informada no portal, recomenda-se verificar as condições de uso antes de redistribuição comercial.

---

## 15. Ética, segurança e LGPD

Este conjunto de dados deve ser utilizado para fins de pesquisa, transparência pública, planejamento de políticas públicas, jornalismo de dados e controle social. Recomenda-se evitar qualquer tentativa de reidentificação de pessoas, vítimas, investigados ou envolvidos, ainda que a base não apresente nomes.

Boas práticas:

- Não publicar dados que possam expor indivíduos ou famílias em nível excessivamente granular.
- Agregar resultados por município, bairro, ano ou mês sempre que possível.
- Evitar inferências discriminatórias sobre territórios ou grupos sociais.
- Contextualizar os resultados com indicadores sociais e demográficos.
- Documentar limitações, ausências e possíveis vieses administrativos da base.

---

## 16. Ferramentas recomendadas

Para análise em Python:

```text
pandas
numpy
matplotlib
plotly
geopandas
folium
scikit-learn
statsmodels
jupyter
openpyxl
pyarrow
```

Para dashboards:

```text
Streamlit
Dash
Power BI
Looker Studio
Metabase
Apache Superset
```

Para dados geográficos:

```text
geopandas
shapely
folium
geobr
contextily
```

---

## 17. Como citar a fonte

Sugestão de citação:

```text
MATO GROSSO DO SUL. Secretaria de Estado de Justiça e Segurança Pública - SEJUSP/MS. 
CVLI - Crimes Violentos Letais Intencionais. Portal de Dados Abertos de Mato Grosso do Sul. 
Disponível em: https://www.dados.ms.gov.br/dataset/crimes-violentos-letais-intencionais-sejusp/resource/crimes-violentos-letais-intencionais-sejusp. 
Acesso em: 21 maio 2026.
```

---

## 18. Status do projeto

```text
[x] Identificação da fonte oficial
[x] Registro dos formatos disponíveis
[x] Leitura do CSV
[x] Documentação do dicionário de dados
[x] Estruturação inicial para GitHub
[ ] Automatização do download
[ ] Conversão versionada para TSV, JSON e XML
[ ] Validação automatizada do schema
[ ] Análise exploratória
[ ] Dashboard
[ ] Integração com população IBGE
```

---

## 19. Licença

A página do recurso informa **"Nenhuma Licença Fornecida"**. Antes de redistribuir, publicar derivações ou utilizar comercialmente, recomenda-se confirmar as condições de uso junto ao Portal de Dados Abertos de Mato Grosso do Sul ou ao órgão responsável.

---

## 20. Responsabilidade

Este repositório não substitui informações oficiais da SEJUSP/MS. Os dados devem ser sempre conferidos com a fonte pública original, especialmente em análises oficiais, relatórios públicos ou estudos comparativos.
