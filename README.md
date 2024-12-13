## Sorteio de Amigo Secreto

Este script em Python realiza o sorteio de amigo secreto, garantindo que não haja autoatribuição (ou seja, ninguém tira a si mesmo) e permite incluir restrições personalizadas. Além disso, oferece a opção de enviar os resultados por e-mail.

## Funcionalidades

- Recebe uma lista de participantes e seus e-mails.
- Permite configurar restrições (quem não pode tirar quem).
- Realiza o sorteio de maneira justa e aleatória.
- Garante que ninguém tire a si mesmo ou viole as restrições.
- Envia os resultados por e-mail automaticamente.

## Pré-requisitos

- Python 3.7 ou superior.
- Bibliotecas:
  - `random` (padrão do Python)
  - `smtplib` (padrão do Python)
  - `email` (padrão do Python)

## Como usar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/amigo-secreto.git
   cd amigo-secreto
   ```

2. Edite o arquivo do script para incluir os seguintes dados:

   - **Lista de participantes e seus e-mails:**
     ```python
     nomes_emails = {
         "Mariana": "mariana@gmail.com",
         "Julia": "julia@hotmail.com",
         "João": "joao@hotmail.com",
         "Flavio": "flavioi@gmail.com",
          "Regis": "regis@hotmail.com",
          "Tiago": "tiago@gmail.com",
          "Gustavo": "gu@gmail.com",
          "Ana": "ana@outlook.com",
          "Pedro": "pedro@gmail.com",
          "Gabi": "gabi@gmail.com"
     }
     ```

   - **Restrições (opcional):**
     ```python
     restricoes = {
         "Tiago": ["Julia"],
         "Gabi": ["Ana"],
         "Pedro": ["Mariana"]
     }
     ```

   - **Credenciais do e-mail remetente:**
     ```python
     email_remetente = "seu_email@gmail.com"
     senha_remetente = "sua_senha"
     ```

3. Execute o script:
   ```bash
   python amigo_secreto.py
   ```

O script realizará o sorteio e enviará e-mails com os resultados para cada participante.

## Estrutura do Código

### Funções principais

- **`sortear_amigo_secreto(nomes, restricoes)`**
  - Argumentos:
    - `nomes` (list): Lista de strings com os nomes dos participantes.
    - `restricoes` (dict): Dicionário onde as chaves são nomes e os valores são listas de quem o participante não pode tirar.
  - Retorna: Um dicionário onde as chaves são os participantes e os valores são seus respectivos "amigos secretos".
  - Garante que nenhuma restrição seja violada.

- **`enviar_email(amigo, sorteado, email_amigo, email_remetente, senha_remetente)`**
  - Argumentos:
    - `amigo` (str): Nome do participante.
    - `sorteado` (str): Nome do amigo secreto do participante.
    - `email_amigo` (str): E-mail do participante.
    - `email_remetente` (str): E-mail do remetente.
    - `senha_remetente` (str): Senha do e-mail do remetente.
  - Envia um e-mail para o participante informando quem ele tirou no sorteio.

### Exemplo de uso

```python
nomes_emails = {
    "Alice": "alice@gmail.com",
    "Bob": "bob@gmail.com",
    "Carol": "carol@gmail.com"
}

restricoes = {
    "Alice": ["Bob"],
    "Bob": ["Alice"]
}

email_remetente = "seu_email@gmail.com"
senha_remetente = "sua_senha"

resultado = sortear_amigo_secreto(list(nomes_emails.keys()), restricoes)

for amigo, sorteado in resultado.items():
    enviar_email(amigo, sorteado, nomes_emails[amigo], email_remetente, senha_remetente)
```

## Personalização

- **Entrada de dados:** você pode alterar a forma como os participantes são inseridos (por exemplo, carregar de um arquivo CSV ou permitir entrada manual).
- **Envio de e-mails:** ajuste o servidor de e-mail e porta, caso necessário.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo `LICENSE` para obter mais informações.

---

### Contato

Criado por [Régis](https://github.com/regisbarbosa). Entre em contato para sugestões ou melhorias!
