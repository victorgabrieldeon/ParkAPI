# **ParkAPI**

**ParkAPI** é uma solução inteligente para gerenciamento de estacionamentos, oferecendo funcionalidades como reservas, check-in/check-out de veículos, cálculo automático de tarifas e pagamento integrado. Ideal para facilitar o gerenciamento de vagas e otimizar a experiência do usuário.

---

## **Funcionalidades**

- **Autenticação e Gestão de Usuários**
  - Registro e login de clientes e administradores.
  - Consultar e atualizar informações do usuário.

- **Gerenciamento de Vagas**
  - Consultar, adicionar e atualizar vagas.
  - Atribuir status de ocupação e disponibilidade.

- **Reservas e Controle de Entrada/Saída**
  - Criar e listar reservas de estacionamento.
  - Registrar entrada e saída de veículos.

- **Pagamentos e Tarifas**
  - Consultar preços por hora, diária, etc.
  - Processar pagamentos e consultar status.

- **Relatórios e Gestão**
  - Relatórios diários de ocupação e faturamento.
  - Relatórios de clientes e reservas.

---

## **Tecnologias**

- **NestJS**: Framework Node.js para construir aplicações escaláveis e eficientes.
- **TypeORM**: ORM para TypeScript e JavaScript, utilizado para o gerenciamento do banco de dados.
- **PostgreSQL**: Banco de dados relacional utilizado para armazenar as informações.
- **JWT**: Autenticação e autorização via tokens JWT.
- **Docker**: Para facilitar a implantação e gerenciamento.

---

## **Instalação**

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/parkapi.git
    ```

2. Navegue até o diretório do projeto:
    ```bash
    cd parkapi
    ```

3. Instale as dependências:
    ```bash
    npm install
    ```

4. Configure o banco de dados no arquivo `.env`:
    ```dotenv
    DATABASE_HOST=localhost
    DATABASE_PORT=5432
    DATABASE_USERNAME=usuario
    DATABASE_PASSWORD=senha
    DATABASE_NAME=parkapi
    ```

5. Execute as migrações para configurar o banco de dados:
    ```bash
    npm run migration:run
    ```

6. Inicie o servidor:
    ```bash
    npm run start:dev
    ```

---

## **Rotas da API**

### **Autenticação**

- `POST /auth/register`: Registrar um novo usuário.
- `POST /auth/login`: Realizar login e obter token de acesso.

### **Vagas**

- `GET /parking-spots`: Listar vagas disponíveis.
- `GET /parking-spots/{id}`: Detalhes de uma vaga.
- `POST /parking-spots`: Criar uma nova vaga (admin).
- `PUT /parking-spots/{id}`: Atualizar status ou informações da vaga.
- `DELETE /parking-spots/{id}`: Remover uma vaga (admin).

### **Reservas**

- `POST /reservations`: Criar uma nova reserva.
- `GET /reservations`: Listar reservas ativas.
- `GET /reservations/{id}`: Detalhes de uma reserva.
- `PUT /reservations/{id}/check-in`: Registrar entrada do veículo.
- `PUT /reservations/{id}/check-out`: Registrar saída e calcular o valor.

### **Pagamentos**

- `GET /pricing`: Consultar preços de tarifas.
- `POST /payments/{reservation_id}`: Processar pagamento de uma reserva.

### **Relatórios**

- `GET /reports/daily`: Relatório de ocupação diária.
- `GET /reports/revenue`: Relatório de faturamento.

---

## **Contribuindo**

1. Faça um fork do repositório.
2. Crie uma nova branch para suas mudanças.
3. Envie um pull request com a descrição das alterações.

---

## **Licença**

Este projeto está licenciado sob a licença MIT - consulte o arquivo [LICENSE](LICENSE) para mais informações.

---
