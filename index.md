# Guia de Estudos TypeScript ![Logo TypeScript](https://img.icons8.com/external-tal-revivo-color-tal-revivo/24/external-typescript-an-open-source-programming-language-developed-and-maintained-by-microsoft-logo-color-tal-revivo.png)

Bem-vindo ao Guia de Estudos TypeScript! Este guia abrangente tem como objetivo fornecer um caminho estruturado para aprender TypeScript, uma linguagem de programação tipada e um superset do JavaScript. O TypeScript é amplamente utilizado no desenvolvimento web moderno, oferecendo segurança e produtividade. Vamos começar a explorar este universo emocionante.

## Conteúdo

1. Introdução ao TypeScript
   - 1.1 O que é TypeScript?
   - 1.2 Configuração do Ambiente
2. Tipos
   - 2.1 Tipos Primitivos
   - 2.2 Tipos Personalizados
3. Estruturas de Dados
   - 3.1 Arrays
   - 3.2 Tuplas
4. Unions e Enums
   - 4.1 Unions
   - 4.2 Enums
5. Funções
   - 5.1 Declaração de Funções
   - 5.2 Parâmetros de Função
   - 5.3 Valor de Retorno de Função
6. Interfaces e Classes
   - 6.1 Interfaces
   - 6.2 Classes
   - 6.3 Herança
   - 6.4 Modificadores de Acesso
7. Generics
   - 7.1 Introdução aos Generics
   - 7.2 Classes e Interfaces Genéricas
8. Promises
   - 8.1 Trabalhando com Promises
   - 8.2 Async/Await
9. Manipulação de Erros
   - 9.1 Tratamento de Exceções
   - 9.2 Lançamento de Exceções Personalizadas
10. Módulos e Sistemas de Módulos
    - 10.1 Importação e Exportação de Módulos
11. Decorações (Decorators)
    - 11.1 Introdução aos Decorators
    - 11.2 Decorators de Classe
    - 11.3 Decorators de Método
12. Tipos Avançados
    - 12.1 Tipos Condicionais
    - 12.2 Inferência de Tipos Condicionais
13. Integração com Outras Bibliotecas/Frameworks
    - 13.1 Integração com React
    - 13.2 Integração com Node.js
14. Testes e TDD (Desenvolvimento Orientado a Testes)
    - 14.1 Configurando o Ambiente de Testes
    - 14.2 Escrevendo Testes com Jest
    - 14.3 Práticas de TDD
15. Ferramentas de Desenvolvimento
    - 15.1 Visual Studio Code (VSCode)
    - 15.2 Extensões Úteis para TypeScript
16. Boas Práticas
    - 16.1 Convenções de Nomeação
    - 16.2 Comentários e Documentação
    - 16.3 Organização de Código
17. Padrões de Projeto
    - 17.1 Padrão Singleton
    - 17.2 Padrão Factory
    - 17.3 Padrão Observer
    - 17.4 Padrão Strategy
18. Manipulação de Exceções
    - 18.1 Exceções Personalizadas
    - 18.2 Lidando com Exceções
19. Estruturas de Repetição
    - 19.1 While Loop
    - 19.2 Do...While Loop
    - 19.3 For Loop
    - 19.4 For...of Loop
    - 19.5 For...in Loop

---

## 1. Introdução ao TypeScript

### 1.1 O que é TypeScript?

O TypeScript é uma linguagem de programação que adiciona **tipagem estática** ao JavaScript. Ele permite **detectar erros em tempo de compilação**, fornecendo maior segurança e ferramentas de desenvolvimento avançadas.

### 1.2 Configuração do Ambiente

Para começar a trabalhar com TypeScript, siga os passos abaixo:

- Instale o Node.js e o npm (Node Package Manager).
- Instale o TypeScript globalmente com o seguinte comando:

```bash
npm install -g typescript
```

## 2. Tipos

### 2.1 Tipos Primitivos

No TypeScript, você pode trabalhar com os seguintes tipos primitivos:

- `number`: Números.
- `string`: Texto.
- `boolean`: Valores verdadeiro ou falso.
- `null` e `undefined`: Valores nulos e indefinidos.
- `symbol`: Símbolos.

Aqui estão exemplos de declarações de variáveis com tipos explícitos:

```typescript
let age: number = 5;
const firstName: string = 'Desenvolvedor';
const isValid: boolean = true;
```

### 2.2 Tipos Personalizados

Você também pode criar tipos personalizados usando `type` ou `interface`. Exemplo:

```typescript
type User = {
  id: number;
  name: string;
};

const user: User = {
  id: 1,
  name: 'Alice',
};
```

## 3. Estruturas de Dados

### 3.1 Arrays

Os arrays no TypeScript podem ser declarados e tipados da seguinte forma:

```typescript
const ids: number[] = [1, 2, 3, 4, 5];
```

### 3.2 Tuplas

Tuplas permitem representar arrays com tipos específicos e tamanhos fixos:

```typescript
const person: [number, string] = [10, 'Desenvolvedor'];
```

## 4. Unions e Enums

### 4.1 Unions

Unions permitem combinar múltiplos tipos em uma variável:

```typescript
const productId: string | number = '12';
```

### 4.2 Enums

Enums são usados para definir valores constantes nomeados:

```typescript
enum Direction {
  Up = 1,
  Down = 2,
  Left = 3,
  Right = 4,
}
```

## 5. Funções

### 5.1 Declaração de Funções

Funções podem ser tipadas em relação aos parâmetros e ao valor de retorno:

```

typescript
function add(x: number, y: number): number {
  return x + y;
}
```

### 5.2 Parâmetros de Função

Os parâmetros de função podem ser opcionais ou padrão:

```typescript
function greet(name: string, age?: number): void {
  console.log(`Olá, ${name}! Você tem ${age || 'idade desconhecida'}.`);
}
```

### 5.3 Valor de Retorno de Função

Você pode especificar o tipo de valor de retorno de uma função:

```typescript
function multiply(x: number, y: number): number {
  return x * y;
}
```

## 6. Interfaces e Classes

### 6.1 Interfaces

Interfaces definem contratos para objetos, podendo incluir campos opcionais e somente leitura:

```typescript
interface User {
  id: number;
  name: string;
  email?: string;
  readonly createdAt: Date;
}
```

### 6.2 Classes

Classes encapsulam dados, permitindo herança e implementação de interfaces:

```typescript
class Person implements User {
  id: number;
  name: string;
  email?: string;
  readonly createdAt: Date;

  constructor(id: number, name: string, createdAt: Date) {
    this.id = id;
    this.name = name;
    this.createdAt = createdAt;
  }
}
```

### 6.3 Herança

Você pode criar classes que herdam de outras classes:

```typescript
class Student extends Person {
  studentId: number;

  constructor(id: number, name: string, createdAt: Date, studentId: number) {
    super(id, name, createdAt);
    this.studentId = studentId;
  }
}
```

### 6.4 Modificadores de Acesso

Os modificadores `public`, `private` e `protected` controlam o acesso aos membros da classe:

```typescript
class BankAccount {
  private balance: number;

  constructor(initialBalance: number) {
    this.balance = initialBalance;
  }

  deposit(amount: number): void {
    this.balance += amount;
  }

  withdraw(amount: number): void {
    if (amount <= this.balance) {
      this.balance -= amount;
    } else {
      console.log('Saldo insuficiente.');
    }
  }
}
```

## 7. Generics

### 7.1 Introdução aos Generics

Generics permitem criar funções e classes parametrizadas por tipos:

```typescript
function identity<T>(arg: T): T {
  return arg;
}

const numberValue: number = identity(5);
const stringValue: string = identity('hello');
```

### 7.2 Classes e Interfaces Genéricas

Você pode criar classes e interfaces genéricas:

```typescript
interface Box<T> {
  value: T;
}

const numberBox: Box<number> = { value: 42 };
const stringBox: Box<string> = { value: 'hello' };
```

## 8. Promises

### 8.1 Trabalhando com Promises

Promises são usadas para lidar com operações assíncronas:

```typescript
function fetchData(): Promise<string> {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Dados carregados com sucesso!');
    }, 2000);
  });
}

fetchData()
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error(error);
  });
```

### 8.2 Async/Await

O `async/await` simplifica o código assíncrono:

```typescript
async function fetchAndLogData(): Promise<void> {
  try {
    const data = await fetchData();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

fetchAndLogData();
```

## 9. Manipulação de Erros

### 9.1 Tratamento de Exceções

O TypeScript permite o uso de blocos `try-catch` para lidar com exceções:

```typescript
try {
  // Código que pode gerar uma exceção
  throw new Error('Isso é um erro de exemplo.');
} catch (error) {
  // Lidar com a exceção
  console.error('Ocorreu um erro:', error.message);
} finally {
  // Este bloco é executado independentemente de ocorrer uma exceção ou não.
  console.log('Finalizado.');
}
```

### 9.2 Lançamento de Exceções Personalizadas

Você pode criar exceções personalizadas estendendo a classe `Error`:

```typescript
class CustomError extends Error {
  constructor(message: string) {
    super(message);
    this.name = 'CustomError';
  }
}

try {
  throw new CustomError('Isso é uma exceção personalizada.');
} catch (error) {
  if (error instanceof CustomError) {
    console.error('Exceção personalizada capturada:', error.message);
  } else {
    console.error('Outra exceção capturada:', error.message);
  }
}
```

## 10. Módulos e Sistemas de Módulos

### 10.1 Importação e Exportação de Módulos

Você pode organizar seu código em módulos e exportar/importar funcionalidades:

**Módulo A (a.ts):**

```typescript
export const message = 'Olá do Módulo A!';
```

**Módulo B (b.ts):**

```typescript
import { message } from './a';

console.log(message);
```

## 11. Decorações (Decorators)

### 11.1 Introdução aos Decorators

Decorators são uma característica avançada do TypeScript. Aqui está um exemplo básico:

```typescript
function classDecorator(constructor: Function) {
  console.log('Classe decorada');
}

@classDecorator
class ExampleDecorated {
  constructor() {
    console.log('Instância da classe');
  }
}

const instance = new ExampleDecorated();
```

### 11.2 Decorators de Classe

Você pode criar decorators de classe para adicionar funcionalidades às classes:

```typescript
function logClass(target: Function) {
  console.log(`Classe: ${target.name}`);
}

@logClass
class Loggable {
  // ...
}
```

### 11.3 Decorators de Método

Decorators de método permitem modificar o comportamento de métodos:

```typescript
function logMethod(target: any, key: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value;
  descriptor.value = function (...args: any[]) {
    console.log(`Método chamado: ${key}`);
    return originalMethod.apply(this, args);
  };
}

class Example {
  @logMethod
  greet(name: string) {
    return `Olá, ${name}!`;
  }
}

const example = new Example();
console.log(example.greet('Alice'));
```

## 12. Tipos Avançados

### 12.1 Tipos Condicionais

Tipos condicionais permitem criar tipos com base em condições

:

```typescript
type Choice<T> = T extends string ? 'text' : 'other type';
const choice: Choice<string> = 'text'; // 'text'
```

### 12.2 Inferência de Tipos Condicionais

Você pode usar inferência de tipos condicionais em funções:

```typescript
function choose<T extends boolean>(value: T): T extends true ? 'yes' : 'no' {
  return value as T extends true ? 'yes' : 'no';
}

const responseYes = choose(true); // 'yes'
const responseNo = choose(false); // 'no'
```

## 13. Integração com Outras Bibliotecas/Frameworks

### 13.1 Integração com React

Para usar TypeScript com o React, configure seu projeto com as tipagens corretas e defina propriedades e estados tipados:

```typescript
import React, { useState } from 'react';

interface CounterProps {
  initialValue: number;
}

const Counter: React.FC<CounterProps> = ({ initialValue }) => {
  const [count, setCount] = useState<number>(initialValue);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Contagem: {count}</p>
      <button onClick={increment}>Incrementar</button>
    </div>
  );
};
```

### 13.2 Integração com Node.js

Para usar TypeScript com Node.js, configure seu projeto com as tipagens corretas e compile seu código TypeScript para JavaScript para executá-lo no ambiente Node.js.

## 14. Estruturas de Repetição

### 14.1 while

O loop `while` executa um bloco de código enquanto uma condição especificada for verdadeira:

```typescript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
```

### 14.2 do...while

O loop `do...while` executa um bloco de código pelo menos uma vez e, em seguida, repete o loop enquanto uma condição especificada for verdadeira:

```typescript
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 5);
```

### 14.3 for

O loop `for` é usado para iterar sobre um bloco de código várias vezes. Geralmente é usado quando você sabe quantas vezes deseja que o loop seja executado:

```typescript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

### 14.4 for...of

O loop `for...of` é usado para iterar sobre elementos iteráveis, como arrays:

```typescript
const colors = ['red', 'green', 'blue'];

for (const color of colors) {
  console.log(color);
}
```

### 14.5 for...in

O loop `for...in` é usado para iterar sobre as propriedades enumeráveis de um objeto:

```typescript
const person = {
  name: 'Alice',
  age: 30,
};

for (const key in person) {
  console.log(`${key}: ${person[key]}`);
}
```

## 15. Ferramentas de Desenvolvimento

### 15.1 Visual Studio Code (VSCode)

O Visual Studio Code (VSCode) é amplamente usado para desenvolvimento TypeScript. Você pode instalar extensões TypeScript no VSCode para melhorar a experiência de desenvolvimento.

### 15.2 Extensões Úteis para TypeScript

Algumas extensões úteis para TypeScript no VSCode incluem:
- `TypeScript TSLint Plugin`: Fornece linting e formatação para código TypeScript.
- `ESLint`: Fornece linting para JavaScript e TypeScript.
- `Prettier`: Formata automaticamente seu código.
- `Jest`: Suporte para testes Jest.

## 16. Boas Práticas

### 16.1 Convenções de Nomeação

Siga as convenções de nomeação TypeScript, como camelCase para nomes de variáveis e PascalCase para nomes de classes.

### 16.2 Comentários e Documentação

Documente seu código usando comentários descritivos e forneça documentação para funções, classes e métodos.

### 16.3 Organização de Código

Organize seu código de forma clara e mantenha uma estrutura de diretórios bem definida.

## 17. Padrões de Projeto

### 17.1 Padrão Singleton

O Padrão Singleton garante que uma classe tenha apenas uma instância e fornece um ponto global de acesso a essa instância.

### 17.2 Padrão Factory

O Padrão Factory cria objetos com base em uma interface e permite que as subclasses decidam qual classe instanciar.

### 17.3 Padrão Observer

O Padrão Observer permite que um objeto (sujeito) notifique seus observadores quando seu estado muda.

### 17.4 Padrão Strategy

O Padrão Strategy define uma família de algoritmos, encapsula cada um deles e torna-os intercambiáveis.

## 18. Manipulação de Exceções

### 18.1 Exceções Personalizadas

Você pode criar exceções personalizadas estendendo a classe `Error` e lançá-las em situações específicas.

### 18.2 Lidando com Exceções

Use blocos `try-catch` para lidar com exceções e trate-as de acordo com a necessidade do seu programa.

Isso conclui o Guia de Estudos TypeScript! Continue explorando os tópicos e praticando para se tornar um desenvolvedor TypeScript experiente. Boa sorte!
