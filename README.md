# Runner Circle - React + GraphQL

Este projeto utiliza **React** com foco em consumo de APIs via **GraphQL**, proporcionando uma interface moderna, eficiente e escalável. A estrutura foi iniciada com Vite para aproveitamento de Hot Module Replacement (HMR) e algumas regras de ESLint.

## Principais Tecnologias

- **React**: construção de interfaces dinâmicas e responsivas.
- **GraphQL**: busca, criação e modificação de dados por meio de queries e mutations otimizadas.
- **Apollo Client** (sugestão): para integração com GraphQL no front-end.
- **Vite**: bundler rápido que facilita o desenvolvimento com React.
- **JavaScript (97,6%)**, **CSS (1,2%)**, **HTML (1,2%)**

## Exemplo de uso do GraphQL com React

```jsx
import { ApolloClient, InMemoryCache, ApolloProvider, useQuery, gql } from '@apollo/client';

const client = new ApolloClient({
  uri: 'https://sua-api-graphql.com/graphql',
  cache: new InMemoryCache()
});

const GET_USERS = gql`
  query GetUsers {
    users {
      id
      name
    }
  }
`;

function Users() {
  const { loading, error, data } = useQuery(GET_USERS);

  if (loading) return <p>Carregando...</p>;
  if (error) return <p>Erro :(</p>;

  return (
    <ul>
      {data.users.map(({ id, name }) => (
        <li key={id}>{name}</li>
      ))}
    </ul>
  );
}

function App() {
  return (
    <ApolloProvider client={client}>
      <Users />
    </ApolloProvider>
  );
}
```

## Como rodar

1. Instale as dependências:
   ```
   npm install
   ```
2. Inicie o servidor de desenvolvimento:
   ```
   npm run dev
   ```

## Expansão

Recomenda-se utilizar TypeScript e configurar regras avançadas no ESLint para produção. Consulte o [template TS do Vite](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) para referências.

---
Projeto desenvolvido por [mrsMatheusRocha](https://github.com/mrsMatheusRocha).
