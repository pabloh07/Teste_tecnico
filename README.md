### Casos de Teste por Campo e Resultados Esperados

**Nome completo:**

* Inserção de nome único - Aceito
* Inserção de nome e sobrenome - Aceito
* Inserção de caracteres que não sejam letras - Inválido
* Enviar campo de nome vazio - Inválido
* Testar o limite de caracteres do banco de dados - Aceito (até o limite)
* Testar nome duplicado - Depende da regra de negócio (sistemas costumam aceitar homônimos)

**E-mail:**

* Inserção de e-mail comum - Aceito
* Inserir sem o @ - Inválido
* Inserir com espaço - Inválido
* Testar e-mail duplicado - Inválido
* Testar e-mail sem extensão - Inválido
* Inserir campo vazio - Inválido

**Número de telefone:**

* Testar número válido - Aceito
* Testar DDD diferente - Aceito
* Testar caracteres não numéricos - Inválido
* Inserir campo vazio - Inválido
* Inserir menos caracteres do que o necessário - Inválido

**Data de nascimento:**

* Testar data de nascimento válida - Aceito
* Testar menor de idade - Depende da regra de negócio do sistema
* Testar caracteres não numéricos - Inválido
* Testar datas futuras - Inválido
* Testar datas impossíveis de existir - Inválido

**Endereço:**

* Inserção de CEP válido - Aceito
* Inserção de CEP sem hífen - Aceito
* Autopreenchimento dos outros campos após o CEP - Aceito
* Inserção de CEP inválido ou inexistente - Inválido
* Inserção de caracteres não numéricos no CEP - Inválido
* Deixar campos obrigatórios vazios - Inválido
* Testar limite de caracteres nos campos "Número" e "Complemento" - Aceito
* Inserir números ou caracteres especiais nos campos de Cidade e Estado - Inválido
* Modificar manualmente os campos de Cidade/Estado após o preenchimento do CEP - Aceito

### Resolução do Desafio (GNRE)

> "Após uma análise detalhada no XML, identifiquei a causa raiz do erro. A chave de acesso da nota fiscal (no campo extra 77) mostra pelos dígitos `2305` que a venda ocorreu originalmente em **maio de 2023**. O bug ou erro de processo aconteceu porque o sistema (ou o cliente) gerou essa guia com atraso em **janeiro de 2024**, preenchendo o vencimento e o pagamento para a data atual (`2024-01-11`), mas sem aplicar os juros e multas devidos pelo recolhimento tardio. Essa incoerência cronológica fez o validador da GNRE rejeitar o arquivo na tag de referência."
