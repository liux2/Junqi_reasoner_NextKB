# A Simple Junqi Reasoner by NextKB

A simple knowledge representation and reasoning project for Luzhanqi chess game.

## Project structures

```bash
.
├── LICENSE
├── README.md
├── companions
│   ├── pull-companions.sh
│   └── run-companions.sh
└── src
    ├── board.krf
    ├── ontology.krf
    ├── pieces.krf
    ├── play.krf
    └── referee.krf
```

`companions/` contains the bash scripts for installing and running the companions.
`src/` contains the krf files that can be uploaded to the companions for querying
and reasoning. Each krf file contains a mircro-theory as part of the game. As the
table shows:

|   **File**   | **Micro-Theory** | **Functions**                        |
|:------------:|:----------------:|--------------------------------------|
|   board.krf  |      BoardMt     | Formation of the board               |
| ontology.krf |      MainMt      | Ontology                             |
|  pieces.krf  |      PieceMt     | Role and rank of pieces              |
|   play.krf   |      MoveMt      | Game state and pieces initilizations |
|  referee.krf |      RuleMt      | Horn Clauses for reasoning           |

## How to use the companions

The companions project homepage and manual can be found at:
[https://www.qrg.northwestern.edu/nextkb/index.html](https://www.qrg.northwestern.edu/nextkb/index.html)

Use `bash pull-companions.sh` to install.

Use `bash run-companions.sh` to run.

## Quary List/ Play sequence

### Play sequence

**1. Make an empty board**

```lisp
(isa ?board Empty-Board)
```

**2. Put pieces**

```lisp
(isa ?board Junqi-Board)
```

**3. Initilize pieces from both players**

```lisp
(initPlayer Done)
```
**4. Tell movement**

```lisp
(move node4 node7)
```

Use the `tell` button to save the fact to working memory.

**5. Make the move**

```lisp
(makeMove Done)
```

Use the `untell` button to retract the fact from working memory.

**6. Validate winning state**

```lisp
(isWinning won)
```

### Other Queries

**1. To get the status of the board**

```lisp
(hasRole ?node1 ?node2)
```

**2. To get the rank of a piece**

```lisp
(hasRank ?role ?rank)
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE)
file for details.
