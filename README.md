# astah-modelado
Taller de modelado con Astah
Documentación de Diagramas de Clases
Este repositorio contiene dos diagramas de clases modelados en UML, correspondientes a dos sistemas distintos: un sistema de citas médicas y un sistema de gestión de autos en una concesionaria.
---
Sistema de Citas Médicas

Este sistema modela el proceso mediante el cual un Paciente agenda una Cita con un Médico.

Clases

- **Paciente**
  - Atributos:
    - nombre : String
    - correo : String
  - Relaciones:
    - Un paciente agenda cero o más citas (0..*).

- **Cita**
  - Atributos:
    - fecha : Date
    - estado : String
  - Relaciones:
    - Es agendada por un solo paciente (1).
    - Es atendida por un solo médico (1).

- **Médico**
  - Atributos:
    - nombre : String
    - especialidad : String
  - Relaciones:
    - Un médico puede atender múltiples citas (*).

Relaciones Clave

- Paciente —(1)--->(0..*)— Cita: asociación agenda.
- Cita —(*)--->(1)— Médico: asociación atiende.

---

Sistema de Concesionaria de Autos

Este sistema representa cómo una Concesionaria administra su inventario de Autos.

Clases

- **Auto**
  - Atributos:
    - modelo : String
    - marca : String
    - anoFabricacion : int
    - disponible : boolean
    - precio : double
  - Métodos:
    - getInformacion() : String
    - actualizarPrecio() : void
    - isDisponible() : boolean
    - setDisponible() : void
    - getModelo() : String
    - getPrecio() : double

- **Concesionaria**
  - Atributos:
    - inventario : List<Auto>
  - Métodos:
    - agregarAuto() : void
    - mostrarAutosDisponibles() : void
    - venderAuto() : boolean

Relaciones Clave

- Concesionaria —(1)◆--->(0..*)— Auto: relación de composición, donde la concesionaria es dueña de los autos en su inventario.

---

Herramientas Utilizadas

- Herramienta de modelado: Astah UML
- Lenguaje de modelado: UML (Unified Modeling Language)
