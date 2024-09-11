# arrays
Prova de Conceito sobre Arrays desenvolvida pelo grupo TechMack
# Times de Futebol - Estatísticas de Temporada
Este projeto implementa funcionalidades para manipular e exibir informações de um conjunto de times de futebol, incluindo vitórias, derrotas e gols. O código é escrito em JavaScript e oferece várias operações como soma de gols, cálculo de pontos e geração de tabelas para exibição em uma interface HTML.

## Funcionalidades Principais
- Soma de Gols: O código calcula a soma total de gols marcados por todos os times.
- Cálculo de Pontos: Cada vitória vale 3 pontos, e o código calcula automaticamente a pontuação de cada time com base no número de vitórias.
- Ordenação por Pontos: Os times são organizados em ordem decrescente de acordo com seus pontos.
- Filtro de Times Vencedores: Times com mais de 10 vitórias são filtrados e exibidos separadamente.
- Geração de Tabelas: As informações dos times são exibidas em tabelas HTML dinâmicas, mostrando nome, pontos, vitórias, derrotas e gols.

# 1. Somar Total de Gols
  O código usa a função reduce para somar o número total de gols marcados por todos os times:
  ```js
    const somarGols = (arrayTimes) => {
    return arrayTimes.reduce((acumulador, time) => acumulador + time.gols, 0);
};
```
# 2. Calcular Pontos dos Times
A função calcularPontos atribui 3 pontos para cada vitória de um time, ou seja, o operador spread é usado para expandir o array de argumentos resultados em elementos individuais (neste caso, vitorias e derrotas), mesmo que a função só utilize o número de vitórias para calcular os pontos.
```js
const calcularPontos = (...resultados) => {
    let [vitorias, derrotas] = resultados;
    return vitorias * 3;
};
```
# 3. Ordenar Times por Pontuação
Os times são ordenados com base nos pontos em ordem decrescente:
```js
const timesOrdenados = timesComPontos.sort((a, b) => b.pontos - a.pontos);
```
# 4. Filtrar Times com Mais de 10 Vitórias
Um filtro é aplicado para exibir apenas os times com mais de 10 vitórias:
```js
const timesVitorias = times.filter(time => time.vitorias > 10);
```
# 5. Geração Dinâmica de Tabelas
As tabelas são geradas dinamicamente no HTML usando a função gerarColuna para exibir as colunas de interesse (nome, pontos, vitórias, derrotas, gols):
```js
const gerarColuna = (arrayTimes, colunaId, chave) => {
    const tabelaBody = document.querySelector(`#${colunaId} tbody`);
    tabelaBody.innerHTML = ''; // Limpa a tabela antes de adicionar

    arrayTimes.forEach(time => {
        const linha = document.createElement('tr');
        linha.innerHTML = `<td>${time[chave]}</td>`;
        tabelaBody.appendChild(linha);
    });
};
```

# Estrutura do Projeto
- index.html: Estrutura básica para exibir as tabelas.
- content.html: Estrutura básica contendo todo o contéudo ditadico sobre os metódos das arrays
- times.js: Contém todas as funções de manipulação dos dados dos times.
- tabela_completa: Formato da tabela completa com todos os metódos utilizados 

















## Autores
Este projeto foi desenvolvido para entendermos, os diferentes tipos de uso dos metódos das arrays
Projetado por
- Arthur_Eduardo
- Guilherme_Sampaio
- Felipe_Melantonio 
