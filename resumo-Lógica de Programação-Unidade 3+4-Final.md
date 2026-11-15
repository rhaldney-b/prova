---
title: "Resumo Consolidado — Lógica de Programação (Unidade 3 + 4)"
date: 2026-11-15
tags: [Lógica de Programação, Algoritmos, Estruturas de Repetição, Vetores, Funções, Unidade 3+4, Provão 17/11, Resumo de Estudo]
---

# Resumo Consolidado — Lógica de Programação (Unidade 3 + 4)

## 1. Objetivos da Unidade
- Analisar algoritmos com estruturas de repetição **enquanto** e **repita** em pseudocódigo e MATLAB (while e for).
- Identificar problemas que necessitam de estruturas de repetição.
- Desenvolver algoritmos que necessitam de estruturas de repetição na resolução de problemas.
- Declarar estruturas de dados homogêneas de uma dimensão (vetores) em pseudocódigo e MATLAB.
- Construir algoritmos com vetores na solução de problemas.
- Reconhecer e criar funções/sub-rotinas em MATLAB e pseudocódigo.

---

## 2. Estruturas de Repetição

### Conceito
- **Estrutura de repetição** = laço (loop) que repete um bloco de instruções até que uma condição seja atendida.
- O laço contém o trecho de código que deve ser repetido; a execução termina quando a condição é atendida (verdadeira/false).

### Tipos de Estruturas de Repetição

| Estrutura | Uso | Característica |
|-----------|-----|----------------|
| **while-end** | Repetição indeterminada | Testa a condição no início; só executa se a condição for verdadeira. |
| **for-end** | Repetição determinada | Contador define quantas vezes o laço se repetirá. |
| **while...break** | Teste no meio do laço | Encerramento sob condição verdadeira em qualquer ponto (não disponível nativamente no MATLAB, mas imitável). |

### Estrutura while-end
```
enquanto <condição> faça
    <bloco de comandos>
fim
```
- Executa repetidamente enquanto a condição for **verdadeira**.
- Se a condição já for falsa no início, o laço **não executa nenhuma vez**.
- Ideal quando **não se sabe quantas vezes** o laço será repetido.

### Estrutura for-end
```
para <contador> de <início> incr <passo> até <fim> faça
    <bloco de comandos>
fim
```
- Controle por **variável de controle** (contador).
- Repete um número **finito** de vezes, quando se conhece a quantidade.
- Sintaxe do MATLAB: `for i = 1:1:10` (início, passo, fim).
- A variável de controle **não deve ser alterada dentro do laço** (incumprir isto distorce a estrutura).

### Tabelas de Contagem (Exemplo)
| Número da rodada | Contador |
|------------------|----------|
| 1ª repetição     | 1        |
| 2ª repetição     | 2        |
| 3ª repetição     | 3        |
| ...              | ...      |
| 10ª repetição    | 10       |

### Passos de execução do for-end (Chapra, 2013, p. 65):
1. Índice recebe o valor inicial.
2. Compara o índice com o valor final.
3. Se `índice ≤ fim`, executa as declarações.
4. Ao chegar em `end`, incrementa o índice pelo valor do passo e volta ao `for`.
5. Repete até que `índice > fim`; então encerra o laço.

### Comando break (estrutura while...break)
- Encerra a execução do laço sob uma condição verdadeira em qualquer ponto.
- No MATLAB, não existe nativamente; pode ser "imitado" com uma variável de controle ou `if` + `break`.
- Exemplo conceptual:
```matlab
while condição
    if <condição_de_saída>
        break;
    end
    <comandos>
end
```

### Comando pause
- Interrompe temporariamente o programa até que uma tecla seja pressionada.
- Usado para exibir sequências de gráficos passo a passo.

---

## 3. Variáveis Indexadas (Vetores)

### Conceito
- **Vetor / Array / Variável indexada**: estrutura de dados homogênea, unidimensional, que armazena uma **sequência de elementos**.
- Os elementos são acessados por **índice** (posição), começando em **1** (MATLAB) ou **0** (PSEUDOCÓDIGO).
- Todos os elementos são do **mesmo tipo** de dados (homogêneos).
- Não é possível inserir elementos de tipos diferentes.

### Diferença entre Vetor e Tabela
- Vetor = linha ou coluna única (umidimensional).
- Tabela = duas ou mais dimensões (matriz).

### Declaração de Vetores

#### PSEUDOCÓDIGO
```pseudocódigo
vetor <nome> ← [valor1, valor2, valor3, ...]
```
Exemplo:
```pseudocódigo
notas ← [7.5, 8.0, 6.5, 9.0]
```

#### MATLAB — Vetor de Linha
```matlab
vetor = [1, 2, 3, 4, 5]
```
ou
```matlab
vetor = [1 2 3 4 5]
```

#### MATLAB — Vetor de Coluna
```matlab
vetor = [1; 2; 3; 4; 5]
```
ou
```matlab
vetor = [1
         2
         3
         4
         5]
```

#### MATLAB — Espaçamento Constante (Intervalo)
```matlab
vetor = 1:0.5:3   % 1, 1.5, 2, 2.5, 3
vetor = 1:5       % 1, 2, 3, 4, 5 (passo implícito = 1)
```

#### MATLAB — Espaçamento com quantidade de elementos
```matlab
vetor = linspace(1, 10, 4)   % 4 elementos entre 1 e 10
```

### Operações com Vetores

| Operação | Como fazer |
|----------|------------|
| **Acesso** | `vetor(i)` — posição i |
| **Edição** | `vetor(i) ← novo_valor` |
| **Criar posição** | `vetor(i) ← valor` (cria posição se não existir) |
| **Excluir** | `vetor(i) ← []` — remove elemento |
| **Concatenar** | `vetor1 = [vetor1, vetor2]` |
| **Soma** | `vetor1 + vetor2` (mesma dimensão) |
| **Subtração** | `vetor1 - vetor2` |
| **Multiplicação por escalar** | `2 * vetor` |
| **Multiplicação elemento a elemento** | `vetor1 .* vetor2` |
| **Divisão elemento a elemento** | `vetor1 ./ vetor2` |
| **Potência elemento a elemento** | `vetor1 .^ 2` |
| **Troca de coluna por linha** | `vetor'` (operador de transposição) |

### Restrições
- **Dimensões devem coincidir** para operações entre vetores.
- Erro comum: `matrix dimensions must agree` (dimensões diferentes).
- A **variável de controle** não deve ser modificada dentro do laço (incumprir esto altera a quantidade de repetições).

### Percorrer Vetores
#### PSEUDOCÓDIGO
```pseudocódigo
para i de 1 até tamanho(vetor) faça
    escrever(vetor[i])
fim
```

#### MATLAB
```matlab
for i = 1:length(vetor)
    disp(vetor(i));
end
```

### Seleção de Elementos
#### PSEUDOCÓDIGO
```pseudocódigo
para i de 1 até tamanho(vetor) faça
    se vetor[i] > 4 então
        escrever(vetor[i])
    fim
fim
```

#### MATLAB
```matlab
for i = 1:length(vetor)
    if vetor(i) > 4
        disp(vetor(i));
    end
end
```

### Funções Nativas para Vetores (MATLAB)
| Função | Uso |
|--------|-----|
| `length(vetor)` | Número de elementos |
| `size(vetor)` | Dimensões (linhas, colunas) |
| `find(vetor > 4)` | Índices de elementos que satisfazem a condição |
| `sum(vetor)` | Soma dos elementos |
| `mean(vetor)` | Média dos elementos |
| `max(vetor)` | Valor máximo |
| `min(vetor)` | Valor mínimo |
| `sort(vetor)` | Ordena os elementos |
| `rand` | Números aleatórios entre 0 e 1 |
| `randi` | Números inteiros aleatórios uniformes |
| `randn` | Distribuição normal (média 0, desvio padrão 1) |

### Entrada e Saída de Dados em Vetores
#### Entrada (MATLAB)
```matlab
vetor = zeros(1, 3);  % vetor vazio de 1 linha, 3 colunas
for i = 1:3
    vetor(i) = input(['Informe o valor da posição ' num2str(i) ':']);
end
```

#### Saída (MATLAB)
```matlab
disp(vetor);          % exibe o vetor
fprintf('%d ', vetor); % formata a saída
```

---

## 4. Funções (Sub-rotinas)

### Conceito
- **Sub-rotina** = bloco de comandos projetado para tarefa específica, reutilizável.
- Comparável a um relógio: sempre mostra as horas quando solicitado, independentemente de quem peça.
- Abrange os detalhes do programa, melhorando desempenho e manutenção.

### Tipos de Sub-rotinas
| Tipo | Retorno | Parâmetros |
|------|---------|------------|
| Sem retorno, sem parâmetros | Não | Não |
| Sem retorno, com parâmetros | Não | Sim |
| Com retorno, sem parâmetros | Sim | Não |
| Com retorno, com parâmetros | Sim | Sim |

### Diferença entre Script e Function (MATLAB)

| Característica | Script | Function |
|----------------|--------|----------|
| Extensão | `.m` | `.m` |
| Parâmetros de entrada | Não | Sim |
| Retorno de valores | Não | Sim |
| Variáveis locais | Sim (compartilham o espaço de trabalho) | Sim (isoladas) |
| Comunicação | Espaço de trabalho | Argumentos de entrada e saída |
| Uso | Comandos sequenciais | Reutilização, módulos |

### Criar uma Função em MATLAB
1. Criar arquivo `.m` com o **mesmo nome** da função.
2. A primeira linha define a função:
```matlab
function [saída1, saída2] = nome_funcao(entry1, entry2)
```
3. O arquivo é executado chamando o nome da função.

#### Exemplo
```matlab
function distancia = calcula_distancia(p, q)
    distancia = sqrt(sum((p - q).^2));
end
```

### Chamar uma Função
```matlab
resultado = calcula_distancia(pontoA, pontoB);
```

### Tamanho de Argumentos
| Comando | Uso |
|---------|-----|
| `nargin` | Número de argumentos de entrada dentro da função |
| `nargout` | Número de argumentos de saída dentro da função |
| `nargin(f)` | Número de argumentos de entrada de uma função externa |
| `nargout(f)` | Número de argumentos de saída de uma função externa |

### Argumentos Variáveis
| Comando | Uso |
|---------|-----|
| `varargin` | Permite aceitar **qualquer número de parâmetros de entrada** (deve ser o último parâmetro de entrada) |
| `varargout` | Permite **qualquer número de parâmetros de saída** (deve ser o último parâmetro de saída) |

### Exemplo de Função com Múltiplos Argumentos de Saída
```matlab
function [area, volume] = cilindro(raio, altura)
    area = 2 * pi * raio * (raio + altura);
    volume = pi * raio^2 * altura;
end
```

### Exemplo de Chamada
```matlab
[area_c, vol_c] = cilindro(3, 5);
```

### Execução de uma Função
- O comando `return` interrompe a execução do arquivo M de função quando encontrado ou no fim do arquivo.

---

## 5. Aplicações Práticas

### Uso de Estrutura de Repetição com Vetor
```matlab
for i = 1:length(vetor)
    if vetor(i) > 4
        disp(vetor(i));
    end
end
```

### Uso de Função com Vetor
```matlab
function media = calcula_media(vetor)
    soma = 0;
    for i = 1:length(vetor)
        soma = soma + vetor(i);
    end
    media = soma / length(vetor);
end
```

### Exemplo de Script
```matlab
% cálculo da distância entre dois pontos
p = [1, 2, 3];
q = [4, 5, 6];
distancia = sqrt(sum((p - q).^2));
disp(distancia);
```

---

## 6. Pontos-chave para Estudo

| Tópico | Dica de Estudo |
|--------|---------------|
| **Estruturas de repetição** | Saiba quando usar `while` (condicional) vs `for` (contador). |
| **Contadores** | Inicialização, incremento, condição de parada. |
| **Vetores** | Índice começa em 1 (MATLAB) ou 0 (pseudocódigo). |
| **Funções** | Nome do arquivo = nome da função. |
| **Argumentos** | Instancie `varargin` para entrada variável, `varargout` para saída variável. |
| **Scripts vs Functions** | Scripts executam a sequência de comandos como digitados; Functions possuem parâmetros de entrada/saída e visibilidade limitada. |
| **Cuidado** | Não altere a variável de controle dentro do laço; dimensões devem coincidir em operações de vetores. |
| **Prática** | Utilize exercícios do livro e implemente algoritmo do comando de média das notas. |

---

## 7. Referências

- CHAPRA, S. C. Métodos numéricos e aplicados com MATLAB® para engenheiros e cientistas. 3. ed. Porto Alegre: AMGH, 2013.
- ASCENCIO, A. F. G.; CAMPUS, E. A. V. Fundamentos da Programação de Computadores: algoritmos, Pascal, C/C++ e Java. 3. ed. São Paulo: Pearson, 2012.
- FORBELLONE, A. L. V.; EBERSPÄCHER, H. F. Lógica de programação: a construção de algoritmos e estrutura de dados. 3. ed. São Paulo: Pearson, 2005.
- GILAT, A. MATLAB com aplicações em engenharia. 4. ed. Porto Alegre: Bookman, 2012.
- MANZANO, J. A. N. G.; OLIVEIRA, J. F. Algoritmos: lógica para desenvolvimento de programação de computadores. 28. ed. São Paulo: Érica, 2016.
- PALM III, W. J. Introdução ao MATLAB para engenheiros. 3. ed. Porto Alegre: AMGH, 2013.
- SEBESTA, R. W. Conceitos de linguagens de programação. 11. ed. Porto Alegre: Bookman, 2018.

---

## 8. Engine de Resposta para a Prova

Para o tipo de prova (resposta objetiva):
1. **Ler a questão com atenção** e identificar os comando (while, for, vetor, função).
2. **Analisar a estrutura de repetição** proposta (testa no início/ meado/fim).
3. **Trabalhar com vetores**: requisitar índice, contagem de elementos, manipulação de faixas.
4. **Criar sub-rotinas**: definir parâmetros de entrada/saída, chamar a função.

Para a questão discursiva:
1. **Explicar a estrutura de repetição** (enquanto ou para/faça).
2. **Mostrar o fluxo** do laço (teste, repetir, encerrar).
3. **Mostrar a aplicação de vetores** (declaração, acesso, edição, percurso).
4. **Criar função/sub-rotina** (parâmetros de entrada/saída, chamada).

---

**Resumo para Estudo — Importante:**

- A estrutura de repetição **while-end** testa a condição **no início**; se a condição for falsa, o laço **não executa**.
- A estrutura de repetição **for-end** é controlada por **variável de controle** e repete **um número determinado de vezes**.
- A estrutura de repetição **while...break** permite **encerração sob condição verdadeira em qualquer ponto** (ité de MATLAB).
- Um vetor é uma estrutura de dados **homogênea, unidimensional** acessada por **índice** (começa em 1 no MATLAB).
- Funções (sub-rotinas) são blocos de comandos reutilizáveis, com parâmetros de entrada e saída.
- O MATLAB permite funções com **número variável de argumentos** (`varargin`, `varargout`).
- A **estrutura de repetição é uma solução clássica** para problemas de processamento de coleções de dados.

---

*Gerado em: 2026-11-15*  
*Disciplina: Lógica de Programação — EAD Católica — Prova presencial 17/11 09h*  
*Identificador: resumo-Lógica de Programação-Unidade 3+4-Final.md*