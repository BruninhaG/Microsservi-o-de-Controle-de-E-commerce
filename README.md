# 🛒 Microsserviço de Controle de E-commerce

## 📝 Descrição do Projeto
Este projeto foi desenvolvido com o objetivo de construir uma **arquitetura de microsserviços** para controle de um sistema de E-commerce.

Utilizando **Java e Spring Boot**, o sistema simula a integração e comunicação entre dois microsserviços principais:
* **`warehouse` (Armazém):** Responsável pelo controle de estoque e informações dos produtos.
* **`storefront` (Vitrine/Loja):** Responsável por servir a interface de loja e interagir com o `warehouse` via comunicação síncrona (REST/HTTP).

O desenvolvimento focou na aplicação de conceitos de arquitetura distribuída, criação de APIs RESTful, gerenciamento de entidades e boas práticas de desenvolvimento em Java.

## ✨ Microsserviços e Funcionalidades
### 🏭 Microsserviço `warehouse` (Armazém)
* **Controle de Estoque:** CRUD (Criação, Leitura, Atualização, Deleção) de entidades de produtos.
* **APIs de Inventário:** Exposição de endpoints para consulta e atualização de produtos, consumidas pela `storefront`.
* **Gerenciamento de Entidades:** Implementação das classes modelo e repositórios.

### 🏪 Microsserviço `storefront` (Vitrine/Loja)
* **Integração Externa:** Consumo de APIs do microsserviço `warehouse` para exibir dados de produtos na vitrine.
* **Lógica de Controle:** Implementação de *controllers* e *services* para gerenciar o fluxo de dados entre a aplicação e o `warehouse`.
* **Rota Principal:** Exibição da lista de produtos e detalhes de um produto específico.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Java 17+
* **Framework:** Spring Boot 3+
    * Spring Web (para construção das APIs REST)
    * Spring Data JPA (para persistência de dados)
* **Banco de Dados:** H2 Database (In-memory para desenvolvimento/teste)
* **Gerenciador de Dependências:** Maven
* **Desenvolvimento:** IDE [Ex: IntelliJ IDEA, VS Code]
* **Controle de Versão:** Git

## 💻 Instalação e Execução
### Pré-requisitos
Certifique-se de ter instalado:
* **JDK 17** ou superior
* **Maven** (ou use o wrapper embutido)

### Passos
1. **Clone o repositório:**
    ```bash
    git clone [Link do seu repositório no Git]
    cd [Nome da pasta do projeto]
    ```

2. **Execute o Microsserviço `warehouse` (Armazém):**
    Este é o **primeiro** microsserviço a ser iniciado.
    ```bash
    cd warehouse
    # Para rodar via Maven
    ./mvnw spring-boot:run
    ```
    O serviço estará disponível em `http://localhost:[Porta do Warehouse, ex: 8081]`.

3. **Execute o Microsserviço `storefront` (Vitrine/Loja):**
    ```bash
    cd ../storefront
    # Para rodar via Maven
    ./mvnw spring-boot:run
    ```
    O serviço estará disponível em `http://localhost:[Porta do Storefront, ex: 8080]`.

> **ℹ️ Nota:** O microsserviço `storefront` **requer** que o `warehouse` esteja em execução para buscar os dados de produtos.

## 🔗 Rotas da API (Endpoints Principais)
### Microsserviço `warehouse`
| Método | Rota | Descrição |
| :---: | :--- | :--- |
| `GET` | `/products` | Lista todos os produtos no estoque. |
| `GET` | `/products/{id}` | Retorna detalhes de um produto específico. |
| `POST` | `/products` | Cria um novo produto (necessita Body JSON). |

### Microsserviço `storefront`
| Método | Rota | Descrição |
| :---: | :--- | :--- |
| `GET` | `/storefront/products` | Consulta e exibe a lista de produtos obtida do `warehouse`. |

## 🎨 Demonstração
Você pode testar a comunicação entre os serviços acessando o endpoint do `storefront` no seu navegador:

* **Listar Produtos:** `http://localhost:[Porta do Storefront]/storefront/products`

O *storefront* fará automaticamente a requisição para o *warehouse* e exibirá os dados.

---

## 👩‍💻 Autora
Feito com 💛 por Bruna Guimarães

---
## 🌟 Apoie o projeto
Se você gostou, não esqueça de deixar uma ⭐ no repositório!
Isso ajuda muito o projeto a crescer e me incentiva a continuar criando. 🙌

---

## 🚀 Status do Projeto
✅ Concluído
