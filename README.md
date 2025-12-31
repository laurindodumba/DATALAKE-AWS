
#  AWS Data Engineering Pipeline




Neste projeto foi desenvolvido um **pipeline de engenharia de dados na AWS**, seguindo boas práticas de **Data Lake**, **arquitetura em camadas (Bronze / Silver / Gold)** e automação para ingestão, transformação e disponibilização de dados para análise.

---

##  Visão Geral

O objetivo deste projeto é demonstrar a construção de um pipeline de dados escalável e confiável utilizando serviços da AWS, desde a extração de dados de fontes externas até a disponibilização para consumo analítico.

Usando dados do diretório de identificações de contas Transacionais - DICT  que é o orgão de serviços de arranjos de Pix que permite buscar detalhes de contas transacionaus com chaves de endereçamento para que faz um pagamento através das chaves do Pix, que pode ser um email, CPF, CNPJ telefone e EVP. Basicamente funciona da seeguinte forma toda vez que alguém quiser realizar algum Pix as informações sobre a pessoa que irá receber os valores do Pix, volta para o DICT para confirmar as informações do destinário que vai receber tornado a operação mais segura e fácil.

**Principais características:**

* Ingestão de dados via API / arquivos
* Armazenamento em Data Lake (Amazon S3)
* Processamento e transformação de dados
* Organização em camadas (Bronze, Silver e Gold)
* Código modular e reutilizável

---

## 🏗️ Arquitetura do Pipeline

```text
┌──────────────┐
│ Data Source  │  (API / JSON)
└──────┬───────┘
       │
       ▼
┌────────────────────┐
│ S3 - Bronze Layer  │  (Raw data)
└──────┬─────────────┘
       │
       ▼
┌────────────────────┐
│ S3 - Silver Layer  │  (Cleaned & standardized)
└──────┬─────────────┘
       │
       ▼
┌────────────────────┐
│ S3 - Gold Layer    │  (Business-ready data)
└────────────────────┘
```

---

##  Data Lake Layers

###  Bronze (Raw)

* Dados brutos
* Sem transformações
* Fonte original preservada

###  Silver (Trusted)

* Limpeza de dados
* Padronização de tipos
* Tratamento de valores nulos

### Ambiente na AWS

<img width="1632" height="435" alt="image" src="https://github.com/user-attachments/assets/a8360bcd-6c59-49d1-a648-0d15fef4dde9" />




---

##  Tecnologias Utilizadas

* **AWS S3** – Data Lake
* **AWS IAM** – Controle de acesso
* **Python 3** – Linguagem principal
* **Boto3** – Integração com AWS
* **Pandas / PySpark** – Transformações de dados
* **Git & GitHub** – Versionamento

---

##  Estrutura do Projeto

```text
├── data/
│   ├── bronze/
│   ├── silver/
│   └── gold/
├── src/
│   ├── extract.py
│   ├── transform.py
│   ├── load.py
│   └── main.py
├── config/
│   └── settings.yaml
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚙️ Configuração do Ambiente

###  Clonar o repositório

```bash
git clone https://github.com/laurindodumba/DATALAKE-AWS/tree/main
cd seu-repositorio
```

###  Criar ambiente virtual

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\\Scripts\\activate     # Windows
```

###  Instalar dependências

```bash
pip install -r requirements.txt
```

###  Configurar credenciais AWS

```bash
aws configure
```

---


Fluxo executado:

1. Extração dos dados
2. Upload para camada Bronze
3. Transformações (Silver)
4. Agregações finais (Gold)

---

##  Segurança e Boas Práticas

* Princípio do menor privilégio (IAM)
* Separação de permissões por camada
* Não versionar credenciais
* Uso de variáveis de ambiente

---

## Possíveis Evoluções

* Orquestração com Apache Airflow
* Processamento distribuído com AWS Glue / Spark
* Catálogo de dados com AWS Glue Data Catalog
* Monitoramento com CloudWatch
* CI/CD com GitHub Actions

---


## 👤 Autor

**Laurindo Dumba**
Engenheiro de Dados | 

🔗 LinkedIn: [https://www.linkedin.com](https://www.linkedin.com/in/laurindo-dumba-45b214102/)

---

PS: Se este projeto te ajudou, deixe uma estrela ⭐ no repositório!
