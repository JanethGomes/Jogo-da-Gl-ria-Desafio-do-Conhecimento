# Jogo-da-Glo-ria-Desafio-do-Conhecimento
Repositório oficial do projeto de POO (UAL 2026–2027): "Jogo da Glória — Desafio do Conhecimento". Uma aplicação em consola desenvolvida em Java para dois jogadores, que combina a mecânica clássica do tabuleiro com desafios interativos de Matemática e Conhecimento Geral.

# Jogo da Glória — Desafio do Conhecimento

##  Descrição

O **Jogo da Glória — Desafio do Conhecimento** é uma adaptação do tradicional Jogo da Glória, desenvolvida em **Java**, com recurso aos princípios da **Programação Orientada a Objetos (POO)**.

O jogo combina entretenimento e aprendizagem, permitindo que dois jogadores compitam num tabuleiro de 24 casas, enfrentando desafios de Matemática e Conhecimento Geral.

A aplicação funciona através de uma interface de consola.

##  Objetivo do Jogo

O objetivo é ser o primeiro jogador a alcançar exatamente a **casa 24**.

Ao longo do percurso, os jogadores encontram diferentes tipos de casas que podem fazê-los avançar, recuar ou responder a perguntas.

##  Regras do Jogo

- O jogo é disputado por **2 jogadores**.
- Ambos começam na posição 0.
- Cada jogador lança um dado com valores entre 1 e 6.
- O lançamento pode ser manual ou aleatório, dependendo da modalidade escolhida.
- Os jogadores jogam alternadamente.
- Dois jogadores podem ocupar a mesma casa.
- Para vencer, é necessário chegar exatamente à casa 24.
- Se o lançamento ultrapassar a casa 24, o jogador permanece na posição anterior.

##  Tipos de Casas

O tabuleiro contém quatro tipos de casas:

| Tipo | Funcionamento |
|---|---|
| Normal | O jogador permanece na casa. |
| Avanço | O jogador avança automaticamente para uma posição definida. |
| Recuo | O jogador recua automaticamente para uma posição definida. |
| Pergunta | O jogador responde a um desafio de Matemática ou Conhecimento Geral. |

**Nota:** Os efeitos das casas especiais não são aplicados em cadeia.

## Sistema de Perguntas

### Matemática

As casas **8 e 17** apresentam equações de primeiro grau.

Exemplos:

- `2x + 3 = 11` → x = 4
- `3x - 5 = 10` → x = 5
- `4x + 2 = 18` → x = 4

### Conhecimento Geral

As casas **4, 11, 15 e 20** apresentam perguntas sobre diferentes áreas, incluindo:

- Geografia
- História
- Ciências
- Cultura e Literatura
- Desporto

As perguntas são selecionadas aleatoriamente a partir de uma coleção previamente definida.

### Sistema de Recompensas

- **Resposta correta:** avança 2 casas.
- **Resposta errada:** recua 1 casa.

##  Organização do Tabuleiro

O tabuleiro contém 24 casas, distribuídas da seguinte forma:

| Casa | Tipo | Efeito |
|---|---|---|
| 4 | Conhecimento Geral | +2 / -1 |
| 5 | Avanço | Vai para a casa 9 |
| 8 | Matemática | +2 / -1 |
| 10 | Recuo | Vai para a casa 7 |
| 11 | Conhecimento Geral | +2 / -1 |
| 12 | Avanço | Vai para a casa 16 |
| 15 | Conhecimento Geral | +2 / -1 |
| 17 | Matemática | +2 / -1 |
| 19 | Recuo | Vai para a casa 14 |
| 20 | Conhecimento Geral | +2 / -1 |
| 24 | Meta | Vitória |

As restantes casas são normais.

## Tecnologias Utilizadas

- **Java** — Linguagem de programação.
- **Programação Orientada a Objetos** — Organização e estruturação do código.
- **Consola** — Interface de interação com os jogadores.

##  Estrutura da Aplicação

O projeto prevê as seguintes classes:

| Classe | Responsabilidade |
|---|---|
| `Player` | Representar os jogadores e as respetivas posições. |
| `Board` | Gerir as casas do tabuleiro. |
| `Cell` | Representar os diferentes tipos de casas. |
| `Question` | Representar perguntas e respostas. |
| `Game` | Controlar turnos, movimentos e condições de vitória. |
| `Dice` | Gerir lançamentos manuais e aleatórios. |
| `Main` | Apresentar a interface de consola. |

## Funcionalidades Previstas

- Sistema de dois jogadores.
- Tabuleiro com 24 casas.
- Lançamento manual ou aleatório do dado.
- Movimentação dos jogadores.
- Casas especiais de avanço e recuo.
- Perguntas de Matemática.
- Perguntas de Conhecimento Geral.
- Seleção aleatória de perguntas.
- Validação das respostas.
- Deteção automática da vitória.

##  Estado do Projeto

O projeto encontra-se em fase de desenvolvimento, com as seguintes etapas previstas:

- [ ] Definição das regras e estrutura do tabuleiro.
- [ ] Implementação das classes principais.
- [ ] Desenvolvimento da movimentação dos jogadores.
- [ ] Implementação dos desafios matemáticos.
- [ ] Implementação das perguntas de Conhecimento Geral.
- [ ] Desenvolvimento dos modos de lançamento dos dados.
- [ ] Integração das funcionalidades.
- [ ] Realização de testes e validações.
- [ ] Aperfeiçoamento e conclusão da aplicação.

## Condição de Vitória

O jogo termina quando um dos jogadores chega **exatamente à casa 24**, sendo declarado vencedor.

---

**Jogo da Glória — Desafio do Conhecimento** 

*Aprender, jogar e conquistar a vitória!*
