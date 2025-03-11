# Modelagem física de dados

Usando o **phpMyAdmin e comandos SQL**, você deve fazer a **modelagem física** de um banco de dados chamado **tecinternet_escola_seunome** e nele criar as **tabelas**, **colunas** e **relacionamentos**.

💡*Não se esqueça de **guardar** todos os comandos SQL que utilizou na **modelagem física** em um arquivo Markdown (exemplo: **modelo-fisico.md**). Este arquivo deve ser colocado no seu repositório.*
---
## Criando Base de dados 
``` sql
CREATE DATABASE tecinternet_escola_kelly CHARACTER SET utf8mb4 ;
-- Criando tabelas
```

## 1. Cursos
``` sql
CREATE TABLE cursos( 
    id INT PRIMARY KEY NOT NULL AUTO_INCREMENT, 
    nome VARCHAR(60) NOT NULL , 
    carga_horaria INT NOT NULL , 
    professor_id INT NULL 

    );
```

## 2. Professores
``` sql
CREATE TABLE professores ( 
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(120) NOT NULL, 
    area_atuacao ENUM ('design','desenvolvimento','infra') NOT NULL, 
    curso_id INT 
    );
```

## 3. Alunos
``` sql
CREATE TABLE alunos ( 
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY, 
    nome VARCHAR(120) NOT NULL, 
    data_nasc DATE,
    nota_1 DECIMAL (4,2), 
    nota_2 DECIMAL (4,2),
    curso_id INT NOT NULL
    );
```
### Criando relacionamentos 

1. Cursos => professores
``` sql
ALTER TABLE cursos
    ADD CONSTRAINT fk_cursos_professores
    FOREIGN KEY (professor_id) REFERENCES professores(id);
```

2. Professores => cursos
``` sql
ALTER TABLE professores
    ADD CONSTRAINT fk_professores_cursos
    FOREIGN KEY (curso_id) REFERENCES cursos(id);
```

3. Alunos => cursos
``` sql
ALTER TABLE alunos
    ADD CONSTRAINT fk_alunos_cursos
    FOREIGN KEY (curso_id) REFERENCES cursos(id);
``` 
---
## Backup banco de dados e tabelas vazias
