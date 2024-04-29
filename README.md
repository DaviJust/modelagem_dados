## Modelo de Banco de Dados - Gerenciamento de Empresas Parceiras e Colaboradores

**Objetivo:**

Este modelo de banco de dados visa facilitar o gerenciamento de empresas parceiras, suas áreas de atuação, tecnologias utilizadas, colaboradores e rescisões de contratos. Ele oferece uma estrutura robusta para armazenar e organizar informações relevantes para empresas que trabalham com parcerias estratégicas.

**Entidades:**

* **Empresa Parceira:**
    * Representa as empresas parceiras que colaboram com a sua organização.
    * Campos:
        * `ID`: Número inteiro (chave primária)
        * `CNPJ`: String (14 caracteres) - Validar formato CNPJ
        * `Nome`: String (255 caracteres)
        * `Ramo de Atividade`: String (100 caracteres)
        * `Endereço`: String (255 caracteres)
        * `Telefone`: String (20 caracteres) - Validar formato telefone
        * `Área da Empresa Parceira`: String (40 caracteres)
        * `IE`: String (13 caracteres)
        * `EMAIL`: String (80 caracteres)
* **Área:**
    * Representa as áreas de atuação das empresas parceiras.
    * Campos:
        * `ID Área`: Número inteiro (chave primária)
        * `Nome`: String (100 caracteres)
        * `Descrição`: String (255 caracteres)
        * `Empresa Parceira_ID`: Número inteiro (chave estrangeira para a tabela `Empresa Parceira`)
* **Tecnologia:**
    * Representa as tecnologias utilizadas pelas empresas parceiras.
    * Campos:
        * `ID`: Número inteiro (chave primária)
        * `Nome`: String (100 caracteres)
        * `Descrição`: String (255 caracteres)
* **Tecnologia_Área:**
    * Relaciona as tecnologias com as áreas de atuação das empresas parceiras.
    * Campos:
        * `ID`: Número inteiro (chave primária)
        * `Tecnologia_ID`: Número inteiro (chave estrangeira para a tabela `Tecnologia`)
        * `Área_ID`: Número inteiro (chave estrangeira para a tabela `Área`)
* **Colaborador:**
    * Representa os colaboradores das empresas parceiras que trabalham em conjunto com a sua organização.
    * Campos:
        * `Matrícula`: Número inteiro (chave primária)
        * `CPF`: String (11 caracteres) - Validar formato CPF
        * `Nome`: String (255 caracteres)
        * `Email`: String (100 caracteres) - Validar formato email
        * `Empresa Parceira_Área_ID`: Número inteiro (chave estrangeira para a tabela `Empresa-Parceira_Área`)
        * `RG`: String(14 caracteres)
        * `Endereço`: String(255 caracteres)

**Relacionamentos:**

* Uma empresa parceira pode ter diversas áreas (relação 1 para N).
* Uma área pode ter diversas tecnologias (relação 1 para N).
* Uma tecnologia pode ser utilizada em diversas áreas (relação 1 para N).
* Uma empresa parceira pode ter diversos colaboradores (relação 1 para N).
* Um colaborador está associado a uma única empresa parceira e a uma única área de atuação dentro da empresa (relação 1 para 1).
* Uma empresa parceira pode ter diversos contratos rescindidos (relação 1 para N).

**Benefícios:**

* **Organização e Controle:** Facilita a gestão de informações sobre empresas parceiras, áreas de atuação, tecnologias utilizadas, colaboradores e rescisões de contratos.
* **Acesso Rápido:** Permite consultas e atualizações de dados de forma rápida e eficiente.
* **Tomada de Decisões:** Auxilia na tomada de decisões estratégicas relacionadas a parcerias e colaboradores.
* **Histórico Completo:** Armazena o histórico de informações sobre empresas parceiras, incluindo rescisões de contratos.

**Implementação:**

* Este modelo de banco de dados pode ser implementado em diversos sistemas de gerenciamento
