# Gastos dos Deputados

Ferramenta de transparência que mostra, em tempo real, os gastos de cota parlamentar dos deputados federais, consumindo a API de dados abertos da Câmara dos Deputados.

🔗 **Ver no ar:** [kellymariah.github.io/gastos-deputados](https://kellymariah.github.io/gastos-deputados)

## Sobre o projeto

Um exercício de jornalismo de dados feito do zero com HTML, CSS e JavaScript puro, sem frameworks. O app lista os deputados federais e, ao clicar em um nome, exibe suas despesas com a cota parlamentar: valores, fornecedores e tipo de gasto, atualizados direto da fonte oficial.

O dado sempre esteve público. A ideia foi torná-lo visível para quem não vive abrindo planilha de governo.

## Funcionalidades

- Lista os deputados em exercício, com foto, partido e estado
- Busca por nome em tempo real
- Ao clicar em um deputado, mostra suas despesas detalhadas (uma segunda chamada à API, sob demanda)
- Soma das despesas formatada em reais
- Interface com fundo animado e cards translúcidos (glassmorphism)

## Como funciona por dentro

O projeto consome dois endpoints da [API de dados abertos da Câmara](https://dadosabertos.camara.leg.br):

1. `/deputados` — traz a lista de parlamentares
2. `/deputados/{id}/despesas` — traz as despesas de um deputado específico

No JavaScript, os dados são buscados com `fetch` e `async/await`, transformados em cards com `.map()`, filtrados na busca com `.filter()` e somados com `.reduce()`.

## Tecnologias

- HTML
- CSS (Flexbox, Grid, animações com `@keyframes`)
- JavaScript (fetch, async/await, manipulação do DOM)
- API pública de dados abertos da Câmara dos Deputados

## Limitações conhecidas

- A lista carrega os primeiros 100 deputados. Um ranking geral de "quem mais gasta" exigiria somar as despesas de todos os 513 parlamentares, o que demanda um backend (próximo passo do projeto).
- Os dados dependem da disponibilidade da API da Câmara.

## Autoria

Feito por Kelly Mariah ([@kellymariah](https://github.com/kellymariah)) como exercício de front-end e jornalismo de dados.
