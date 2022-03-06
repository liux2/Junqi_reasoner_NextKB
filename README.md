# A Simple Junqi Reasoner by NextKB

A simple knowledge representation and reasoning project.

### Quary List/ Play sequence

**1. Make an empty board**

```
(isa ?board Empty-Board)
```

**2. Put pieces**

```
(isa ?board Junqi-Board)
```

**3. Initilize pieces from both players**

```
(initPlayer Done)
```
**4. Tell movement**

```
(move node4 node7)
```

**5. Make the move**

```
(makeMove Done)
```
