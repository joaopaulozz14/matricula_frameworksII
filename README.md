# Sistema de Gerenciamento Acadêmico

## 📚 Sobre o Projeto

Este projeto consiste em um sistema de gerenciamento acadêmico desenvolvido utilizando **Spring Boot**, com o objetivo de realizar o controle de alunos, cursos e matrículas.

A aplicação permite cadastrar alunos, cadastrar cursos e gerenciar as matrículas dos alunos nos cursos, utilizando uma arquitetura baseada no padrão **MVC (Model-View-Controller)**.

O projeto foi desenvolvido como parte dos estudos da disciplina de **Linguagem de Programação 3**, aplicando conceitos de desenvolvimento backend com Java, persistência de dados e ORM.

---

## 🚀 Tecnologias Utilizadas

* Java 21
* Spring Boot
* Spring MVC
* Spring Data JPA
* Hibernate
* Thymeleaf
* Bootstrap
* MySQL
* Maven

---

## 🏗️ Arquitetura do Projeto

O projeto segue uma organização baseada no padrão MVC:

```
src/main/java
│
├── controller
│   └── Responsável pelas requisições HTTP
│
├── model
│   └── Entidades JPA do sistema
│
├── repository
│   └── Comunicação com o banco de dados
│
└── service
    └── Regras de negócio da aplicação
```

---

# 📌 Funcionalidades

## 👨‍🎓 Gerenciamento de Alunos

* Cadastro de alunos
* Listagem de alunos cadastrados
* Alteração de dados
* Remoção de alunos

---

## 📖 Gerenciamento de Cursos

* Cadastro de cursos
* Visualização dos cursos disponíveis
* Atualização de informações
* Exclusão de cursos

---

## 📝 Gerenciamento de Matrículas

* Cadastro de matrícula de alunos em cursos
* Associação entre aluno e curso
* Controle de status da matrícula
* Registro da data de matrícula

---

# 🗄️ Modelo de Dados

O sistema possui três principais entidades:

## Aluno

Representa os estudantes cadastrados no sistema.

Relacionamento:

```
Aluno 1 -------- N Matrícula
```

Um aluno pode possuir várias matrículas.

---

## Curso

Representa os cursos disponíveis.

Relacionamento:

```
Curso 1 -------- N Matrícula
```

Um curso pode possuir vários alunos matriculados.

---

## Matrícula

Responsável por relacionar alunos e cursos.

Possui informações como:

* Data da matrícula
* Status da matrícula
* Aluno associado
* Curso associado

---

# 🔗 Relacionamentos JPA

Foi utilizado o Hibernate para realizar o mapeamento objeto-relacional.

Exemplo:

```java
@OneToMany(
    mappedBy = "alunoModel",
    fetch = FetchType.LAZY
)
private List<MatriculaModel> matriculas;
```

O carregamento **LAZY** foi utilizado para evitar consultas desnecessárias ao banco de dados, carregando informações relacionadas somente quando forem realmente necessárias.

---

# ⚙️ Como executar o projeto

## Pré-requisitos

Antes de iniciar, tenha instalado:

* Java 21+
* Maven
* MySQL

---

## 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

---

## 2. Configure o banco de dados

Crie um banco MySQL:

```sql
CREATE DATABASE sistema_academico;
```

---

## 3. Configure o arquivo application.properties

Exemplo:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/sistema_academico

spring.datasource.username=root

spring.datasource.password=sua_senha


spring.jpa.hibernate.ddl-auto=update

spring.jpa.show-sql=true
```

---

## 4. Execute a aplicação

Pelo Maven:

```bash
mvn spring-boot:run
```

Ou execute a classe principal:

```
Lp3SpringApplication.java
```

---

# 🌐 Endpoints Principais

## Alunos

| Método | Endpoint           | Descrição           |
| ------ | ------------------ | ------------------- |
| GET    | /alunos            | Lista alunos        |
| GET    | /cadastroaluno     | Formulário cadastro |
| POST   | /salvaraluno       | Salva aluno         |
| GET    | /editaraluno/{id}  | Edita aluno         |
| GET    | /removeraluno/{id} | Remove aluno        |

## Cursos

| Método | Endpoint     | Descrição    |
| ------ | ------------ | ------------ |
| GET    | /cursos      | Lista cursos |
| POST   | /salvarcurso | Salva curso  |

## Matrículas

| Método | Endpoint         | Descrição        |
| ------ | ---------------- | ---------------- |
| POST   | /salvarmatricula | Cria matrícula   |
| GET    | /matriculas      | Lista matrículas |

---

# 🖥️ Interface

A interface foi desenvolvida utilizando:

* Thymeleaf para renderização das páginas
* Bootstrap para estilização dos componentes

Principais telas:

* Cadastro de alunos
* Cadastro de cursos
* Cadastro de matrículas
* Listagem dos registros

---

# 📌 Conceitos Aplicados

Durante o desenvolvimento foram aplicados:

✅ Programação Orientada a Objetos
✅ Spring MVC
✅ Injeção de Dependência
✅ JPA/Hibernate ORM
✅ Relacionamentos entre entidades
✅ CRUD completo
✅ Persistência em banco de dados
✅ Mapeamento LAZY/EAGER
✅ Validação de dados

---

# 👨‍💻 Autor

Desenvolvido por **João Paulo**

Projeto acadêmico desenvolvido para estudos de desenvolvimento backend com Java e Spring Boot.
