# Atividades de Banco de Dados - Etapa 4 (FINAL)

## CRUD - Consultas

---
### 1. Faça uma consulta que mostre os alunos que nasceram antes do ano 2009
``` sql
SELECT * FROM alunos WHERE alunos.data_nasc <= '2008-12-31';
```
---
### 2. Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.
``` sql
SELECT 
	nome,
    FORMAT ((nota_1 + nota_2)/2,2) AS media
FROM alunos;
```
---
### 3. Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.
``` sql
SELECT 
	nome AS Curso,
	(carga_horaria * 0.25) AS "Limite de Faltas"
FROM cursos
ORDER BY Curso
;
```
---
### 4. Faça uma consulta que mostre os nomes dos professores que são somente da área "desenvolvimento".
``` sql
SELECT 
	area_atuacao AS 'Área de Atuação',
    nome AS Professor
FROM professores
WHERE area_atuacao = 'desenvolvimento'
ORDER BY Professor
;
```
---