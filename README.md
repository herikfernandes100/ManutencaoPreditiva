# Manutenção Preditiva

Projeto de exploração e preparação de dados para análise de manutenção preditiva em máquinas industriais.

O projeto utiliza dados de sensores, como temperatura, velocidade de rotação, torque e desgaste da ferramenta, para investigar a ocorrência de falhas (`Target`).

## Objetivos

- Conhecer e explorar o conjunto de dados;
- verificar dimensões, tipos, valores ausentes e estatísticas descritivas;
- analisar a distribuição da variável-alvo;
- preparar os dados para uma futura etapa de modelagem;
- separar as variáveis preditoras (`X`) do alvo (`y`).

## Estrutura do projeto

```text
ManutencaoPreditiva/
├── data/
│   └── raw/
│       └── predictive_maintenance.csv
├── notebooks/
│   ├── 01_exploracao.ipynb
│   └── 02_preprocessamento.ipynb
├── README.md
└── requeriments.txt
```

## Tecnologias e requisitos

- Python 3.9 ou superior;
- Jupyter Notebook ou Visual Studio Code com a extensão Jupyter;
- pandas;
- NumPy;
- Matplotlib;
- ipykernel.

## Como executar

### 1. Clone o repositório

```bash
git clone <URL_DO_REPOSITORIO>
cd ManutencaoPreditiva
```

### 2. Crie um ambiente virtual

No Windows PowerShell:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
```

No Linux ou macOS:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Instale as dependências

```bash
python -m pip install --upgrade pip
pip install -r requeriments.txt
```

Caso prefira instalar manualmente:

```bash
pip install pandas numpy matplotlib jupyter ipykernel
```

### 4. Abra e execute os notebooks

No VS Code:

1. Abra a pasta do projeto;
2. abra o arquivo `notebooks/01_exploracao.ipynb`;
3. selecione o interpretador/kernel da `.venv`;
4. execute as células em ordem ou use **Run All**;
5. repita o processo com `notebooks/02_preprocessamento.ipynb`.

Também é possível iniciar o Jupyter pelo terminal:

```bash
jupyter notebook
```

Em seguida, abra a pasta `notebooks` e execute os arquivos na ordem indicada.

## Etapas do projeto

### Exploração

O notebook `01_exploracao.ipynb`:

- carrega o arquivo CSV;
- exibe as primeiras linhas;
- verifica o tamanho e os tipos das colunas;
- identifica valores ausentes;
- calcula estatísticas descritivas;
- lista as colunas disponíveis;
- apresenta a distribuição da variável `Target`.

### Pré-processamento

O notebook `02_preprocessamento.ipynb`:

- remove as colunas identificadoras `UDI` e `Product ID`;
- remove `Failure Type` da base usada na preparação;
- transforma `Type` (`L`, `M`, `H`) em valores numéricos;
- separa as variáveis de entrada `X` da variável-alvo `y`;
- normaliza as variáveis de entrada pelo intervalo mínimo-máximo;
- converte `X` e `y` para arrays NumPy.

## Sobre os dados

O conjunto contém informações de máquinas e sensores industriais. Entre as principais colunas estão:

| Coluna | Descrição |
| --- | --- |
| `Type` | Tipo da máquina: `L`, `M` ou `H` |
| `Air temperature [K]` | Temperatura do ar em Kelvin |
| `Process temperature [K]` | Temperatura do processo em Kelvin |
| `Rotational speed [rpm]` | Velocidade de rotação |
| `Torque [Nm]` | Torque aplicado |
| `Tool wear [min]` | Desgaste da ferramenta em minutos |
| `Target` | Indicador de ocorrência de falha |
| `Failure Type` | Tipo de falha registrada |

O arquivo original está em `data/raw/predictive_maintenance.csv`.

## Próximos passos

- avaliar o balanceamento das classes;
- dividir os dados em treino e teste;
- treinar modelos de classificação;
- comparar métricas de desempenho;
- analisar quais sensores mais contribuem para a previsão de falhas.

## Status

Em desenvolvimento: exploração e pré-processamento concluídos como etapa inicial do projeto.
