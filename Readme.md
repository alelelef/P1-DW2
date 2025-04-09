# Trabalho de Graduação Interdisciplinar

**Alef Chaves**  
**Akemi Obana**

---

## 🧠 Visão Geral

# Sistema Web para Administração de Usuários e Produtos

Este sistema foi desenvolvido com base no padrão  **MVC (Model-View-Controller)**, com foco na separação clara entre regras de negócio, interface e controle de dados. A aplicação oferece uma solução prática para o **cadastro, consulta, edição e remoção** de informações relacionadas a **usuários e produtos**.

Os dados manipulados pela plataforma são armazenados em um banco de dados relacional **MySQL**, garantindo confiabilidade e persistência das informações.

Com uma abordagem orientada à organização modular, o projeto facilita futuras expansões, manutenção do código e reutilização de componentes.


---

## 🧩 Arquitetura e Organização

### 🔁 Padrão MVC

- **Model**: Representa os dados e as regras de negócio, incluindo as entidades `Produto` e `Usuário`. Utiliza um ORM para comunicação com o banco de dados.
- **View**: Composta por páginas HTML que interagem com o usuário final, exibindo formulários e dados.
- **Controller**: Responsável por receber as requisições, validar os dados recebidos e coordenar a lógica de persistência.

### 📂 Estrutura de Pastas

```
/projeto/
├── controllers/
├── models/
├── views/
├── database/
├── templates/
└── main.py
```


---

## ⚙️ Funcionalidades da Aplicação

### 🛍️ Produtos
- `GET /produtos`: Lista todos os produtos.
- `GET /produtos/{id}`: Retorna um produto específico.
- `POST /produtos`: Cria um novo produto com validação.
- `PUT /produtos/{id}`: Atualiza um produto existente.
- `DELETE /produtos/{id}`: Remove um produto.

### 👥 Usuários
- `GET /usuarios`: Lista todos os usuários.
- `GET /usuarios/{id}`: Retorna um usuário específico.
- `POST /usuarios`: Cadastra um novo usuário.
- `PUT /usuarios/{id}`: Atualiza dados de um usuário.
- `DELETE /usuarios/{id}`: Exclui um usuário.

---

## ✅ Validações Implementadas

### Produto
- Nome: mínimo 3 caracteres.
- Preço: deve ser um número positivo.
- Estoque: número inteiro ≥ 0.

### Usuário
- Nome: não pode ser vazio.
- E-mail: formato válido.
- Senha (se aplicável): com critérios de segurança.

Em caso de erro, a API retorna mensagens descritivas, facilitando a correção.

---

## 🧪 Desafios e Soluções

## 🚧 Dificuldades Encontradas e Soluções

🔹 **Gerenciamento de Sessões e Autenticação:** Durante o desenvolvimento, foi necessário implementar um sistema de autenticação eficiente para garantir a segurança dos dados dos usuários. Inicialmente, houve desafios na configuração de tokens de autenticação e na persistência das sessões. A solução foi adotar o **JWT (JSON Web Token)** para autenticação segura e armazenar os tokens de forma segura no backend.

🔹 **Otimização do Tempo de Resposta:** Conforme o banco de dados crescia, as consultas começaram a demorar mais do que o esperado. Isso afetava diretamente a experiência do usuário. A solução foi implementar **índices no banco de dados**, otimizar as **queries SQL** e utilizar **cache** para reduzir o tempo de carregamento das informações frequentemente acessadas.

🔹 **Gerenciamento de Erros e Logs:** O tratamento de erros não estava estruturado no início do projeto, o que dificultava a identificação e correção de falhas. Para resolver isso, foi implementado um sistema de **logs centralizados**, que registra todas as operações críticas do sistema e possibilita um diagnóstico rápido de problemas inesperados.

🔹 **Compatibilidade entre Navegadores:** Durante os testes, foi identificado que algumas funcionalidades não se comportavam da mesma forma em diferentes navegadores. A solução foi realizar testes em múltiplos navegadores e ajustar o código, garantindo compatibilidade total com **Chrome, Firefox e Edge**.


---

## 📚 Referências

- [MySQL Documentation](https://dev.mysql.com/doc/)
- [FastAPI Docs](https://fastapi.tiangolo.com/)
- [Patterns of Enterprise Application Architecture – Martin Fowler](https://martinfowler.com/books/eaa.html)
- [IBM Developer – Understanding MVC Architecture](https://developer.ibm.com/articles/mvc-design-pattern/)
---

## 🏁 Conclusão

Este projeto consolidou os conhecimentos adquiridos durante o curso de Desenvolvimento de Software Multiplataforma, ao mesmo tempo em que permitiu a aplicação prática da arquitetura MVC em um sistema web real.

Com validações robustas, rotas bem definidas e organização clara, a aplicação está preparada para novas funcionalidades, como autenticação, dashboards e filtros personalizados.

> Desenvolvido por **Alef Chaves** e **Akemi Obana** – Fatec Itaquera
