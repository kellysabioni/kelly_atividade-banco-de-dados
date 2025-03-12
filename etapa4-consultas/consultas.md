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
