# M4 | Tarefa 2 - Modelando um sistema (Etapa 3 - Parcial)
https://www.planttext.com
```
@startuml

title Instituição ABC - Class Diagram

class Aluno {
+Int id
+Int idCurso
+Int idContrato
+String name
+String cpf
+String email
+String phone
+DateTime birthday
+DateTime created_at
+DateTime updated_at
}

class Contrato {
+Int id
+String url_contrato
+DateTime created_at
+DateTime updated_at
}

class Professor {
+Int id
+Int idDepartamento
+Int idCargo
+String name
+String cpf
+String email
+String phone
+DateTime birthday
+DateTime admission
+DateTime created_at
+DateTime updated_at
}
class Coordenador {
+Int id
+Int idDepartamento
+Int idCargo
+String name
+String cpf
+String email
+String phone
+DateTime birthday
+DateTime admission
+DateTime created_at
+DateTime updated_at
}
class Funcionario {
+Int id
+Int idDepartamento
+String name
+String cpf
+String email
+String phone
+DateTime admission
+DateTime created_at
+DateTime updated_at
}

class Cargo {
+Int id
+String name
+DateTime created_at
+DateTime updated_at
}
class Especialidade {
+Int id
+String name
+DateTime created_at
+DateTime updated_at
}
class Historico {
+Int id
+Int idAluno
+Int idNota
+DateTime created_at
}
class Nota {
+Int id
+Int idDisciplina
+Decimal value
}

class Departamento {
+Int id
+String name
+DateTime created_at
+DateTime updated_at
}
class Curso {
+Int id
+Int idDepartamento
+String name
+DateTime created_at
+DateTime updated_at
}
class Disciplina {
+Int id
+Int idCurso
+Int idProfessor
+String name
+DateTime created_at
+DateTime updated_at
}
class Tarefa {
+Int idDisciplina
+String name
+String description
+DateTime deadline
+DateTime created_at
+DateTime updated_at
}
class Evento {
+Int id
+Int idDisciplina
+String name
+String description
+DateTime date
+DateTime created_at
+DateTime updated_at
}

Departamento "1" *-- "0..1"  Curso
Departamento "1" -- "0..1" Funcionario
Departamento "1" -- "0..n" Professor
Departamento "1" -- "1" Coordenador

Curso "1..n" *-- "1..n" Disciplina

Disciplina "1..n" -- "0..n" Aluno 
Disciplina "1..n" o-- "0..n" Evento
Disciplina "1..n" o-- "0..n" Tarefa
Disciplina "1..n" -- "0..n" Nota
Disciplina "1" --> "1" Professor


Professor "1" *-- "0..n" Especialidade
Cargo "1" *-- "1..n" Professor
Cargo "1" *-- "1..n" Funcionario
Cargo "1" *-- "1..n" Coordenador
Aluno o-- Historico
Aluno "1..n" *-- "1..n" Contrato
Historico "1"--> "1" Nota
@enduml
```
