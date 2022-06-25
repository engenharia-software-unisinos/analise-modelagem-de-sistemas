# M4 | Tarefa 2 - Modelando um sistema (Etapa 3 - Parcial)
https://www.planttext.com
```

@startuml

title Instituição ABC - Class Diagram

class AccountController { 
+AccountService service 
}
class AlunoController { 
+AlunoService service 
}
class ProfessorController { 
+ProfessorService service 
}
class FuncionarioController { 
+FuncionarioService service 
}
class CoordenadorController { 
+CoordenadorService service 
}
class DepartamentoController { 
+DepartamentoService service 
}
class CursoController { 
+CursoService service 

}

class AccountService {
+DbContext context
+LoggerService logger
}
class AlunoService {
+DbContext context
+LoggerService logger
}
class ProfessorService {
+DbContext context
+LoggerService logger
}
class FuncionarioService {
+DbContext context
+LoggerService logger
}
class CoordenadorService {
+DbContext context
+LoggerService logger
}
class DepartamentoService {
+DbContext context
+LoggerService logger
}
class CursoService {
+DbContext context
+LoggerService logger
}
class LoggerService {
+ILogger logger
}

class DbContext {
+DbSet<Aluno> Alunos
+DbSet<Professor> Professores
+DbSet<Funcionario> Funcionarios
+DbSet<Coordenador> Coordenadores
+DbSet<Curso> Cursos
+DbSet<Departamento> Departamentos
+DbSet<Evento> Eventos
+DbSet<Historico> Historicos
+DbSet<Nota> Notas
+DbSet<Especialidade> Especialidades
+DbSet<Cargo> Cargos
}

class Aluno {
+Int id
+String name
+String cpf
+String email
+String phone
+DateTime birthday
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
+Int idCurso
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
class Tarefa {
+Int idCurso
+String name
+String description
+DateTime deadline
+DateTime created_at
+DateTime updated_at
}
class Evento {
+Int id
+Int idCurso
+Int idProfessor
+String name
+String description
+DateTime date
+DateTime created_at
+DateTime updated_at
}

AccountController "1" --> "1" AccountService
ProfessorController "1" --> "1" ProfessorService
AlunoController "1" --> "1" AlunoService
CursoController "1" --> "1" CursoService
FuncionarioController "1" --> "1" FuncionarioService
DepartamentoController "1" --> "1" DepartamentoService
CoordenadorController "1" --> "1" CoordenadorService

AccountService "1" --> "1" LoggerService
ProfessorService "1" --> "1" LoggerService
AlunoService "1" --> "1" LoggerService
CursoService "1" --> "1" LoggerService
FuncionarioService "1" --> "1" LoggerService
DepartamentoService "1" --> "1" LoggerService
CoordenadorService "1" --> "1" LoggerService
AccountService "1" --> "1" DbContext
ProfessorService "1" --> "1" DbContext
AlunoService "1" --> "1" DbContext
CursoService "1" --> "1" DbContext
FuncionarioService "1" --> "1" DbContext
DepartamentoService "1" --> "1" DbContext
CoordenadorService "1" --> "1" DbContext

Departamento "1" *-- "0..1"  Curso
Departamento "1" -- "0..1" Funcionario
Departamento "1" -- "0..n" Professor
Departamento "1" -- "1" Coordenador

Curso "1..n" -- "0..n" Aluno 
Curso "1..n" o-- "0..n" Evento
Curso "1..n" o-- "0..n" Tarefa
Curso "1..n" -- "0..n" Nota
Evento "1..n" --> "1" Professor


Professor "1" *-- "0..n" Especialidade
Cargo "1" *-- "1..n" Professor
Cargo "1" *-- "1..n" Funcionario
Cargo "1" *-- "1..n" Coordenador
Aluno o-- Historico
Historico "1"--> "1" Nota
@enduml
```
