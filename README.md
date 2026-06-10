# 🌦️ Sistema de Previsão Climática com Dados do INMET

Sistema desenvolvido em **Python** para leitura, processamento e previsão climática utilizando arquivos históricos do **INMET (Instituto Nacional de Meteorologia)**.

O software permite carregar arquivos meteorológicos `.csv`, identificar automaticamente informações da estação meteorológica e realizar consultas por **cidade** e **data futura** através de uma interface gráfica simples.

A previsão é exibida contendo:

* Temperatura prevista
* Umidade prevista
* Pressão atmosférica
* Velocidade do vento
* Probabilidade de chuva
* Correlação dominante
* Método utilizado
* Confiabilidade estimada

---

## 📌 Tecnologias Utilizadas

* Python 3
* Tkinter (Interface gráfica)
* CSV (Leitura de arquivos)
* Datetime (Manipulação de datas)
* OS (Manipulação de diretórios)

### Sem uso de bibliotecas externas

Este projeto **não utiliza bibliotecas de Machine Learning, Estatística ou Álgebra Linear prontas**.

Não são utilizados:

* NumPy
* Pandas
* Scikit-Learn
* TensorFlow
* PyTorch
* StatsModels

Todos os cálculos estatísticos e matemáticos são implementados manualmente.

---

## 📊 Métodos Estatísticos Implementados

* Média
* Mediana
* Moda
* Variância
* Desvio padrão
* Covariância
* Correlação de Pearson
* Cohen's d
* Regressão Linear Simples
* Média Móvel
* Suavização de Tendência
* Cálculo Probabilístico Baseado em Histórico Climático

---

## 🔍 Metodologia de Previsão

A previsão climática combina:

1. Média sazonal histórica
2. Regressão linear manual
3. Média móvel
4. Frequência histórica de chuva
5. Correlação entre umidade e precipitação

---

## 📁 Estrutura do Projeto

```text
Projeto_Machine_Learning
│
├── main.py
├── interface.py
│
├── core
│   ├── parser.py
│   ├── engine.py
│   ├── probability.py
│   ├── regression.py
│   ├── statistics.py
│   ├── geo.py
│   └── graphs.py
│
└── data
    └── uploads
        ├── arquivo_inmet_1.csv
        ├── arquivo_inmet_2.csv
        └── arquivo_inmet_3.csv
```

---

## 📄 Formato dos Arquivos Aceitos

O sistema aceita arquivos:

```text
.csv
```

Os arquivos devem seguir o padrão de exportação do INMET contendo informações como:

* Estação
* Código da estação
* UF
* Região
* Latitude
* Longitude
* Altitude
* Data
* Hora UTC
* Precipitação
* Pressão
* Temperatura
* Umidade
* Vento
* Radiação

### Exemplo de arquivo válido

```text
INMET_S_RS_B846_NONOAI_01-01-2026_A_30-04-2026.CSV
```

Extensões aceitas:

```text
.CSV
.csv
```

---

## 📂 Onde Colocar os Arquivos CSV

Os arquivos do INMET devem ser colocados em:

```text
data/uploads
```

Exemplo:

```text
Projeto_Machine_Learning/data/uploads/INMET_S_RS_B846_NONOAI_01-01-2026_A_30-04-2026.CSV
```

Caso a pasta não exista, o sistema tentará criá-la automaticamente.

---

## 📦 Dependências

O projeto utiliza apenas bibliotecas padrão do Python.

```python
os
csv
json
datetime
tkinter
unicodedata
```

---

## 🖥️ Verificando o Tkinter

Para verificar se o Tkinter está disponível:

```bash
python -m tkinter
```

Se abrir uma janela de teste, está tudo funcionando corretamente.

---

## 🚀 Instalação

### 1. Instale o Python

Download:

```text
https://www.python.org/downloads/
```

Durante a instalação, marque:

```text
Add Python to PATH
```

### 2. Clone ou Baixe o Projeto

```text
C:\Users\SeuUsuario\Desktop\Projeto_Machine_Learning
```

### 3. Crie a Pasta de Uploads

```text
Projeto_Machine_Learning/data/uploads
```

### 4. Adicione os Arquivos do INMET

Copie os arquivos `.csv` para:

```text
data/uploads
```

---

## ▶️ Como Executar

Abra o terminal na pasta do projeto:

```bash
cd C:\Users\SeuUsuario\Desktop\Projeto_Machine_Learning
```

Execute:

```bash
python main.py
```

Ou:

```bash
C:\Users\SeuUsuario\AppData\Local\Python\python.exe main.py
```

---

## 🧭 Como Utilizar

Ao iniciar o sistema será exibida uma interface gráfica contendo:

* Cidade
* Data futura
* Resultado da previsão

### Exemplo

```text
Cidade: NONOAI
Data futura: 2027-06-15
```

Clique em:

```text
Consultar previsão
```

---

## 📈 Exemplo de Resultado

```text
Local consultado:
NONOAI/RS

Estação meteorológica:
B846

Região climática:
S

Data prevista:
2027-06-15

Temperatura média prevista:
18.7 °C

Umidade prevista:
82.3 %

Pressão atmosférica prevista:
951.2 mB

Velocidade do vento prevista:
2.1 m/s

Probabilidade de chuva:
47.5 %

Correlação dominante:
umidade x precipitacao = 0.63

Método utilizado:
regressao_linear_manual + media_movel + frequencia_historica

Confiabilidade estimada:
68.4 %
```

---

## ⚠️ Cidade Não Encontrada

Caso a cidade informada não seja encontrada:

```text
Nenhum arquivo correspondente à cidade informada foi encontrado.
```

Um aviso também será exibido na interface gráfica.

---

## 📌 Observações Sobre a Previsão

A previsão é baseada exclusivamente nos dados históricos disponíveis.

A qualidade dos resultados depende de:

* Quantidade de dados disponíveis
* Número de anos analisados
* Integridade dos registros
* Ausência de falhas no CSV
* Representatividade da estação meteorológica

### Recomendações

Para obter previsões mais confiáveis:

* Utilizar vários anos de dados
* Utilizar múltiplas estações próximas
* Evitar arquivos com grandes lacunas
* Utilizar registros completos de temperatura, umidade, pressão e precipitação

---

## ⚠️ Limitações

O sistema não consulta dados online.

Todo o processamento é realizado exclusivamente a partir dos arquivos locais armazenados em:

```text
data/uploads
```

Além disso, por requisito do projeto, não são utilizadas bibliotecas externas de Machine Learning ou Estatística.

---

## ⚡ Execução Rápida

```bash
cd Projeto_Machine_Learning

mkdir data\uploads

python main.py
```

Copie os arquivos do INMET para:

```text
data/uploads
```

Depois:

1. Execute o sistema
2. Informe a cidade desejada
3. Informe uma data futura
4. Clique em **Consultar previsão**

---

## 📜 Licença

Este projeto pode ser utilizado para fins acadêmicos, educacionais e de pesquisa climática.

Sinta-se à vontade para adaptar, modificar e expandir a solução conforme suas necessidades.
