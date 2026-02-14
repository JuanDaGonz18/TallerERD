# Taller 2: Modelo de Información y Diagrama de Contexto

## Integrantes

Julián Barragán Pérez
Juan David González Rubio
Josue Sarmiento

## Objetivo

Definir y modelar las entidades principales del dominio de la Clínica Salud Viva y representar los flujos de información entre actores y sistemas mediante un Modelo Entidad–Relación (ERD) y un Diagrama de Contexto de negocio.

---

## Caso base: Clínica Salud Viva

En este taller se trabajará sobre el caso base de la Clínica Salud Viva. El objetivo es que los equipos construyan un modelo reutilizable que luego podrán adaptar a clientes reales.

### Resumen del caso

- La clínica ofrece servicios presenciales y virtuales.
- Pacientes agendan citas; médicos gestionan agendas; personal administrativo valida cobertura con aseguradoras y genera facturación.

---

## Contexto y alcance

Los datos principales abarcan pacientes, médicos, especialidades, citas y facturación. Se asume interoperabilidad básica entre un ERP clínico, la base central de pacientes y sistemas de terceros (aseguradoras).

---

## Modelo Entidad–Relación (Caso Base)

### Entidad: Paciente

- PK: `id_paciente`
- Atributos: `tipo_documento`, `numero_documento`, `nombres`, `apellidos`, `fecha_nacimiento`, `telefono`, `correo`, `direccion`, `estado`

### Entidad: Médico

- PK: `id_medico`
- Atributos: `nombres`, `apellidos`, `numero_licencia`, `telefono`, `correo`, `estado`

### Entidad: Especialidad

- PK: `id_especialidad`
- Atributos: `nombre_especialidad`, `descripcion`

### Entidad: Cita

- PK: `id_cita`
- FKs: `id_paciente` → `Paciente`, `id_medico` → `Médico`, `id_especialidad` → `Especialidad`
- Atributos: `fecha`, `hora`, `modalidad`, `estado`, `motivo_consulta`, `observaciones`

### Entidad: Factura

- PK: `id_factura`
- FK: `id_cita` → `Cita`
- Atributos: `fecha_emision`, `valor_total`, `estado_pago`, `metodo_pago`

---

## Relaciones y cardinalidades (resumen)

- `Paciente (1) — (N) Cita` — Un paciente puede tener muchas citas.
- `Médico (1) — (N) Cita` — Un médico puede atender muchas citas.
- `Especialidad (1) — (N) Cita` — Una especialidad puede asociarse a muchas citas.
- `Cita (1) — (0..1) Factura` — Una cita puede generar cero o una factura.

---

## Decisiones de modelado

1. Mantener `Especialidad` como entidad independiente para evitar redundancia y facilitar la gestión de catálogos.
2. `Cita` actúa como entidad central que conecta pacientes, médicos y especialidades.
3. `Factura` depende de `Cita`, ya que la facturación corresponde a un servicio prestado.
4. Permitir `Cita` sin `Factura` (p. ej. canceladas o pendientes de facturación).

---

## Diagrama de Contexto

El diagrama de contexto del sistema se encuentra en el archivo adjunto a continuación.

**Archivo:** `Diagrama de contexto.drawio.png`

![Diagrama de contexto](./Diagrama%20de%20contexto.drawio.png)

---

## Licencia

Material del curso de Arquitectura Empresarial — Universidad de La Sabana. Uso académico bajo licencia MIT.
