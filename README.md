# utilsArchives
### Arquivos úteis para se realizar teste no back-end
# Insomnia
  ## Seções 
  ### Se faz necessário cadastrar algum funcionário antes de realizar a seguinte ação!
  * Cadastrar seções  
  ###### POST: localhost:6868:/secoes
  ```json
    {
      "responsavel": "Thiago",
      "nome": "Departamento de E-commerce"
    }
  ```
  * Buscar seção pelo id 
    * ###### GET: localhost:6868/secoes/{id}
  * Listar seções   
    * ###### GET: localhost:6868/secoes
  * Remover seção 
    * ###### DELETE: localhost:6868/secoes/{id} 
  ## Funcionários 
  #### Ao cadastrar o funcionário, um usuário para logar no sistema é criado automaticamente, com as credenciais informadas
  * Cadastrar funcionários
  ###### POST: localhost:6868/funcionarios
  ```json
    {
      "funcionarioInfo": {
        "numero_cracha": 67299,
        "nome": "Josias",
        "cpf": "12912323215",
        "telefone": "(47)99267-6792",
        "valor_hora": 25.5,
        "email": "josias@weg.net",
        "senha": "1234"
      },
      "secao_nome": "WEG Digitals"
    }
  ```
  * Buscar funcionários
    * ###### GET: localhost:6868/funcionarios/{numeroCracha}
  * Listar todos os funcionários
    * ###### GET: localhost:6868/funcionarios
  * Remover funcionários
    * ###### DELETE: localhost:6868/funcionarios/{numeroCracha}
  ## Consultores
  #### Para cadastrar um consultor é necessário que haja, no mínimo, um fornecedor cadastrado
  * Cadastrar consultores
  ###### POST: localhost:6868/funcionarios/consultor
  ```json
    {
      "funcionario": {
        "numero_cracha": 67236,
        "nome": "Douglas",
        "cpf": "11111111111",
        "telefone": "(47)99267-6792",
        "valor_hora": 25.5,
        "email": "douglas@outlook.net",
        "senha": "1234"
      },
      "nome_fornecedor": "ABAP"
    }
  ```
  * Buscar consultores
    * ###### GET: localhost:6868/funcionarios/consultor/{numeroCracha}
  * Listar todos os consultores
    * ###### GET: localhost:6868/funcionarios/consultor
  * Remover consultor
    * ###### DELETE: localhost:6868/funcionarios/consultor/{numeroCracha}
  ## Fornecedores
  * Cadastrar fornecedores
  ###### POST: localhost:6868/fornecedores
  ```json
    {
      "nome": "ABAP",
      "cnpj": "84.429.695/0001-11",
      "email": "abap@gmail.com"
    }
  ```
  * Buscar fornecedor pelo consultor
    * ###### GET: localhost:6868/fornecedores/{numeroCracha}
  * Listar todos os fornecedores
    * ###### GET: localhost:6868/fornecedores
  ## Cargos
  * Cadastrar cargos
  ###### POST: localhost:6868/cargos
  ```json
    {
      "nome": "User"
    }
  ```
  * Buscar cargos
    * ###### GET: localhost:6868/cargos/{id}
  * Listar todos os cargos
    * ###### GET: localhost:6868/cargos
  * Remover cargos
    * ###### DELETE: localhost:6868/cargos/{id}
  ## Projetos
  #### Para cadastrar um projeto é necessários que haja, pelo menos dois funcionários e duas seções cadastradas
  * Cadastrar projetos
  ###### POST: localhost:6868/projetos
  ```json
    {
      "infoProjetosInputDTO": {
        "numeroDoProjeto": 182245,
        "titulo": "GHI - Implantação2 de motores de carros3",
        "descricao": "Implantar motores eletricos na secao de tinturaria",
        "nome_responsavel": "Victor",
        "nome_solicitante": "Cauã",
        "data_de_inicio": "18/06/2021",
        "data_de_termino": "18/07/2021",
        "data_de_aprovacao": "17/06/2021"
      },
      "despesasInputDTOS": [
        {
          "nome": "Desenvolvimento Java",
          "esforco": 300,
          "valor": 15000
        },
        {
          "nome": "Desenvolvimento ABAP",
          "esforco": 300,
          "valor": 25000
        }
      ],
      "ccPagantesInputDTO": [
        {
          "secao_id": 1,
          "valor": 25000
        },
        {
          "secao_id": 2,
          "valor": 15000
        }
      ]
    }
  ```
  * Buscar projetos
    * ####### GET: localhost:6868/projetos/{numeroDoProjeto}
  * Listar todos os projetos
    * ####### GET: localhost:6868/projetos
  * Editar projetos
  ###### PUT: localhost:6868/projetos/editar/{numeroDoProjeto}
  ```json
    {
      "infoProjetosInputDTO": {
        "numeroDoProjeto": 182245,
        "titulo": "GHI - Implantação2 de motores de carros3",
        "descricao": "Implantar motores eletricos na secao de tinturaria",
        "nome_responsavel": "Victor",
        "nome_solicitante": "Cauã",
        "data_de_inicio": "18/06/2021",
        "data_de_termino": "18/07/2021",
        "data_de_aprovacao": "17/06/2021"
      },
      "despesasInputDTOS": [
        {
          "nome": "Desenvolvimento Java",
          "esforco": 250,
          "valor": 15000
        },
        {
          "nome": "Desenvolvimento ABAP",
          "esforco": 300,
          "valor": 25000
        }
      ],
      "ccPagantesInputDTO": [
        {
          "secao_id": 1,
          "valor": 30000
        },
        {
          "secao_id": 2,
          "valor": 10000
        }
      ]
    }
  ```
  * Remover projetos
    * ###### DELETE: localhost:6868/projetos/{id}
  #### Rotas de filtros
  * Listar projetos concluídos
    * ###### GET: localhost:6868/projetos/concluidos
  * Listar projetos em andamento
    * ###### GET: localhost:6868/projetos/em_andamento
  * Listar projetos atrasados
    * ###### GET: localhost:6868/projetos/atrasados
  * Listar projetos por seção
    * ###### GET: localhost:6868/projetos/secao/{secao}
  #### Rotas de contagens
  * Contagem de projetos concluidos e de verbas por status
    * ###### GET: localhost:6868/projetos/count
  * Contagem de projetos concluídos nos últimos 7 dias
    * ###### GET: localhost:6868/projetos/count/last-seven
  * Contagem de verba utilizada por projeto
    #### Se usar o parâmetro 0, será feito o cálculo de todos os projetos
    * ###### GET: localhost:6868/projetos/count/verba/{numeroDoProjeto}  
  * Contagem de verba utilizada nos últimos n dias
    * ###### GET: localhost:6868/projetos/count/{dias}
  * Contagem de horas apontadas por consultor no projeto
    * ###### GET: localhost:6868/projetos/horas/{numeroCracha}
  #### Consultores - Projetos
  * Alocar consultores aos projetos
    * ###### POST: localhost:6868/alocar/{numeroDoProjeto}/{numeroCracha}
  * Apontamento de horas
  ###### PUT: localhost:6868/projetos/horas/{numeroDoProjeto}/{numeroCracha}
  ```json
    {
      "horas": 50
    }
  ```
  * Listar projetos em que o consultor está atrelado
    * ###### GET: localhost:6868/projetos/consultor/{numeroCracha}
  * Desalocar consultores dos projetos
    * ###### DELETE: localhost:6868/projetos/{numeroDoProjeto}/{numeroCracha}
  ## Atas
  * Fazer upload das atas
  ###### POST: localhost:6868/files/upload/{numeroDoProjeto}
  ![Upload ATA](https://github.com/ProjectGEW/utilsArchives/blob/main/ata_upload.PNG)
  * Fazer download das atas
    * ###### GET: localhost:6868/files/download/{numeroDoProjeto} 
