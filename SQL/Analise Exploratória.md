# Investigação de Anomalias e Análise Exploratória

Para realizar a análise exploratória, utilizou-se conceitos fundamentais de integridade de Banco de Dados. O objetivo é validar se o banco reflete corretamente a realidade da execução da despesa pública. A investigação foi feita a partir das seguintes regras:

1. **Integridade Referencial e de Vazio**: Garante que os vínculos entre tabelas existam e que os dados obrigatórios não sejam nulos.
2. **Integridade Semântica**: Verifica se os dados obedecem as regras de negócio da execução da despesa pública

## 2.1 Análise de Integridade Referencial
*Nesta etapa, buscamos registros no qual registros filhos apontam para pais inexistentes ou nulos.*

#### Q1: Existem pagamentos sem empenho associado?

*Um pagamento não pode existir sem um empenho prévio*

**Consulta**: Verificar registros em 'pagamento' onde 'id_empenho' é nulo.

#### Q2: Existem liquidações sem empenho vinculado?

*Uma liquidação não pode ocorrer se não há um empenho associado a ela*

**Consulta**: Verificar registros em 'liquidacao_nota_fiscal' onde 'id_empenho' é nulo.

#### Q3: Existem empenhos sem contrato?

*Embora existam compras diretas, valores altos sem contrato indicam anomalias.*

**Consulta**: Verificar quantos empenhos possuem 'id_contrato' nulo e quais os valores de empenhos sem contrato.

#### Q4: Existem empenhos sem Entidade?

*Um empenho deve, obrigatoriamente, estar associado a uma entidade*

**Consulta**: Verificar se algum empenho possui 'id_entidade' nulo.

#### Q5: Existem contratos sem entidade ou fornecedor?

**Consulta**: Verificar se algum contrato possui 'id_endidade' e 'id_fornecedor' nulo.

---

## 2.2 Integridade Semântica
*Nesta etapa, verificamos se os valores e datas possuem algum sentido lógico, mesmo que o banco de dados permita a inserção.*

#### Q6: O valor total pago supera o valor empenhado?
*Não é possível realizar um pagamento maior do que foi empenhado*

**Consulta**: Agrupar pagamentos por empenho, somar e comparar com 'valor' da tabela empenho.

#### Q7: A soma dos empenhos supera o valor do contrato?
*O contrato estabelece um teto financeiro. A soma de todos os empenhos vinculados a um contrato não devem ultrapassar esse teto.*

**Consulta**: Agrupar empenhos por contrato, somar e comparar com 'valor' da tabela contrato.

#### Q8: Existem pagamentos/liquidações anteriores ao empenho?
*A regra de negócio diz que o fluxo de execução da despesa pública é Empenho -> Liquidação -> Pagamento. Quaisquer datas fora dessa ordem é uma anomalia.*

**Consulta**: Comparar 'data_emissao' da tabela liquidação com 'data_empenho' e 'datapagamento' com 'data_empenho'.






