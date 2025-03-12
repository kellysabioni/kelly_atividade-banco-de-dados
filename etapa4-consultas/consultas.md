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
### 5. Faça uma consulta que mostre a quantidade de professores que cada área ("design", "infra", "desenvolvimento") possui.
``` sql
SELECT
	area_atuacao AS 'Área de Atuação',
    COUNT(nome) AS 'Qtde de Docentes'
FROM professores
GROUP BY area_atuacao
;
```
---
### 6. Faça uma consulta que mostre o nome dos alunos, o título e a carga horária dos cursos que fazem.
``` sql
SELECT
	alunos.nome AS Aluno,
    cursos.nome AS Curso,
    cursos.carga_horaria AS 'Carga Horaria'
    
FROM alunos JOIN cursos
ON alunos.curso_id = cursos.id 
ORDER BY aluno
;
```
---
### 7. Faça uma consulta que mostre o nome dos professores e o título do curso que lecionam. Classifique pelo nome do professor.
``` sql
SELECT
	professores.nome AS Professor,
    cursos.nome AS Curso        
FROM professores JOIN cursos
ON professores.curso_id = cursos.id 
ORDER BY Professor
;
```
---
### 8. Faça uma consulta que mostre o nome dos alunos, o título dos cursos que fazem, e o professor de cada curso.
``` sql
SELECT
	alunos.nome AS Aluno, 
    cursos.nome AS Curso,
    professores.nome AS Professor
FROM alunos
	JOIN cursos
    ON alunos.curso_id = cursos.id 

	JOIN professores
    ON professores.curso_id = cursos.id 

ORDER BY Aluno
;
```
---
### 9. Faça uma consulta que mostre a quantidade de alunos que cada curso possui. Classifique os resultados em ordem descrecente de acordo com a quantidade de alunos.
``` sql
SELECT
    cursos.nome AS Curso,
	COUNT(alunos.nome) AS Qtde
FROM alunos JOIN cursos
ON alunos.curso_id = cursos.id 
GROUP BY cursos.nome
ORDER BY qtde
;
```
---