# Jogo da Glória — Desafio do Conhecimento

Repositório oficial do projeto de POO (UAL 2026–2027): "Jogo da Glória — Desafio do Conhecimento". Uma aplicação em consola desenvolvida em Java para dois jogadores, que combina a mecânica clássica do tabuleiro com desafios interativos de Matemática e Conhecimento Geral.

## Descrição

O **Jogo da Glória — Desafio do Conhecimento** é uma adaptação do tradicional Jogo da Glória, desenvolvida em **Java**, com recurso aos princípios da **Programação Orientada a Objetos (POO)**.

O jogo combina entretenimento e aprendizagem, permitindo que dois jogadores compitam num tabuleiro de 24 casas, enfrentando desafios de Matemática e Conhecimento Geral.

A aplicação funciona através de uma interface de consola.

## Objetivo do Jogo

O objetivo é ser o primeiro jogador a alcançar exatamente a **casa 24**.

Ao longo do percurso, os jogadores encontram diferentes tipos de casas que podem fazê-los avançar, recuar ou responder a perguntas.

## Regras do Jogo

- O jogo é disputado por **2 jogadores**.
- Ambos começam na posição 0.
- Cada jogador lança um dado aleatório, com valores entre 1 e 6.
- Os jogadores jogam alternadamente.
- Dois jogadores podem ocupar a mesma casa.
- Um jogador nunca fica abaixo da casa 0.
- Para vencer, é necessário chegar exatamente à casa 24.
- Se o lançamento ultrapassar a casa 24, o jogador permanece na posição anterior.

## Tipos de Casas

O tabuleiro contém quatro tipos de casas:

| Tipo | Funcionamento | Classe |
|---|---|---|
| Normal | O jogador permanece na casa. | `NormalCell` |
| Avanço | O jogador avança automaticamente para uma posição definida. | `JumpCell` |
| Recuo | O jogador recua automaticamente para uma posição definida. | `JumpCell` |
| Pergunta | O jogador responde a um desafio de Matemática ou Conhecimento Geral. | `QuestionCell` |

**Nota:** os efeitos das casas especiais não são aplicados em cadeia.

## Sistema de Perguntas

### Matemática

As casas **8 e 17** apresentam equações de primeiro grau. O banco tem 5 equações.

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

O banco tem 6 perguntas. As perguntas são selecionadas aleatoriamente a partir de uma lista previamente definida, por isso a mesma pergunta pode repetir-se.

### Sistema de Recompensas

- **Resposta correta:** avança 2 casas.
- **Resposta errada:** recua 1 casa.

## Organização do Tabuleiro

O tabuleiro contém 24 casas (posições 0 a 24), distribuídas da seguinte forma:

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

## Estrutura da Aplicação

O código tem onze classes, divididas em dois pacotes: `Project` e `Project.cells`.

```
src/
 └── Project/
      ├── Main.java
      ├── Game.java
      ├── Board.java
      ├── Player.java
      ├── Dice.java
      ├── Question.java
      ├── BancoPerguntas.java
      └── cells/
           ├── Cell.java
           ├── NormalCell.java
           ├── JumpCell.java
           └── QuestionCell.java
```

| Classe | Responsabilidade |
|---|---|
| `Player` | Representar os jogadores e as respetivas posições. |
| `Dice` | Lançar o dado aleatório, de 1 a 6. |
| `Question` | Representar perguntas e respostas e verificar a tentativa do jogador. |
| `BancoPerguntas` | Fornecer as listas de perguntas de Conhecimento Geral e de Matemática. |
| `Board` | Montar as 25 posições do tabuleiro e devolver a casa de cada uma. |
| `Game` | Controlar turnos, movimentos e condições de vitória. |
| `Main` | Apresentar a interface de consola. |
| `Cell` | Classe abstrata com o método `aterrar(Player)`. |
| `NormalCell` | Casa sem efeito. |
| `JumpCell` | Casa de avanço ou recuo para um destino definido. |
| `QuestionCell` | Fazer a pergunta, ler a resposta e aplicar +2 ou -1 casas. |

### Conceitos de POO aplicados

- **Encapsulamento:** atributos privados, com getters e validação em `setPosicao`.
- **Herança e classe abstrata:** `NormalCell`, `JumpCell` e `QuestionCell` estendem `Cell`.
- **Polimorfismo:** o `Game` chama `aterrar(jogador)` sem saber o tipo da casa.

### Alterações face ao plano inicial

- **Dado:** ficou só o modo aleatório, em vez de manual ou aleatório.
- **Casas:** `Cell` passou a abstrata, com três subclasses.
- **Perguntas:** ficaram numa classe própria, `BancoPerguntas`. Matemática e Conhecimento Geral usam a mesma `QuestionCell`, com listas diferentes.
- **Meta:** o valor 24 passou a constante `Board.META`.

## Funcionalidades

- [x] Sistema de dois jogadores
- [x] Tabuleiro com 24 casas
- [x] Lançamento aleatório do dado
- [x] Movimentação dos jogadores
- [x] Casas especiais de avanço e recuo
- [x] Perguntas de Matemática
- [x] Perguntas de Conhecimento Geral
- [x] Seleção aleatória de perguntas
- [x] Validação das respostas
- [x] Deteção automática da vitória
- [ ] Mapa do tabuleiro (mapa-board) na consola

## Estado do Projeto

O projeto encontra-se em fase de aperfeiçoamento. Etapas:

- [x] Definição das regras e estrutura do tabuleiro.
- [x] Implementação das classes principais.
- [x] Desenvolvimento da movimentação dos jogadores.
- [x] Implementação dos desafios matemáticos.
- [x] Implementação das perguntas de Conhecimento Geral.
- [x] Lançamento do dado (apenas aleatório).
- [x] Integração das funcionalidades.
- [ ] Realização de testes e validações (registar uma partida completa até à casa 24).
- [ ] Aperfeiçoamento e conclusão da aplicação.

### Aspetos a corrigir

Os aspetos a mudar não dizem respeito à lógica do jogo, mas à formatação dos textos e à apresentação na consola:

- Corrigir a pontuação e os acentos das mensagens.
- Escrever a resposta na mesma linha da pergunta.
- Corrigir as gralhas nos comentários e uniformizar a formatação do código.
- Incluir um mapa do tabuleiro (mapa-board) com as 25 posições e a posição dos dois jogadores, apresentado no início de cada turno.

## Contribuições

O projeto foi desenvolvido em grupo. A distribuição de tarefas manteve-se igual à planeada, e cada elemento apoiou o desenvolvimento do outro.

- **Janeth Moisés:** estrutura do tabuleiro (`Board`), movimentação dos jogadores (`Player`), casas normais, de avanço e de recuo (`NormalCell` e `JumpCell`) e respetivos testes.
- **Victória Menezes:** sistema de perguntas (`Question`, `QuestionCell` e `BancoPerguntas`), categorias de Matemática e de Conhecimento Geral, lançamento do dado (`Dice`) e testes de validação.
- **Em conjunto:** integração (`Game` e `Main`), revisão do código e testes do jogo.

## Condição de Vitória

O jogo termina quando um dos jogadores chega **exatamente à casa 24**, sendo declarado vencedor.

---

**Jogo da Glória — Desafio do Conhecimento**

*Aprender, jogar e conquistar a vitória!*
