
# Cadastro de Usuários com Django

Este projeto é uma aplicação web simples para cadastro de usuários, desenvolvida com Django. O projeto permite que os usuários sejam cadastrados e listados em uma página. 

## Referência
Este projeto foi baseado no vídeo do YouTube: [Como criar uma aplicação Django do zero](https://www.youtube.com/watch?v=-m5ywU8SW9E).

## O que foi feito

- Criação de um modelo de usuário com campos para nome e idade.
- Implementação de views para exibir a página inicial e a lista de usuários.
- Formulário para inserir novos usuários com validação CSRF.
- Listagem dos usuários cadastrados em uma tabela.

## Tecnologias usadas

- [Django](https://www.djangoproject.com/) - Framework web utilizado.
- [Bootstrap](https://getbootstrap.com/) - Framework CSS para estilização.

## Dificuldades encontradas e resolvidas

Durante o desenvolvimento deste projeto, enfrentei algumas dificuldades que exigiram pesquisa e resolução. Aqui estão as principais questões que encontrei e como as resolvi:

1.  **Erro de CSRF (Cross Site Request Forgery)**:
    
    -   **Descrição**: Ao tentar enviar o formulário para cadastrar um novo usuário, recebi uma mensagem de erro indicando que o token CSRF estava ausente. Isso acontece porque o Django protege as aplicações web contra ataques CSRF.
    -   **Solução**: Adicionei o tag `{% csrf_token %}` dentro do formulário HTML. Essa tag gera um token que é enviado com a requisição POST, garantindo que o servidor reconheça a solicitação como legítima.
2.  **Problemas de Renderização no HTML**:
    
    -   **Descrição**: Encontrei um erro de DOM que indicava que havia uma tag `<div>` fechando de forma inesperada. Isso pode acontecer por causa de uma estrutura de HTML mal formada.
    -   **Solução**: Revisei o código HTML, especialmente a estrutura de tags. Verifiquei se todas as tags estavam abertas e fechadas corretamente e certifiquei-me de que não havia tags aninhadas de maneira errada.
3.  **Visualização do ID do Usuário**:
    
    -   **Descrição**: Após cadastrar um novo usuário, percebi que o ID não estava sendo exibido na página de listagem de usuários.
    -   **Solução**: Corrigi o loop no template `usuarios.html`, certificando-me de que a variável utilizada para acessar o ID era a correta (`{{ usuario.id }}`.
4.  **Limpeza do Banco de Dados**:
    
    -   **Descrição**: Ao desenvolver e testar a aplicação, percebi que o banco de dados acumulava muitos dados de teste, dificultando a visualização dos resultados.
    -   **Solução**: Criei um comando de gerenciamento personalizado no Django para limpar o banco de dados. Isso permitiu que eu removesse todos os registros da tabela de usuários de forma rápida e fácil, permitindo um ambiente de teste mais limpo.

Essas dificuldades me ajudaram a entender melhor como o Django funciona e como aplicar as melhores práticas ao desenvolver aplicações web. A resolução desses problemas não só melhorou a funcionalidade do meu aplicativo, mas também ampliou meu conhecimento sobre as ferramentas e recursos disponíveis no Django.

## Como rodar o programa

1. Clone o repositório: Clone o repositório
 ``` git clone https://github.com/agraziella/sistema-cadastro.git ```
 

2. Crie um ambiente virtual e ative-o

```python -m venv venv ```

```source venv/bin/activate``` *# Para Linux/Mac*

```venv\Scripts\activate ```*# Para Windows*

4. Instale as dependências
```pip install django``` 

5. Execute as migrações do banco de dados
```python manage.py migrate``` 

6. Inicie o servidor
```python manage.py runserver``` 

7. Acesse a aplicação no seu navegador 
