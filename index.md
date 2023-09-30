## Guia de Estudos TypeScript <img width="24" height="24" src="https://img.icons8.com/external-tal-revivo-color-tal-revivo/24/external-typescript-an-open-source-programming-language-developed-and-maintained-by-microsoft-logo-color-tal-revivo.png" alt="external-typescript-an-open-source-programming-language-developed-and-maintained-by-microsoft-logo-color-tal-revivo"/>

Bem-vindo ao Guia de Estudos TypeScript! Este guia abrangente tem como objetivo fornecer um caminho estruturado para aprender TypeScript, uma linguagem de programação tipada e um superset do JavaScript. O TypeScript é amplamente utilizado no desenvolvimento web moderno, oferecendo segurança e produtividade. Vamos começar a explorar este universo emocionante.

## Conteúdo

1. Introdução ao TypeScript
   - O que é TypeScript?
   - Configuração do Ambiente
2. Tipos
   - Básicos
   - Primitivos
3. Estruturas de Dados
   - Arrays
   - Tuplas
4. Unions e Enums
   - Unions
   - Enums
5. Funções
   - Declaração de Funções
6. Interfaces e Classes
   - Interfaces
   - Classes
7. Generics
   - Generics
8. Promises
   - Promises
9. Manipulação de Erros
10. Módulos e Sistemas de Módulos
11. Decorações (Decorators)
12. Tipos Avançados
13. Integração com Outras Bibliotecas/Frameworks
14. Testes e TDD (Desenvolvimento Orientado a Testes)
15. Ferramentas de Desenvolvimento
16. Boas Práticas
17. Padrões de Projeto
18. Manipulação de Exceções

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

## 2. Tipos Básicos

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
    Down = 2
}
```

## 5. Funções

### 5.1 Declaração de Funções

Funções podem ser tipadas em relação aos parâmetros e ao valor de retorno:

```typescript
const sum = (x: number, y: number): string | number => {
    return (x + y).toString();
};
```

## 6. Interfaces e Classes

### 6.1 Interfaces

Interfaces definem contratos para objetos, podendo incluir campos opcionais e somente leitura:

```typescript
interface User {
    firstName: string;
    age: number;
    email: string;
    orders: Order[];
    register(): string;
}
```

### 6.2 Classes

Classes encapsulam dados, permitindo herança e implementação de interfaces:

```typescript
class Person implements IPerson {
    readonly id: number;
    protected name: string;
    private age: number;

    constructor(id: number, name: string, age: number) {
        this.id = id;
        this.name = name;
        this.age = age;
    }

    sayMyName(): string {
        return this.name;
    }
}
```

## 7. Generics

### 7.1 Generics

Generics permitem criar funções e classes parametrizadas por tipos:

```typescript
const returnValue = <T>(value: T): T => value;
```

## 8. Promises

### 8.1 Promises

Promises são usadas para lidar com operações assíncronas:

```typescript
const returnPromise = async (): Promise<number> => {
    return 5;
};
```

## 9. Manipulação de Erros

**Tratamento de erros e exceções em TypeScript**

O TypeScript permite o uso de blocos `try-catch` para lidar com exceções. Aqui está um exemplo simples:

```typescript
try {
    // Código que pode gerar uma exceção
    throw new Error("Isso é um erro de exemplo.");
} catch (error) {
    // Lidar com a exceção
    console.error("Ocorreu um erro:", error.message);
} finally {
    // Este bloco é executado independentemente de ocorrer uma exceção ou não.
    console.log("Finalizado.");
}
```

## 10. Módulos e Sistemas de Módulos

**Como organizar e importar/exportar módulos em TypeScript**

Em TypeScript, você pode usar o sistema de módulos CommonJS ou ES6. Aqui está um exemplo simples de exportação e importação de módulos:

**Módulo A (a.ts):**

```typescript
export const mensagem = "Olá do Módulo A!";
```

**Módulo B (b.ts):**

```typescript
import { mensagem } from "./a";

console.log(mensagem);
```

## 11. Decorações (Decorators)

**Uma introdução às decorações e como usá-las em classes**

Decorators são uma característica avançada do TypeScript. Aqui está um exemplo básico:

```typescript
function decoradorDeClasse(construtor: Function) {
    console.log("Classe decorada");
}

@decoradorDeClasse
class ExemploDecorado {
    constructor() {
        console.log("Instância da classe");


    }
}

const inst = new ExemploDecorado();
```

## 12. Tipos Avançados

**Tipos avançados, como tipos condicionais e inferência condicional de tipos**

```typescript
// Tipos condicionais
type Escolha<T> = T extends string ? "texto" : "outro tipo";
const escolha: Escolha<string> = "texto"; // "texto"

// Inferência condicional de tipos
function escolher<T extends boolean>(valor: T): T extends true ? "sim" : "não" {
    return valor as T extends true ? "sim" : "não";
}

const respostaSim = escolher(true); // "sim"
const respostaNao = escolher(false); // "não"
```

## 13. Integração com Outras Bibliotecas/Frameworks

**Como usar TypeScript em conjunto com bibliotecas populares**

A integração com outras bibliotecas/frameworks varia dependendo da biblioteca em questão. Por exemplo, para integrar o TypeScript com o React, você pode simplesmente configurar seu projeto para usar o TypeScript, como mencionado anteriormente.

## 14. Testes e TDD (Desenvolvimento Orientado a Testes)

**Práticas de teste em TypeScript e TDD**

Testar código TypeScript é semelhante ao JavaScript. Você pode usar bibliotecas de teste como Jest, Mocha ou Jasmine. Aqui está um exemplo simples usando Jest:

```typescript
// math.ts
export function somar(a: number, b: number): number {
    return a + b;
}

// math.test.ts
import { somar } from "./math";

test("soma 1 + 2 é igual a 3", () => {
    expect(somar(1, 2)).toBe(3);
});
```

## 15. Ferramentas de Desenvolvimento

**Uso de ferramentas populares, como o VSCode**

O Visual Studio Code (VSCode) é amplamente usado para desenvolvimento TypeScript. Não há código específico para mostrar aqui, mas você pode instalar extensões TypeScript no VSCode para melhorar a experiência de desenvolvimento.

## 16. Boas Práticas

**Recomendações gerais de boas práticas ao escrever código TypeScript**

Alguns princípios gerais incluem seguir as diretrizes do estilo de código TypeScript (por exemplo, usar camelCase para nomes de variáveis, PascalCase para nomes de classes, etc.) e manter o código limpo e organizado.

## 17. Padrões de Projeto

**Padrões de projeto comuns em TypeScript**

Exemplos de padrões de projeto em TypeScript incluem Singleton, Factory, Observer, entre outros. Os padrões de projeto são soluções comprovadas para problemas comuns de design de software.

## 18. Manipulação de Exceções

**Como lidar com exceções personalizadas em TypeScript**

Você pode criar exceções personalizadas estendendo a classe `Error`. Aqui está um exemplo:

```typescript
class MinhaExcecao extends Error {
    constructor(message: string) {
        super(message);
        this.name = "MinhaExcecao";
    }
}

try {
    throw new MinhaExcecao("Isso é uma exceção personalizada.");
} catch (error) {
    if (error instanceof MinhaExcecao) {
        console.error("Exceção personalizada capturada:", error.message);
    } else {
        console.error("Outra exceção capturada:", error.message);
    }
}
```

Esses são exemplos introdutórios para os tópicos adicionais que você pode incluir em sua documentação sobre TypeScript. Cada um desses tópicos pode ser aprofundado com exemplos mais complexos, dependendo das necessidades do seu guia de estudos.
```

Agora você tem a documentação completa e unificada pronta para ser usada no GitHub. Se tiver mais alguma pergunta ou precisar de mais assistência, sinta-se à vontade para perguntar!
