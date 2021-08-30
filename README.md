# utilsArchives
### Arquivos úteis para se realizar teste no back-end
# Insomnia
  ## Centro de Custos 
  ### Se faz necessário cadastrar algum funcionário antes de realizar a seguinte ação!
  * Cadastrar centro de custos  
  ###### POST: localhost:6868:/centros_de_custos
  ```json
    {
      "responsavel": "Thiago",
      "nome": "Departamento de E-commerce"
    }
  ```
  * Bucas centro de custos pelo id 
    * ###### GET: localhost:6868/centros_de_custos/{id}
  * Listar centros de custos   
    * ###### GET: localhost:6868/centros_de_custos
  * Remover centro de custo 
    * ###### DELETE: localhost:6868/centros_de_custos/{id} 
  ## Funcionários 
  #### Ao cadastrar o funcinário, um usuário para logar no sistema é criado automaticamente, com as credenciais informadas
  ###### POST: localhost:6868/funcionarios
  ```json
    {
      "numero_cracha": 67278,
      "nome": "sdains",
      "cpf": "12912323217",
      "usuario": {
        "email": "dsads@weg.net",
        "senha": "1234"
      }
    }
  ```
  * Listar Funcinários
  
