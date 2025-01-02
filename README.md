# ETL Coinbase Dashboard

Este projeto consiste em um pipeline ETL (Extract, Transform, Load) que consome dados da API da Coinbase, armazena as informações em um banco de dados relacional para consultas, e exibe os dados em um dashboard interativo desenvolvido com Streamlit.

## Índice
- [Objetivo](#objetivo)
- [Arquitetura do Projeto](#arquitetura-do-projeto)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Executar o Projeto](#como-executar-o-projeto)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

## Objetivo
O objetivo deste projeto é criar uma solução de engenharia de dados que possibilite o consumo, armazenamento e visualização de informações financeiras da Coinbase. Isso permitirá a análise de tendências de mercado e o monitoramento de dados em tempo real.

## Arquitetura do Projeto
1. **Extração (Extract):** Consome dados da API da Coinbase sobre preços, volumes e outras métricas relevantes de criptomoedas.
2. **Transformação (Transform):** Processa e organiza os dados brutos para deixá-los em um formato utilizável, como tabelas normalizadas.
3. **Carregamento (Load):** Armazena os dados processados em um banco de dados relacional (PostgreSQL).
4. **Visualização:** Utiliza Streamlit para exibir os dados em gráficos e tabelas interativas.

## Tecnologias Utilizadas
- **Python**: Linguagem principal para o pipeline ETL.
- **Requests**: Para consumo da API da Coinbase.
- **Pandas**: Para manipulação e transformação de dados.
- **SQLAlchemy**: Para conexão e operações no banco de dados.
- **PostgreSQL**: Banco de dados relacional para armazenamento dos dados.
- **Streamlit**: Para criação do dashboard interativo.

## Como Executar o Projeto
### Pré-requisitos
1. **Python 3.9+** instalado.
2. Banco de dados PostgreSQL configurado.
3. Biblioteca `poetry` para gerenciar dependências (opcional).

### Passo a Passo
1. Clone este repositório:
   ```bash
   git clone https://github.com/seuusuario/etl_coinbase_dashboard.git
   cd etl_coinbase_dashboard
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   # ou, se usar poetry
   poetry install
   ```

3. Configure as variáveis de ambiente no arquivo `.env`:
   ```
   API_KEY=SUACHAVEAPI
   DATABASE_URL=postgresql://usuario:senha@localhost:5432/coinbase
   ```

4. Execute o script ETL para consumir e carregar os dados no banco:
   ```bash
   python etl.py
   ```

5. Execute o Streamlit para visualizar o dashboard:
   ```bash
   streamlit run dashboard.py
   ```

6. Acesse o dashboard em [http://localhost:8501](http://localhost:8501).

## Estrutura do Projeto
```
.
├── data
│   └── processed  # Dados transformados (se necessário)
├── db
│   └── schema.sql  # Scripts para criar as tabelas do banco de dados
├── etl.py          # Script principal do pipeline ETL
├── dashboard.py    # Dashboard Streamlit
├── requirements.txt # Dependências do projeto
├── .env.example    # Exemplo de arquivo de configuração de variáveis de ambiente
└── README.md       # Documentação do projeto
```

## Contribuindo
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests para melhorias ou correções.

## Licença
Este projeto está licenciado sob a [MIT License](LICENSE).
