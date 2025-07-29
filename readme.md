# 🎧 PodCast Manager

Um app ao estilo Netflix, onde é possível centralizar e visualizar episódios de podcasts em vídeo, organizados por categorias.

---

## 📋 Descrição

O PodCast Manager tem como objetivo fornecer uma interface simples e organizada para assistir a podcasts em vídeo, categorizando episódios e permitindo buscas rápidas por nome.

---

## 🌐 Domínio

Podcasts em formato de vídeo (ex: YouTube).

---

## 🚀 Features

- 📂 Listagem de episódios organizados por categorias:
  - Exemplos: saúde, fitness, mentalidade, humor, bodybuilder, esporte, corrida.
- 🔍 Filtro por nome do podcast.

---

## ⚙️ Como funciona

### 🔹 Feature: Listar episódios por categoria

#### Requisição
`GET /episodios`

#### Resposta:
```json
[
  { 
    "podcastName": "Flow",
    "episode": "CBUM - Flow #319",
    "videoId": "pQSuQmUfS30",
    "category": ["saúde", "esporte", "bodybuilder"]
  },
  { 
    "podcastName": "Flow",
    "episode": "RUBENS BARRICHELLO - Flow #339",
    "videoId": "4KDGTdiOV4I",
    "category": ["esporte", "corrida"]
  }
]
