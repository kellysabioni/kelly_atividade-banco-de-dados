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
### 10. Faça uma consulta que mostre o nome dos alunos, suas notas, médias, e o título dos cursos que fazem. Devem ser considerados somente os alunos de Front-End e Back-End. Mostre os resultados classificados pelo nome do aluno.
``` sql
SELECT
	alunos.nome AS Aluno,
    alunos.nota_1 AS 'Nota 01',
    alunos.nota_2 AS 'Nota 02',
    FORMAT(((nota_1 + nota_2)/2),2) AS 'Media Final',
    cursos.nome AS Curso        
FROM alunos JOIN cursos
ON alunos.curso_id = cursos.id 
WHERE cursos.nome = 'Front-End' OR  cursos.nome = 'Back-End'
ORDER BY Aluno
;
```
---
### 11. Faça uma consulta que altere o nome do curso de Figma para Adobe XD e sua carga horária de 10 para 15.
``` sql
UPDATE cursos SET nome = 'Adobe XD' AND carga_horaria = 15 WHERE id = 4;
```
---
### 12. Faça uma consulta que exclua um aluno do curso de Redes de Computadores e um aluno do curso de UX/UI.
``` sql
-- Exclusão aleatória
DELETE FROM alunos 
WHERE id IN (
    (SELECT id FROM alunos WHERE curso_id = 5 LIMIT 1),
    (SELECT id FROM alunos WHERE curso_id = 3 LIMIT 1)
);

-- Exclusão determinando o aluno 
DELETE FROM alunos WHERE id IN ( 1 , 7 );
```
---
### 13. Faça uma consulta que mostre a lista de alunos atualizada e o título dos cursos que fazem, classificados pelo nome do aluno.
``` sql
SELECT
	alunos.nome AS Aluno,
    cursos.nome AS Curso
FROM alunos 
	JOIN cursos
	ON alunos.curso_id = cursos.id 
ORDER BY aluno
;
```
---


## 🔥 DESAFIOS 🔥
---
1. Criar uma consulta que calcule a idade do aluno
``` sql
-- Usando DATEDIFF
SELECT 
    nome AS Aluno,
    -- FLOOR arredonda para baixo 
    --Divisão por 365.25 para definir os anos considerando anos bissextos 
    FLOOR (DATEDIFF(CURRENT_DATE, data_nasc) / 365.25) AS Idade
FROM alunos;

-- Usando TIMESTAMPDIFF
SELECT 
    nome AS Aluno,
    -- ROUND arredonda para numero intero
    ROUND(TIMESTAMPDIFF(YEAR, data_nasc, CURRENT_DATE)) AS Idade
FROM alunos;
```
---
2. Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média **maior ou igual a 7**.
``` sql
SELECT
    nome,
    FORMAT ((nota_1 + nota_2)/2,2) AS media
FROM alunos
WHERE
    (nota_1 + nota_2)/2 >= 7
ORDER BY media DESC
;
```
---
3. Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média **menor que 7**.
``` sql
SELECT
    nome,
    FORMAT ((nota_1 + nota_2)/2,2) AS media
FROM alunos
WHERE
    (nota_1 + nota_2)/2 <= 7
ORDER BY media DESC
;
```
---
4. Criar uma consulta que mostre a quantidade de alunos com média **maior ou igual a 7**.
``` sql
SELECT
    COUNT(nome) AS Qtde
FROM alunos
WHERE
    (nota_1 + nota_2)/2 >= 7
;
```
