# Atividades de Banco de Dados - Etapa 3

## C. Modelagem Física

Usando o **phpMyAdmin e comandos SQL**, você deve fazer a **modelagem física** de um banco de dados chamado **tecinternet_escola_seunome** e nele criar as **tabelas**, **colunas** e **relacionamentos**.

💡*Não se esqueça de **guardar** todos os comandos SQL que utilizou na **modelagem física** em um arquivo Markdown (exemplo: **modelo-fisico.md**). Este arquivo deve ser colocado no seu repositório.*

---

Ao final, exporte um backup do seu banco de dados com as **tabelas vazias** e coloque também em seu repositório.

---

## CRUD

💡*Não se esqueça de **guardar** todos os comandos SQL que utilizou na nesta **manipulação de dados** em um arquivo Markdown (exemplo: **comandos-crud.md**). Este arquivo deve ser colocado no seu repositório.*

### Cadastre pelo menos 5 cursos: 

1. Front-End, carga horária 40h
2. Back-End, carga horária 80h
3. UX/UI Design, carga horária 30h
4. Figma, carga horária 10h
5. Redes de Computadores, carga horária 100h

🚨 **Atenção:** por enquanto, deixe o campo `professor_id` como **nulo**.

### Cadastre pelo menos 5 professores: 

1. Jon Oliva, área infra
2. Lemmy Kilmister, área design
3. Neil Peart, área design
4. Ozzy Osbourne, área desenvolvimento
5. David Gilmour, área desenvolvimento

🚨 **Atenção:** durante o cadastro dos professores, associe **cada professor** a **um curso na ordem contrária** dos registros. 

Exemplos: 

- O primeiro professor (Jon Oliva, infra) será atribuido ao último curso (Redes de Computadores)
- O segundo professor (Lemmy, design) será atribuido ao penúltimo curso (Figma)

---

### Atualize os dados do campo `professor_id` da tabela cursos, associando cada curso ao seu professor correspondente.

---

### Cadastre pelo menos 10 alunos distribuidos aleatoriamente dentre os cursos, com datas de nascimento variadas, notas baixas e altas (sempre entre 0.00 e 10.00).

💡*Não se esqueça de **guardar** todos os comandos SQL que utilizou nesta **manipulação de dados** em um arquivo Markdown (exemplo: comandos-crud.md). Este arquivo deve ser colocado no seu repositório.*