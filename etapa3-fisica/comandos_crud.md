# Comandos CRUD

## Cadastrando cursos
``` sql
INSERT INTO cursos (nome, carga_horaria)
VALUES ('Front-End', 40),
('Back-End', 80),
('UX/UI Design', 30),
('Figma', 10),
('Redes de Computadores', 100);
```
---
## Cadastrando professores
``` sql
INSERT INTO professores (nome, area_atuacao, curso_id)
VALUES ('Jon Oliva', 'infra',5),
('Lemmy Kilmister', 'design',4),
('Neil Peart', 'design',3),
('Ozzy Osbourne', 'desenvolvimento',2),
('David Gilmour', 'desenvolvimento',1);
```
---
### Cadastrando alunos 
``` sql
INSERT INTO alunos (nome, curso_id, data_nasc, nota_1, nota_2)
VALUES (
('Lucas Almeida',    1, '1993-07-12', 8.45, 8.02),
('Maria Souza',      2, '1995-03-22', 5.72, 3.60),
('Pedro Oliveira',   3, '2001-11-05', 9.68, 7.35),
('Ana Costa',        4, '1998-01-28', 6.14, 10.00),
('Carlos Pereira',   5, '2003-09-16', 7.93, 4.88),
('Joana Silva',      2, '1994-04-19', 4.88, 7.93),
('Fernanda Rocha',   3, '1999-08-02', 10.00, 6.14),
('Gabriel Santos',   4, '2000-12-25', 7.35, 9.68),
('Ricardo Martins',  1, '1996-05-30', 3.60, 5.72),
('Juliana Ferreira', 5, '1997-10-09', 8.02, 7.45)
);
```
---