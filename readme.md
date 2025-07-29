# 🎧 PodCast Manager

Um app ao estilo Netflix para organizar, listar e assistir episódios de podcasts em vídeo, organizados por categorias.


## 📋 Descrição

O PodCast Manager é um servidor Node.js que centraliza episódios de podcasts em vídeo (como os do YouTube), permitindo que sejam listados por categorias ou filtrados por nome de podcast.


## 🌐 Domínio

Podcasts com conteúdo em vídeo (ex: entrevistas, bate-papos e episódios gravados no YouTube).


## 🚀 Funcionalidades

- 📂 **Listar episódios por categorias**:
  - Categorias suportadas: `saúde`, `fitness`, `mentalidade`, `humor`, `bodybuilder`, `esporte`, `corrida`.
- 🔍 **Filtrar episódios por nome do podcast** através de parâmetro na URL.

---

## ⚙️ Como funciona

A API foi construída usando **Node.js puro**, sem frameworks externos, e organiza sua lógica em `controllers`, `routes` e `utils`.


## 🔧 Exemplo de código (servidor)

```ts
import * as http from "http";
import {
  getFilterEpisodes,
  getListEpisodes,
} from "./controllers/podcasts-controller";
import { Routes } from "./routes/routes";
import { HttpMethod } from "./utils/http-methods";

export const app = async (
  request: http.IncomingMessage,
  response: http.ServerResponse
) => {
  const baseUrl = request.url?.split("?")[0];

  if (request.method === HttpMethod.GET && baseUrl === Routes.LIST) {
    await getListEpisodes(request, response);
  }

  if (request.method === HttpMethod.GET && baseUrl === Routes.EPISODE) {
    await getFilterEpisodes(request, response);
  }
};
```

---

# 🛠️ Endpoints disponíveis

## 📥 GET /podcasts
Retorna todos os episódios listados por categoria.

Resposta:

```json
[
  {
    "podcastName": "Flow",
    "episode": "CBUM - Flow #319",
    "videoId": "pQSuQmUfS30",
    "cover": "https://i.ytimg.com/vi/pQSuQmUfS30/maxresdefault.jpg",
    "link": "https://www.youtube.com/watch?v=pQSuQmUfS30",
    "category": ["saúde", "esporte", "bodybuilder"]
  },
  {
    "podcastName": "Flow",
    "episode": "RUBENS BARRICHELLO - Flow #339",
    "videoId": "4KDGTdiOV4I",
    "cover": "https://i.ytimg.com/vi/4KDGTdiOV4I/maxresdefault.jpg",
    "link": "https://www.youtube.com/watch?v=4KDGTdiOV4I",
    "category": ["esporte", "corrida"]
  }
]
```

---

## 🔍 GET /episode?podcastName=Flow

Retorna apenas os episódios do podcast cujo nome foi enviado como parâmetro.
 

# 📦 Tecnologias Utilizadas

- Node.js
- TypeScript
- HTTP nativo (http.createServer)
- Modularização com controllers e rotas
- JSON como formato de resposta


# 📈 Próximas melhorias

- Adicionar player embutido
- Persistência com banco de dados
- Interface front-end para visualização dos episódios
- Paginação e ordenação
- Autenticação para usuários


# 📄 Licença

Este projeto está sob a licença MIT.

# ✉️ Contato

Em caso de dúvidas, sugestões ou contribuições, entre em contato:
Adryan Lopes
[E-mail](adylopesk8@gmail.com)
[LinkedIn](https://www.linkedin.com/in/adryanlopes/)
[Instagram](https://www.instagram.com/https_marrom/)

