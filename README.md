# Projeto: Extração e Análise de Dados do Lattes com Apache Hop

## 📌 Sobre o Projeto

Este projeto tem como objetivo extrair, transformar e analisar dados de currículos da Plataforma Lattes, utilizando ferramentas de ETL e visualização de dados.

A solução foi desenvolvida com foco em automatizar a leitura de arquivos XML do Lattes, estruturar os dados e gerar insights a partir deles.

---

## Tecnologias utilizadas
- Apache Hop (ETL)
- XML (dados do Lattes)
- Banco de dados relacional
- Power BI (visualização de dados)

---
## Como executar o projeto
1. Subir o banco de dados com Docker
   ```
   docker build -t lattes-db .
   docker run -d --name lattes-db -p 5437:5432 lattes-db
   ```
2. Configurar o banco
   - Acesse o banco pelo DBeaver (ou outro)
   - Crie as tabelas de pesquisadores e producoes
     
3. executar os pipelines no Apache Hop
   - dados_pesquisador → leitura de um único XML
   - dados_pesquisadores_varios → leitura de múltiplos pesquisadores
   - dados_producoes_pesquisadores_varios → extração das produções acadêmicas

   Esses pipelines realizam:
  - Leitura dos arquivos XML
  - Tratamento dos dados
  - Inserção no banco de dados

---

## Etapas do projeto
1.  Extração de dados
Leitura de múltiplos arquivos XML do Lattes
Uso do transform Get file names para percorrer diretórios
Processamento dos dados com Get data from XML
2. Transformação
Seleção e organização dos dados com Select values
Tratamento de campos como:
Nome do pesquisador
ID Lattes
Produções acadêmicas (artigos)
ISSN
Ano de publicação
3. Carga de dados
Inserção e atualização dos dados no banco utilizando Insert/Update
Estruturação das tabelas para permitir análise posterior
4. Visualização
Conexão do banco de dados ao Power BI
Criação de gráficos e dashboards para análise das produções acadêmicas

---

## Resultados

O projeto permite:

Automatizar a leitura de currículos Lattes em XML
Estruturar dados acadêmicos de forma organizada
Analisar produção científica por pesquisador
Visualizar dados de forma clara através de dashboards
