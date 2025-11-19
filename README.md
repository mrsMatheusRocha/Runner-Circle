# 🏃‍♂️ Runner Circle — React + GraphQL

Bem-vindo ao **Runner Circle**! Este projeto é um exemplo moderno de consumo de APIs **GraphQL** via **React**, proporcionando uma interface amigável, eficiente e super escalável. Construído com **Vite** para máxima performance, Hot Module Replacement (HMR) instantâneo e boas práticas de desenvolvimento.

---

## 🚀 Tecnologias Principais

- **React** — Interfaces dinâmicas e responsivas.
- **GraphQL** — Queries & mutations ágeis para busca e manipulação de dados.
- **Apollo Client** — Integração fluida com APIs GraphQL no front-end.
- **Vite** — Bundler _ultra-rápido_ com experiência DX aprimorada.
- **JavaScript (97.6%)**, **CSS (1.2%)**, **HTML (1.2%)**

---

## ✨ Exemplo de uso: GraphQL + Apollo Client + React

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

---

## 🔥 Como rodar o projeto

1. **Instale as dependências:**
   ```bash
   npm install
   ```
2. **Inicie o servidor de desenvolvimento:**
   ```bash
   npm run dev
   ```
3. **Acesse:** [http://localhost:5173](http://localhost:5173) e veja a mágica acontecer 👀

---

## 🛠 Dicas e Expansão

- Utilize **TypeScript** para maior confiabilidade e produtividade.
- Configure **ESLint** com regras avançadas para garantir qualidade no código.
- Explore [Vite + React + TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) para turbinar seu setup.

---

## 🤝 Autor

Desenvolvido por [mrsMatheusRocha](https://github.com/mrsMatheusRocha) com 💙.  
Fique à vontade para contribuir ou dar aquele ⭐️ no repositório!

---
