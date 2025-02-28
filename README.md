# Atividades de Banco de Dados 

## ETAPA 1 - Modelagem Conceitual

Este projeto apresenta a modelagem conceitual de um sistema acadêmico, contendo três entidades principais: **CURSO, PROFESSOR e ALUNO**. A modelagem foi realizada utilizando o Visio, respeitando as regras de cardinalidade e integridade dos dados.

+ **CURSO:** Possui identificador, título, carga horária e professor (opcional).
+ **PROFESSOR:** Possui identificador, nome, área de atuação e leciona um único curso.
+ **ALUNO:** Possui identificador, nome, data de nascimento e notas, estando vinculado a um curso.

### Relacionamentos:

- 1:N → Um curso pode ter vários alunos.
- 1:1 → Um curso é lecionado por um único professor

#### A modelagem completa está disponível na imagem gerada e incluída neste repositório.
![Entidades, Relacienamentos e Atributos](etapa1-conceitual/Atividades%20de%20Banco%20de%20Dados.png)