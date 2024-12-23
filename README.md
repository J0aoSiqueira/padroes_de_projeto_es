# padroes_de_projeto_es

# Padrões de Projeto 

**Atenção**: Este texto contém uma tradução livre dos artigos publicados do site Refactoring Guru, que contém os códigos e as explicações originadas em inglês.

Os Padrões de Projeto (ou Design Patterns, em inglês) são soluções típicas para os problemas comuns em design de software. Dentro desta área, existem três tipos de padrões de projeto:

- **Criacionais**: São padrões que fornecem vários mecanismos de criação de objetos, que aumentam a flexibilidade e a reutilização do código existente;

- **Estruturais**: São padrões que servem para estudar o comportamento ou método de um objeto e como este objeto pode se unir em estruturas maiores, enquanto mantém as estruturas flexíveis e eficientes;

- **Comportamentais**: São padrões que estão preocupados com os algoritmos e com a atribuição de responsabilidades entre os objetos, portanto eles estudam o comportamento ou método de um objeto.

## Padrão de Projeto Criacional: Singleton

O **Singleton** é um padrão de projeto criacional que permite a você garantir que uma classe tenha apenas uma instância, enquanto fornece um ponto de acesso global para essa instância.

### Problemas e Solução
O Singleton serve para solucionar dois problemas, ao passo que ela viola o Príncipio de Responsabilidade Única do SOLID:

1. Garante que uma classe tenha apenas uma única instância, sendo dispensável a utilização de inúmeras instâncias de uma mesma classe;

2. Fornece um ponto de acesso global para essa instância, o que mantém ela seguro dela ser reescrita por um outro código.

Para isso, as implementações do Singleton tem dois passos em comum:

- Faz o construtor padrão da classe private, previnindo outros objetos de usar o operador ```new``` com a classe Singleton;
- Cria um método de criação estático que age como um construtor. Por baixo dos panos, este método chama o construtor privado para criar um objeto e o salva no campo estático. As chamadas posteriores para este método retornam o objeto instânciado.

### Estrutura
[[Singleton/structure-en-indexed.png]]
Nesta estrutura, a classe Singleton declara o método estático ```getInstance``` que retorna a instância da própria classe. Dessa forma, o construtor deveria estar escondido do código tradicional, sendo o método a única forma de se obter o objeto Singleton.

### Exemplo de código
[[Singleton/image.png]]
Neste exemplo de código em TypeScript (TS), a classe Singleton cria uma instância estática do objeto Singleton, dessa forma, mantém o construtor da classe privado e a obtenção da instância pública, que faz uma condicional em que se a instância não existir, deve criar uma instância nova a partir do construtor. Após definir algumas lógicas para o código, a instância é retornada para a função, em que neste exemplo, é criado duas variáveis para garantir as duas possuam a mesma instância com as mesmas variáveis, retornando no final:

```Singleton works, both variables contain the same instance.```
