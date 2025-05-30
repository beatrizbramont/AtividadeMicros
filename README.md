# 📚 API de Atividades 

Este repositório contém a **API de Atividades**, desenvolvida com **Flask** e **SQLAlchemy**, como parte de uma arquitetura baseada em **microsserviços**.

## 🧩 Arquitetura

A API de Atividades é um **microsserviço** que faz parte de um sistema maior de [School System](https://github.com/beatrizbramont/ProjetoAPI.git)
, sendo responsável exclusivamente pelo gerenciamento das atividades que o professor passa para seus alunos.

⚠️ **Esta API depende de outra API de Gerenciamento Escolar (School System)**, que deve estar em execução e exposta localmente. A comunicação entre os serviços ocorre via **requisições HTTP REST**, para validar:

- Se o **Professor** existe (`GET /professor/<id>`)

---

## 🚀 Tecnologias Utilizadas

- Python 3.x;
- Flask;
- SQLAlchemy;
- SQLite (como banco de dados local);
- Requests (para consumo da API externa).

---

## ▶️ Como Executar a API

### 1. Clone o repositório

```bash
git clone https://github.com/beatrizbramont/AtividadeMicros.git
cd AtividadeMicros
```

### 2. Crie um ambiente virtual (opcional, mas recomendado)

```bash
python3 -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Execute a API

```bash
python app.py
```

A aplicação estará disponível em:
📍 `http://127.0.0.1:5000`

📝 **Observação:** O banco de dados é criado automaticamente na primeira execução.

---

## 📡 Endpoints Principais

- `GET /atividades` – Lista todas as atividades
- `POST /atividades` – Cria uma nova atividade
- `GET /atividades/<id>` – Detalha uma atividade


### Exemplo de corpo JSON para criação:

```json
{
  "professor_id": 1,
  "tipo": "Atividade",
  "data_entrega": "2025-10-08",
  "titulo": "Mil beijos de garoto",
  "descricao": "Romance"
}
```

---

## 🔗 Dependência Externa

Certifique-se de que a **API de Gerenciamento Escolar** esteja rodando em:

```
http://127.0.0.1:8001
```

E que o endpoint de `GET /professor/<id>` corretamente para que a validação seja feita com sucesso.

---

## 📦 Estrutura do Projeto

```
AtividadeMicros/
│
├── controller/
│   └── ativ_controller.py      
│
├── instance/
│   └── atividades.db           
│
├── models/
│   └── ativ_model.py      
│
├── app.py                    
├── config.py                 
├── database.py               
├── Dockerfile 
├── README.md               
└── requirements.txt          


```

---

## 🛠️ Futuras Melhorias

- Integração via fila (RabbitMQ) com outros microsserviços;
- Autenticação de usuários;
- Inserção das rotas PUT e DELETE (`PUT /atividades/<id>` – Atualiza uma atividade
                                   `DELETE /atividades/<id>` – Remove uma atividade).

---

## 🧑‍💻 Autores

- Beatriz Bramont 
- Isadora Silva
- Giovanna Petrilli