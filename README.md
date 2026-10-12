# DevBills — estudos de TypeScript

Projeto de estudos para praticar TypeScript enquanto desenvolvo o **DevBills**. A trilha cobre a configuração do ambiente, os principais recursos da linguagem e a compreensão do projeto, incluindo a integração com Firebase.

> As anotações e explicações completas estão nas páginas do Notion. Este README funciona como índice de estudo e guia inicial do repositório.

## Conteúdo de estudo

1. [Introdução ao TypeScript](https://app.notion.com/p/Introdu-o-ao-TypeScript-24c71704b67381c88257c0b12fc8f53f)
2. [Configurando o TypeScript](https://app.notion.com/p/Configurando-o-TypeScript-24c71704b673817fb5bbdcf49cfa9e99)
3. [Instalando o tsx](https://app.notion.com/p/Instalando-o-tsx-24c71704b673813583b7f187d083f5e5)
4. [Tipagem estática](https://app.notion.com/p/1-Tipagem-Est-tica-24c71704b67381aa947ed8a99fbb86ec)
5. [Interfaces e tipos personalizados](https://app.notion.com/p/2-Interfaces-e-Tipos-Personalizados-24c71704b673813ea42dc7dbfdb0cae0)
6. [Enums](https://app.notion.com/p/3-Enums-24c71704b673819394dfeaf48f7d9a40)
7. [Generics](https://app.notion.com/p/4-Generics-24c71704b6738114ad57f9220eb5e09a)
8. [Utility Types](https://app.notion.com/p/5-Utility-Types-24c71704b67381c48364e2a5ab938eb5)
9. [Entendendo o projeto](https://app.notion.com/p/Entendendo-o-projeto-24c71704b67381e38c9ee843bc168b6f)
10. [Firebase](https://app.notion.com/p/Firebase-24c71704b67381348ea7c4cf30a6c0bd)

## Conceitos para praticar

### Tipagem estática

Tipos ajudam a documentar os dados esperados e permitem encontrar incompatibilidades durante o desenvolvimento.

```ts
const formatCurrency = (amount: number): string =>
  new Intl.NumberFormat("pt-BR", {
    style: "currency",
    currency: "BRL",
  }).format(amount);
```

### Interfaces e tipos

Use tipos para descrever os dados do domínio do projeto e mantenha as estruturas reutilizáveis.

```ts
interface Transaction {
  id: string;
  description: string;
  amount: number;
  date: Date;
}

type TransactionStatus = "pending" | "completed";
```

### Generics e Utility Types

Generics permitem criar funções e estruturas reutilizáveis sem perder a informação dos tipos. Utility Types ajudam a transformar tipos existentes.

```ts
function first<T>(items: T[]): T | undefined {
  return items[0];
}

type NewTransaction = Omit<Transaction, "id">;
type TransactionUpdate = Partial<Transaction>;
```

## Começando o projeto

Requisitos: Node.js e npm instalados.

```bash
npm init -y
npm install --save-dev typescript tsx @types/node
npx tsc --init
```

Crie `src/index.ts` para o código inicial e adicione estes scripts em `package.json`:

```json
{
  "scripts": {
    "dev": "tsx src/index.ts",
    "typecheck": "tsc --noEmit"
  }
}
```

Execute o projeto e confira os tipos:

```bash
npm run dev
npm run typecheck
```


