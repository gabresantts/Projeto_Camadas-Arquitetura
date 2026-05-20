# Projeto_Camadas-Arquitetura
Objetivo da atividade: identificar as atribuições/responsabilidades de cada camada da arquitetura.

# Atividade Prática: Arquitetura em Camadas
 
Projeto desenvolvido como atividade prática para demonstrar o funcionamento da arquitetura em camadas, adicionando o campo **telefone** ao sistema de usuários de ponta a ponta.
 
---
 
## Sobre a Atividade
 
A feature implementada percorre todas as camadas da aplicação:
 
```
Cliente → Apresentação → Serviço → Repositório → Banco de Dados
                                                        ↓
Cliente ← Apresentação ← Serviço ← Repositório ← Banco de Dados
```
 
> **Importante:** as atividades devem ser feitas em ordem (1 → 2 → 3 → 4 → 5), pois cada camada depende da anterior.
 
---
 
## Camadas Implementadas
 
| Camada       | Arquivo                                    | Responsabilidade                  |
|--------------|--------------------------------------------|-----------------------------------|
| Dados        | `dados/db.py`                              | Estrutura do banco de dados       |
| Domínio      | `dominio/usuario.py`                       | Regras de negócio e validações    |
| Repositório  | `repositorio/repositorio_usuario.py`       | Operações SQL (CRUD)              |
| Serviço      | `servico/servico_usuario.py`               | Orquestração das operações        |
| Apresentação | `apresentacao/rotas_usuario.py`            | Endpoints da API REST             |
 
---
 
## Como Rodar
 
### 1. Instalar dependências
 
```bash
pip install -r requirements.txt
```
 
### 2. Resetar o banco (apenas na primeira vez)
 
```bash
python
>>> from dados.db import resetar_banco
>>> resetar_banco()
>>> exit()
```
 
### 3. Iniciar o servidor
 
```bash
python app.py
```
 
O servidor estará disponível em `http://localhost:5000`
 
---
 
## Endpoints
 
| Método   | Rota                  | Descrição        |
|----------|-----------------------|------------------|
| `POST`   | `/api/usuarios`       | Cadastrar usuário |
| `GET`    | `/api/usuarios`       | Listar todos      |
| `GET`    | `/api/usuarios/<id>`  | Buscar por ID     |
| `PUT`    | `/api/usuarios/<id>`  | Atualizar usuário |
| `DELETE` | `/api/usuarios/<id>`  | Deletar usuário   |
 
---
 
## Tecnologias
 
- **Python**
- **Flask**
- **SQLite**
