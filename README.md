# Sistema-de-Previs-o-Clim-tica-com-Dados-do-INMET
Sistema desenvolvido em Python para leitura, processamento e previsão climática utilizando arquivos históricos do INMET (Instituto Nacional de Meteorologia).

O software permite carregar arquivos meteorológicos .csv, identificar automaticamente informações da estação meteorológica e realizar consultas por cidade e data futura através de uma interface gráfica simples.

A previsão é exibida em um painel contendo:

Temperatura prevista;
Umidade prevista;
Pressão atmosférica;
Velocidade do vento;
Probabilidade de chuva;
Correlação dominante;
Método utilizado;
Confiabilidade estimada.
📌 Tecnologias Utilizadas
Python 3
Tkinter (Interface gráfica)
CSV (Leitura de arquivos)
Datetime (Manipulação de datas)
OS (Manipulação de diretórios)
Sem uso de bibliotecas externas

Este projeto não utiliza bibliotecas de Machine Learning, Estatística ou Álgebra Linear prontas.

Não são utilizados:

NumPy
Pandas
Scikit-Learn
TensorFlow
PyTorch
StatsModels

Todos os cálculos estatísticos e matemáticos são implementados manualmente.

📊 Métodos Estatísticos Implementados

O sistema utiliza implementações próprias de:

Média
Mediana
Moda
Variância
Desvio padrão
Covariância
Correlação de Pearson
Cohen's d
Regressão Linear Simples
Média Móvel
Suavização de Tendência
Cálculo Probabilístico Baseado em Histórico Climático
🔍 Metodologia de Previsão

A previsão climática é calculada combinando:

Média sazonal histórica
Regressão linear manual
Média móvel
Frequência histórica de chuva
Correlação entre umidade e precipitação
📁 Estrutura do Projeto
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
📄 Formato dos Arquivos Aceitos

O sistema aceita arquivos:

.csv

Os arquivos devem seguir o padrão de exportação do INMET contendo informações como:

Estação
Código da estação
UF
Região
Latitude
Longitude
Altitude
Data
Hora UTC
Precipitação
Pressão
Temperatura
Umidade
Vento
Radiação
Exemplo de arquivo válido
INMET_S_RS_B846_NONOAI_01-01-2026_A_30-04-2026.CSV

São aceitas extensões:

.CSV
.csv
📂 Onde Colocar os Arquivos CSV

Os arquivos do INMET devem ser colocados em:

data/uploads

Exemplo:

Projeto_Machine_Learning/data/uploads/INMET_S_RS_B846_NONOAI_01-01-2026_A_30-04-2026.CSV

Caso a pasta não exista, o sistema tentará criá-la automaticamente.

📦 Dependências

O projeto utiliza apenas bibliotecas padrão do Python.

Bibliotecas utilizadas
os
csv
json
datetime
tkinter
unicodedata

Normalmente todas já acompanham a instalação do Python.

🖥️ Verificando o Tkinter

Em instalações padrão do Python para Windows, o Tkinter já vem instalado.

Para verificar:

python -m tkinter

Se abrir uma pequena janela de teste, o Tkinter está funcionando corretamente.

🚀 Instalação
1. Instale o Python

Baixe em:

https://www.python.org/downloads/

Durante a instalação no Windows, marque:

Add Python to PATH
2. Clone ou Baixe o Projeto

Exemplo:

C:\Users\SeuUsuario\Desktop\Projeto_Machine_Learning
3. Crie a Pasta de Uploads
Projeto_Machine_Learning/data/uploads
4. Adicione os Arquivos do INMET

Copie os arquivos .csv para:

data/uploads

Exemplo:

data/uploads/INMET_S_RS_B846_NONOAI_01-01-2026_A_30-04-2026.CSV
▶️ Como Executar

Abra o terminal na pasta do projeto:

cd C:\Users\SeuUsuario\Desktop\Projeto_Machine_Learning

Execute:

python main.py

Ou:

C:\Users\SeuUsuario\AppData\Local\Python\python.exe main.py

Exemplo de ambiente:

& C:\Users\I010523\AppData\Local\Python\pythoncore-3.14-64\python.exe main.py
🧭 Como Utilizar

Ao iniciar o sistema será exibida uma interface gráfica contendo:

Cidade
Data futura
Resultado da previsão
Exemplo
Cidade: NONOAI
Data futura: 2027-06-15

Clique em:

Consultar previsão

O sistema localizará os dados da cidade nos arquivos presentes em:

data/uploads
📈 Exemplo de Resultado
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
⚠️ Cidade Não Encontrada

Caso a cidade informada não seja encontrada nos arquivos carregados, será exibida a mensagem:

Nenhum arquivo correspondente à cidade informada foi encontrado.

Além disso, a interface apresentará um aviso ao usuário.

📌 Observações Sobre a Previsão

A previsão gerada é baseada exclusivamente em dados históricos disponíveis nos arquivos carregados.

A qualidade da previsão depende de fatores como:

Quantidade de dados disponíveis;
Número de anos analisados;
Integridade dos registros;
Ausência de falhas no CSV;
Representatividade da estação meteorológica.
Recomendações

Para melhores resultados:

Utilizar vários anos de dados;
Utilizar múltiplas estações próximas;
Evitar arquivos com lacunas extensas;
Utilizar registros completos de temperatura, umidade, pressão e precipitação.
⚠️ Limitações

O sistema não realiza consulta automática em serviços online.

Todo o processamento é realizado exclusivamente a partir dos arquivos locais armazenados em:

data/uploads

Além disso, por requisito do projeto, não são utilizadas bibliotecas externas de Machine Learning ou Estatística.

⚡ Execução Rápida
cd Projeto_Machine_Learning

mkdir data\uploads

python main.py

Copie os arquivos do INMET para:

data/uploads

Em seguida:

Execute o sistema;
Informe a cidade desejada;
Informe uma data futura;
Clique em Consultar previsão.
📜 Licença

Este projeto pode ser utilizado para fins acadêmicos, educacionais e de pesquisa climática.

Sinta-se à vontade para adaptar e expandir a solução conforme suas necessidades.
