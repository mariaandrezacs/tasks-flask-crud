# Tasks Flask CRUD

Uma API REST simples desenvolvida com Flask para gerenciamento de tarefas, implementando operações CRUD (Create, Read, Update, Delete).

## 🚀 Funcionalidades

- **Criar** novas tarefas com título e descrição
- **Listar** todas as tarefas
- **Buscar** uma tarefa específica por ID
- **Atualizar** tarefas existentes (título, descrição e status)
- **Deletar** tarefas
- **Testes** automatizados com pytest

## 📋 Pré-requisitos

- Python 3.11 ou superior
- pip (gerenciador de pacotes Python)

## 🔧 Instalação

1. Clone o repositório:
```bash
git clone <repository-url>
cd tasks-flask-crud
```

2. Crie um ambiente virtual (opcional, mas recomendado):
```bash
python -m venv venv
```

3. Ative o ambiente virtual:
- Windows:
```bash
venv\Scripts\activate
```
- Linux/Mac:
```bash
source venv/bin/activate
```

4. Instale as dependências:
```bash
pip install -r requirements.txt
```

## 🏃 Executando a Aplicação

Inicie o servidor Flask:
```bash
python app.py
```

A API estará disponível em `http://127.0.0.1:5000`

## 📡 Endpoints da API

### Criar Tarefa
**POST** `/tasks`

**Body:**
```json
{
  "title": "Nova Tarefa",
  "description": "Descrição da tarefa"
}
```

**Resposta:**
```json
{
  "message": "Nova tarefa criada com sucesso",
  "id": 1
}
```

### Listar Todas as Tarefas
**GET** `/tasks`

**Resposta:**
```json
{
  "tasks": [
    {
      "id": 1,
      "title": "Nova Tarefa",
      "description": "Descrição da tarefa",
      "completed": false
    }
  ],
  "total_tasks": 1
}
```

### Buscar Tarefa por ID
**GET** `/tasks/<id>`

**Resposta:**
```json
{
  "id": 1,
  "title": "Nova Tarefa",
  "description": "Descrição da tarefa",
  "completed": false
}
```

### Atualizar Tarefa
**PUT** `/tasks/<id>`

**Body:**
```json
{
  "title": "Título Atualizado",
  "description": "Nova descrição",
  "completed": true
}
```

**Resposta:**
```json
{
  "message": "Tarefa atualizada com sucesso."
}
```

### Deletar Tarefa
**DELETE** `/tasks/<id>`

**Resposta:**
```json
{
  "message": "Tarefa deletada com sucesso."
}
```

## 🧪 Testes

Para executar os testes, certifique-se de que o servidor Flask esteja rodando em `http://127.0.0.1:5000`, então execute:

```bash
pytest tests.py -v
```

Os testes cobrem todas as operações CRUD:
- `test_create_task` - Criação de tarefa
- `test_get_tasks` - Listagem de tarefas
- `test_get_task` - Busca de tarefa específica
- `test_update_task` - Atualização de tarefa
- `test_delete_task` - Deleção de tarefa

## 📁 Estrutura do Projeto

```
tasks-flask-crud/
├── app.py              # Aplicação Flask principal com rotas CRUD
├── models/
│   └── task.py        # Modelo da classe Task
├── tests.py           # Testes de integração
├── requirements.txt   # Dependências do projeto
└── README.md          # Documentação
```

## 🛠️ Tecnologias Utilizadas

- **Flask** 2.3.0 - Framework web
- **Werkzeug** 2.3.0 - Biblioteca utilitária WSGI
- **requests** 2.31.0 - Biblioteca para requisições HTTP
- **pytest** 7.4.3 - Framework de testes

## 📝 Modelo de Dados

### Task
- `id`: Identificador único (int)
- `title`: Título da tarefa (string)
- `description`: Descrição da tarefa (string)
- `completed`: Status de conclusão (boolean, padrão: false)

## ⚠️ Observações

- Este projeto utiliza armazenamento em memória (lista Python), ou seja, os dados são perdidos ao reiniciar o servidor
- Para uso em produção, considere implementar persistência de dados (banco de dados)
- O servidor roda em modo debug para desenvolvimento

## 📄 Licença

Este projeto foi desenvolvido para fins educacionais.