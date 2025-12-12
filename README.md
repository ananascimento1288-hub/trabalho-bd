# Projeto Escolar: Plataforma de Controle e Análise Acadêmica

**Disciplina:** Banco de Dados | **Professor:** Adeilson Sales Aragão  
**Instituição:** EEEP Manoel Mano - Curso Técnico em Informática

---

## 💡 Introdução e Objetivos

No cenário educacional atual, dados são essenciais. Este projeto visa criar não apenas um banco de dados, mas uma **Interface Gráfica de Usuário (GUI)** intuitiva que transforme dados brutos em informações visuais.

O sistema permite o cadastro completo de discentes e, através de scripts de automação, o banco de dados foi populado com **mais de 100 registros** para simular um ambiente de produção real. O foco principal é o **Dashboard de Business Intelligence (BI)**, que permite à gestão escolar tomar decisões baseadas em gráficos e estatísticas.

## 🖥️ Tour pelo Sistema

O front-end foi desenvolvido priorizando a limpeza visual e a facilidade de navegação, utilizando o framework **Bootstrap 5**.

### 1. Painel de Controle (Dashboard)
O coração do sistema. Aqui, o gestor tem acesso imediato aos indicadores chaves de desempenho (KPIs) e gráficos de distribuição.
![Visualização do Dashboard](./home.png)

### 2. Módulo de Cadastro
Interface amigável para inserção de dados, com validação de campos obrigatórios.
![Visualização do Cadastro](./caminho_para_imagem_cadastro.png)

### 3. Gestão de Registros
Tabela dinâmica que permite visualizar, editar e remover alunos do sistema, conectada diretamente ao banco MySQL.
![Visualização da Lista](./caminho_para_imagem_lista.png)

---

## ⚙️ Arquitetura de Dados (SQL)

A base do sistema é robusta e segura. Abaixo, a estrutura SQL utilizada para persistência dos dados.

**Tabela de Autenticação (`users`):**
Responsável por garantir que apenas pessoal autorizado acesse o sistema.

`CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    user_name VARCHAR(100) NOT NULL,
    user_email VARCHAR(150) NOT NULL UNIQUE,
    user_password VARCHAR(255) NOT NULL
);`

**Tabela Principal (`alunos`):**
Armazena dados pessoais, endereço e informações acadêmicas.

`CREATE TABLE alunos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    data_nascimento DATE NOT NULL,
    cidade VARCHAR(100),
    rua VARCHAR(255),
    bairro VARCHAR(100),
    numero VARCHAR(20),
    cep VARCHAR(10),
    nome_responsavel VARCHAR(255),
    tipo_responsavel VARCHAR(50),
    curso VARCHAR(100) NOT NULL,
    data_cadastro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);`

📈 Inteligência de Dados (As 10 Consultas)
O diferencial deste projeto é a capacidade de filtrar e cruzar dados. O sistema responde a perguntas complexas através de sua interface visual.

Painel de Filtros e KPIs: Visualização dos cards de contagem rápida e barra de ferramentas de filtragem.

Consultas Estratégicas:
Consulta 01: Qual a popularidade de cada curso? Gráfico de pizza demonstrando a porcentagem de alunos por área de estudo.

Consulta 02: Perfil dos alunos de Crateús Análise específica das matrículas provenientes da cidade sede.

Consulta 03: Mapeamento Geográfico Distribuição quantitativa de alunos por todas as cidades cadastradas.

Consulta 04: Origem dos alunos de Informática De onde vêm os estudantes interessados em tecnologia?

Consulta 05: Pirâmide Etária Geral Análise da faixa etária predominante na instituição.

Consulta 06: Pirâmide Etária (Informática) Comparativo de idade focado apenas no curso técnico de Informática.

Consulta 07: Prêmio "Curso do Ano" Sistema identifica e premia visualmente o curso com mais matrículas.

Consulta 08: Preferência em Jericoacoara Qual curso atrai mais alunos da região turística de Jijoca?

Consulta 09: Cidade Destaque Identificação do município com maior representatividade no corpo discente.

Consulta 10: Pólo Tecnológico Qual cidade (excluindo a sede) envia mais alunos para o curso de Informática?

🏁 Considerações Finais
Este projeto cumpre integralmente os requisitos propostos, demonstrando proficiência em PHP para lógica de negócios, SQL para manipulação de dados complexos e Bibliotecas Gráficas para visualização de dados. A implementação de um script de "seeding" para gerar 100 tuplas no banco foi fundamental para validar a escalabilidade das consultas apresentadas no dashboard.
