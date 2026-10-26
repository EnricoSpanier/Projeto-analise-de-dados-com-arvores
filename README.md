# Análise de dados escolares com Árvore AVL e Árvore Binária de Busca

> **English:** Java command-line project that loads ten semesters of public school-enrollment CSVs (2019–2023) into an AVL tree and an unbalanced binary search tree keyed by school code, times each operation (insert, search, remove, traversal) and produces statistical summaries per district and semester.

Projeto acadêmico em Java. Os dados vêm de arquivos CSV com a quantidade de alunos por tipo de ensino da rede estadual, um por semestre, de 2019 a 2023. Cada escola é inserida em duas estruturas, indexadas pelo código da escola, para comparar o comportamento de uma árvore balanceada (AVL) com o de uma árvore binária de busca sem balanceamento.

## O que o programa faz

O `Main` abre um menu interativo no terminal. Para qualquer uma das duas árvores é possível:

- inserir um código de escola manualmente ou carregar os CSVs de todos os semestres;
- percorrer e exibir a árvore (pré-ordem);
- buscar e remover uma escola pelo código;
- apagar a árvore;
- gerar a **análise estatística** por distrito e semestre.

Cada operação imprime o tempo gasto em nanossegundos, o que permite comparar AVL e árvore binária em inserção, busca, remoção e análise.

A análise grava os resultados em `resultadoAVL.csv` / `resultadoAVL.txt` e `resultadoBT.csv` / `resultadoBT.txt` (médias por distrito e semestre para cada tipo de ensino).

## Estrutura

| Caminho | Descrição |
| --- | --- |
| `src/AVLTree.java` | Árvore AVL (inserção, remoção, busca, rotações, análise) |
| `src/BinaryTree.java` | Árvore binária de busca sem balanceamento |
| `src/BTNode.java` | Nó com o código e os dados da escola |
| `src/LLAVL.java`, `src/LLBT.java` | Listas ligadas com uma árvore por semestre |
| `src/ReadCSV.java` | Leitura dos CSVs (separador `;`) e inserção nas árvores |
| `src/Main.java` | Menu interativo |
| `src/csv/` | CSVs de entrada, um por semestre (2019–2023) |
| `Diretrizes do projeto e objetivos` | Enunciado do projeto |
| `resultado*.csv` / `resultado*.txt` | Saídas da análise estatística |

## Como executar

Requisito: JDK instalado. Os caminhos dos CSVs no código usam barra invertida (`src\csv\...`), então o projeto foi feito para rodar no Windows e deve ser executado a partir da raiz do repositório.

```bash
javac -d out src/*.java
java -cp out Main
```

## Autores

Enrico Spanier e Guilherme Vecchi ([@endydragonn](https://github.com/endydragonn)).
