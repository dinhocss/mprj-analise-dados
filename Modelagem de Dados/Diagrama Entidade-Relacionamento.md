# Estratégia de Modelagem
A estratégia utilizada para criação do modelo Entidade-Relacionamento foi a **Engenharia Reversa**. A escolha baseou-se no fato de partirmos de um banco de dados já existente,o que facilitou a criação do modelo conceitual. Além disso, utilizou-se a estratégia **Bottom Up**, iniciando a elaboração do modelo a partir dos atributos, seguindo para a definição das entidades, e por fim, dos relacionamentos entre elas. 

# Definição das Cardinalidades
A análise das chaves estrangeiras permitiu inferir informações acerca da hierarquia e das regras de negócio da administração pública:
* Uma entidade pode participar de diversos contratos, bem como possuir diversos empenhos.
* Um contrato pode ter apenas um fornecedor, assim como estar relacionado com apenas uma entidade.
* Um fornecedor pode não ter nenhum ou possuir vários contratos vigentes.
* Um empenho precisa ter uma entidade, obrigatoriamente, estar vinculado a uma entidade e a um contrato, podendo ter diversos pagamentos associados. A cardinalidade mínima em pagamentos indica que podem ocorrer problemas na hora da entrega, como atrasos ou outros motivos, fazendo com que o pagamento ainda não tenha sido efetuado. Além disso, um empenho está ligado à liquidação da nota fiscal.
* A liquidação pode estar relacionada a um ou mais pagamentos, porém está relacionada com apenas uma nota fiscal.

# Considerações a do Diagrama ER
A partir da análise do diagrama, nota-se que a entidade **Empenho** atua como o eixo central do modelo, possuindo o maior número de relacionamentos. Por ser o elo ntre planejamento (Contrato) e a execução financeira (Liquidação/Pagamento), esta tabela torna-se o ponto de foco para a investigação de anomalias. Qualquer inconsistência nesta etapa pode propagar erros para todo o restante do fluxo orçamentário. 
