# Modelagem de dados para uma universidade

#### O seguinte projeto tem por objetivo realizar um modelo de dados para o funcionamento interno de uma universidade. O nosso cliente já forneceu alguns requisitos sem a necessidade de um formulário para a coleta de dados tipo 1, mas ao decorrer do desenvolvimento pode surgir possíveis anomalias que só serão descobertas pelo modelista de dados ou pelo cliente. Deverá ser feito um diagrama de dados e um dicionário de dados. 

---

## Objetivo do banco de dados:
### Realizar controle centralizado de alunos, professores, cursos, disciplica, histórico escolar e cursos

---

## Fases do projeto:
- Levantamento dos requisitos
- Identificação de entidades e relacionamentos
- Modelo E-R
- Dicionário de dados
- Normalização
- Implementação
- Testes básicos

---

## Levantamento dos requisitos:
- Um aluno só poderá ser matriculado em um curso por vez
- Alunos possuem um código de verificação (RA)
- Cursos são compostos por disciplinas
- Cada disciplina terá até 30 alunos
- As disciplinas podem ser obrigatórias ou optativas a depender do curso
- As disciplinas pertencem a departamentos específicos
- Cada disciplina possui um código de identificação
- Alunos podem trancar matrícula, não estando então matriculados em nenhuma disciplina no semestre
- Em cada semestre cada aluno poderá se matricular em até nove disciplinas
- O aluno só poderá reprovar três vezes na mesma disciplina
- A faculpade terá no máximo 3.000 alunos matriculados simultaneamente em 10 cursos distintos
- Entram 300 alunos novos por ano
- Existem 90 disciplinas no total disponíveis
- Um histórico escolar traz todas as disciplinas cursadas por um aluno, inclusive a nota final, frequência e período do curso realizado
- Professores podem ser cadastrados mesmo sem lecionar nenhuma disciplina
- Existem 40 professores trabalhando na universidade
- Cada professor irá lecionar até quatro disciplinas diferentes
- Cada professor é vinculado a um departamento
- Professores são identificados por um código de professor

---

## Identificação da entidade:
- Aluno
- Professor
- Disciplina
- Curso
- Departamento

---

## Identificação dos relacionamentos:
- Aluno está matriculado em curso
- Aluno cursa disciplina
- Aluno realizou disciplina
- Disciplina pertence a curso
- Professor ministra disciplina
- Professor pertence a departamento
- Departamento é responsável por disciplina
- Departamento controla curso
- Disciplina depende da disciplina (Requisito)

---

## Identificando atributos - aluno:
- Número da matrícula
- Nome
- Sobrenome
- Endereço:
- Rua
- Número
- Bairro
- CEP
- Cidade
- Estado
- Código do curso 

---

## Identificando atributos - Professor:
- Código do professor
- Nome
- Sobrenome
- Código do departamento

---

## Identificando atributos - Disciplina:
- Código da disciplina
- Nome da disciplina
- Descrição Curricular
- Código do departamento
- Número de alunos

---

## Identificando atributos - Curso:
- Código do curso
- Nome do curso
- Código do departamento

---

## Identificando atributos - Departamento:
- Código do Departamento
- Nome do Departamento

---

## Esboço - Diagrama ER:
![Image](https://github.com/user-attachments/assets/c6273ee4-e595-44ba-92a1-48940d3ddfa6)

---

## Novas entidades:
- **Turma**
- **Histórico**
  
---

## Novos relacionamentos:
- **Curso** gera **Turma**
- **Aluno** pertence a **Turma**
- **Hisrórico** compões **Disciplina**
- **Histórico** pertence a um **Aluno**

---

# Novos atributos:
- **Histórico**: Cód. histórico, Notas, Média, Frequência, Período Realização, RA, Cód. Disciplina
- **Turma**: Cód. turma, Período, Cód. curso, Número de alunos, Data início, Data fim

---

## Intermediário - Diagrama ER:
![Image](https://github.com/user-attachments/assets/bdd4a711-ed99-495e-a873-a20b565eb582)

---

# ATUALIZAÇÃO
- Atributos de cada entidade foi adicionada
- Atributos **contato** e **endereco** foram adicionados às entidades **Aluno** e **Professor**

## Intermediário 2 - Diagrama ER:
![Image](https://github.com/user-attachments/assets/0b39784d-1953-4340-9193-abeff02abe6a)

---

# ATUALIZAÇÃO 2
- Renomeação do relacionamento entre as entidades **Professor** e **Disciplina** para **Ministra**
- Inserção do autorelacionamento da entidade **Disciplina**
- Cálculo das cardinalidades

## Intermediário 3 - Diagrama ER:
![Image](https://github.com/user-attachments/assets/41653704-f54f-41ea-899a-85655ef5beca)
