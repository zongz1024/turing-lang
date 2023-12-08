# 图灵语言

图灵语言是一种用于描述图灵机的编程语言。它可以用来定义图灵机的状态转移，初始状态和最终状态。

## 1. 语法

图灵语言的语法由以下几部分组成：

- 状态转移：`TRANSITION <state> <symbol> <new-state> <new-symbol> <direction>`
- 初始状态：`INITIAL <state>`
- 最终状态：`FINAL <state>`

其中，`<state>`、`<new-state>`、`<symbol>`和`<new-symbol>`都是标识符，`<direction>`可以是`LEFT`或`RIGHT`。

```bnf
<program> ::= <statement>*
<statement> ::= <state-transition> | <state-definition>
<state-transition> ::= <current-state> <action>

<current-state> ::= <current-state-identifier> "," <current-symbol> 

<action> ::= <direction> <new-state-identifier> "," <new-symbol> 

<state-definition> ::= <initial-state> | <final-state>
<initial-state> ::= "init" <state>
<final-state> ::= "final" <state>
<state> ::= "state" <identifier>

<current-state-identifier> ::= <identifier>
<new-state-identifier> ::= <identifier>

<current-symbol> ::= <symbol>
<new-symbol> ::= <symbol>
<direction> ::= ">" | "<"

<identifier> ::= <letter> (<letter> | <digit>)*
<symbol> ::= 0 | 1

<letter> ::= "A" | "B" | "C" | ... | "Z"
<digit> ::= "0" | "1" | "2" | ... | "9"
```

## 2. 示例

以下是一个图灵语言的示例程序：

```
init state q0; 
final state q1; 
q0, 0  > q0, 1; 
q0, 1  > q1, 1;
```

这个程序描述了一个简单的图灵机，它将输入中的第一个`0`替换为`1`，然后进入最终状态。

