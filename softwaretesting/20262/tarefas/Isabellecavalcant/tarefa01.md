# Tarefa 01 - Teste de Unidade, Integração, Cobertura e CI

**Nome:** Isabelle Cavalcanti da Silva  
**Usuário GitHub:** [Isabellecavalcant](https://github.com/Isabellecavalcant)  
**E-mail:** euisabellecavalcanti@gmail.com  
**Repositório do projeto:** [Sistema HBL Control — PNLD](https://github.com/HelenaMariano2025/projetoPNLD)

## 9. Pesquisa sobre testes de software

### I. Testes de software e testes de unidade

Testes de software verificam se uma funcionalidade apresenta o comportamento esperado e ajudam a identificar defeitos quando o código é alterado. Testes de unidade examinam uma parte pequena do programa, como um método, de forma isolada. No CRUD de livros, por exemplo, podemos verificar se o método de cadastro prepara os dados e retorna o resultado esperado, simulando a conexão com o banco. Esses testes não substituem os testes de integração, que verificam o funcionamento conjunto do código e do banco de dados.

### II. Linguagem e stack

O projeto escolhido é o Sistema HBL Control (PNLD). A linguagem é **PHP** e a stack utilizada inclui **MySQL** para armazenar os dados, **MySQLi** para a comunicação com o banco, **Composer** para gerenciar dependências e **PHPUnit** para os testes automatizados. A interface utiliza HTML, CSS e JavaScript. Nesta tarefa, o CRUD selecionado é o de livros.

### III. Framework de testes de unidade

O framework escolhido é o **PHPUnit**, utilizado para escrever e executar testes em PHP. Com ele, criamos métodos de teste e usamos asserções para comparar o resultado obtido com o esperado. O PHPUnit também permite criar objetos simulados (*mocks*) para testar uma classe sem depender de uma conexão real com o MySQL. O projeto PNLD já utiliza PHPUnit em seus testes.

- [Site e documentação do PHPUnit](https://phpunit.de/)
- [Manual do PHPUnit: criação de testes](https://docs.phpunit.de/en/12.5/writing-tests-for-phpunit.html)
- [Manual do PHPUnit: objetos simulados](https://docs.phpunit.de/en/12.5/test-doubles.html)

### IV. IDE e ferramentas de depuração

Utilizo o **Visual Studio Code**. Sua área *Run and Debug* permite definir pontos de parada (*breakpoints*), acompanhar a execução linha por linha, inspecionar variáveis e expressões, consultar a pilha de chamadas e usar o console de depuração. Para depurar código PHP em execução, é necessário configurar um depurador compatível, como o **Xdebug**, com uma extensão apropriada no VS Code.

- [Documentação de depuração do Visual Studio Code](https://code.visualstudio.com/docs/debugtest/debugging)

### V. Referência de CRUD com testes

Como referência prática, consultei o projeto [PHP CRUD Users API](https://github.com/jonsanchezr/php-crud-users-api). Ele apresenta uma API CRUD em PHP, configuração de MySQL e Composer, código de testes na pasta `tests` e instruções para executar os testes com `composer test`. A estrutura ajuda a observar como organizar operações de cadastro e seus testes. O PNLD utiliza sua própria implementação em PHP e MySQLi; a referência não foi copiada diretamente para o projeto.

### VI. Mock Objects

Um *mock object* é um objeto criado para substituir uma dependência durante um teste e verificar como o código interage com ela. No PHPUnit, `createMock()` permite configurar respostas e expectativas sobre chamadas de métodos. Por exemplo, em um teste de unidade do cadastro de livros, podemos simular `mysqli` e `mysqli_stmt` e verificar se a operação chama `prepare()` e `execute()` como esperado, sem acessar um banco real. Para verificar a gravação no MySQL, fazemos separadamente um teste de integração.

- [Manual do PHPUnit: Test Doubles](https://docs.phpunit.de/en/12.5/test-doubles.html)