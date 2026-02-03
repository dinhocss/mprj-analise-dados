# Auditoria de Execução de Despesas Públicas

Este repositório contém os artefatos técnicos do desafio de análise de dados focado em auditoria de despesas públicas. O projeto utilizou SQL para validação de integridade e Power BI para visualização de anomalias.

## Conteúdo do repositório

* Relatorio_Tecnico.pdf: Documento detalhado com a metodologia, análises SQL, insights de negócio e plano de ação.
* Glossario.md: Documento dando uma breve explicação das entidades do sistema.
* /ModelagemER: Arquivos contendo o diagrama Entidade-Relacionamento e uma breve explicação sobre a modelagem.
* /SQL: O Jupyter Notebook utilizado para realizar as consultas e alguns arquivos para análise gráfica.
* /Analise-grafica: Arquivo fonte do dashboard para visualização iterativa local.

## Relatório Técnico (PDF)

O documento completo com todas as conclusões pode ser visualizado diretamente no navegador ou baixado: [Clique para ler o Relatório Técnico completo](./Relatorio_Tecnico.pdf)

## Dashboard e Visualizações

Como o projeto foi desenvolvido em Power BI Desktop, para interagir com os dados, é necessário:
1. Baixar o arquivo [Analises_graficas.pbix](./Analise-Grafica/Analises_graficas.pbix)
2. Abrir com o software Microsoft Power BI Desktop.

## Modelo de Dados (DER)
O modelo relacional foi validado garantindo a integridade referencial entre Contratos, Emmpenhos Liquidações e Pagamentos. O modelo pode ser visualizado diretamente no navegador ou baixado: [Clique aqui para visualizar o Diagrama Entidade-Relacionamento](./ModelagemER/DER.png)

Segue também uma breve explicação sobre a estratégia de modelagem adotada: [Clique aqui para acessar o documento](./ModelagemER/Diagrama-Entidade-Relacionamento.md)


## Consultas SQL

As consultas foram feitas através da linguagem Python junto com a biblioteca Pandas. Utilizou-se Jupyter Notebook para realização das consultas, que pode ser acessado diretamente do navegador: [Clique aqui para acessar o Jupyter Notebook](./SQL/conexao-banco-de-dados.ipynb)
