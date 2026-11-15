---
title: "Resumo Final — Banco de Dados (Unidade 1 + 2)"
date: 2026-11-15
tags: [Banco de Dados, Modelagem, SI, BD, SGBD, MER, SQL, Unidade 1+2, Faculdade, prova-17-11]
---

# Resumo Final — Banco de Dados (Unidade 1 + 2)

Fonte: https://goo.gl/aL5fbk

## Conceitos-chave
- **Dado:** registro físico; informação: dados organizados com valor; conhecimento: compreensão das informações.
- **SI:** elementos que interagem, manipulam dados e geram informações.
- **BD:** coleção de dados relacionados; subconjunto da base de dados. **SGBD:** software que gerencia o BD; funções: segurança, integridade, concorrência, recuperação, DDL/DML.
- **Modelo de Dados:** definição abstrata de objetos e operadores. **Arquitetura ANSI/SPARC:** 3 níveis (externo, conceitual, interno); mapeamentos; catálogo (metadados).
- **Hierárquico:** árvore; top-down; ponteiros. **Rede:** grafo; navegação flexível.
- **Relacional:** Codd (1970); tabelas bidimensionais; SQL; teoria dos conjuntos.
- **Objeto-Relacional (MRE):** extensão do relacional; incorpora OO.
- **MER:** entidades (retângulos), relacionamentos (linhas), cardinalidades (números).
- **Entidade-tipo:** classe de entidades.
- **Atributos:** simples, composto, monovalorado, multivalorado, opcional, obrigatório.
- **Relacionamento:** associação entre entidades; expresso por verbo.
- **Cardinalidade:** quantificação (1,1), (1,N), (N,N).
- **Chaves:** superchave, candidata, primária (PK), secundária, estrangeira (FK).
- **Normalização:** decomposição de esquemas; elimina redundâncias. **Dependência Funcional:** X → Y.
- **Formas Normais:** 1FN (sem grupos repetitivos), 2FN, 3FN.
- **Método tradicional de SBD:** define o que, como e quando dos processos.
- **Projeto de BD:** organização (estrutura, conteúdo, aplicações). **Modelagem conceitual:** abstração da realidade.
- **Minimundo:** parcela do mundo-real de interesse.
- **Independência de dados:** aplicações não dependem da estrutura de armazenamento.
- **Dados não redundantes:** item aparece uma vez no BD.
- **Metodologia:** passo a passo com fases. **Ciclo de vida:** planejamento, análise, projeto, implementação, testes, implantação, manutenção.
- **Segurança:** controle discriminatório/mandatário; trilha de auditoria; criptografia; visões; GRANT/REVOKE.
- **Integridade:** precisão e correção; chave primária/estrangeira; triggers; asserções.
- **Concorrência:** múltiplas transações; ACID; atualização perdida, leitura suja, análise inconsistente; serialização; bloqueios C/X; deadlock.
- **Recuperação:** backup e restore do SGBD. **Confiabilidade** e **desempenho:** sem quedas; tempo das operações.
- **Portabilidade/Escalabilidade:** migração entre fabricantes; evolução para versões modernas.
- **SQL:** padrão ISO/ANSI; módulos: DDL, DML, DCL, DTL, DQL. **View:** relação virtual. **Índices:** Primary, Unique, Index, Clustered, NonClustered, Btree, Rtree, Hash, Fulltext Search.

## RESPOSTA-MODELO para a discursiva
- O **modelo relacional** armazena dados em tabelas (relações) com linhas (tuplas) e colunas (atributos); é simples, uniforme e formal.
- O **método tradicional de SBD** define o que, como e quando dos processos; o **projeto de BD** determina a organização e é conduzido por metodologia.
- A **arquitetura ANSI/SPARC** divide o BD em 3 níveis (externo, conceitual, interno), com mapeamentos e catálogo.
- O **MER** representa o mundo-real por meio de **entidades** (retângulos), **relacionamentos** (linhas) e **cardinalidades** (números).
- As **chaves** (superchave, candidata, primária, secundária, estrangeira) permitem identificar univocamente as tuplas e representar relacionamentos.
- A **normalização** (baseada na matemática relacional, Codd 1970) decompõe esquemas de relação para eliminar redundâncias, com 1FN, 2FN, 3FN, BCNF, 4FN, 5FN.
- O **projeto de BD** segue o **ciclo de vida**: planejamento, análise, projeto, implementação, teste, implantação e manutenção.
- As **características de BD**: segurança, integridade, compartilhamento, integração, recuperação, confiabilidade, desempenho, concorrência, distribuição, portabilidade e escalabilidade.
- **Concorrência:** múltiplas transações simultâneas; ACID; controle por bloqueios; níveis de isolamento; serialização.
- **SQL:** padrão ISO/ANSI; módulos DDL, DML, DCL, DTL, DQL; view e índices; normalização (1FN, 2FN, 3FN).

## Régua do corretor
1. Dado
2. Informação
3. Conhecimento
4. Sistema de Informação
5. Banco de Dados
6. Base de Dados
7. SGBD
8. Modelo de Dados
9. Modelo Relacional
10. Hierárquico
11. Rede
12. Objeto-Relacional
13. MER
14. Entidade-tipo
15. Atributo
16. Relacionamento
17. Cardinalidade
18. Chave Primária (PK)
19. Chave Estrangeira (FK)
20. Normalização
21. 1FN / 2FN / 3FN
22. Método Tradicional de SBD
23. Projeto de Banco de Dados
24. Modelagem Conceitual
25. Minimundo
26. Independência de Dados
27. Segurança
28. Integridade
29. Concorrência
30. Recuperação
31. SQL
32. DDL / DML / DCL / DTL / DQL
33. View / Índices
