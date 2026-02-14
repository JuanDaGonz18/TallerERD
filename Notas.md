

# Registro de Trabajo en Clase - Taller 2

## Fecha de la sesión
14/02/2026

## Integrantes presentes
- Juan David González Rubio
- Josue David Sarmiento
- Julián Barragán Pérez

## Actividades realizadas en clase

Durante la sesión se realizó el análisis del caso base **Clínica Salud Viva**, identificando las entidades principales del dominio y sus relaciones.

### Discusión del equipo

- Se analizaron los procesos principales: agendamiento de citas, atención médica y facturación.
- Se discutió qué entidades eran obligatorias según el enunciado.
- Se evaluó si "Especialidad" debía modelarse como atributo o entidad independiente.
- Se revisó cómo debía relacionarse Factura con Cita.

### Decisiones de modelado tomadas

1. Especialidad se modela como entidad independiente para evitar redundancia y permitir escalabilidad.
2. Cita se definió como entidad central, ya que conecta paciente, médico y especialidad.
3. Factura depende de Cita, ya que representa el cobro de un servicio específico.
4. Se definió que:
	- Un paciente puede tener muchas citas (1:N).
	- Un médico puede atender muchas citas (1:N).
	- Una especialidad puede estar asociada a muchas citas (1:N).
	- Una cita puede generar 0 o 1 factura (1:0..1).

### Herramientas utilizadas

- Discusión inicial en papel.
- Modelado preliminar en draw.io.
- Revisión grupal del modelo antes de consolidarlo.

### Avance alcanzado

- Se completó el modelo ER preliminar con entidades, atributos, claves primarias y foráneas.
- Se definieron correctamente las cardinalidades.
- Se dejó listo el borrador del diagrama para ser refinado en la entrega final.

---

## Boceto inicial del modelo

Se realizó un boceto preliminar en draw.io incluyendo:

- Entidades: Paciente, Médico, Especialidad, Cita y Factura.
- Identificación de claves primarias (PK).
- Identificación de claves foráneas (FK).
- Cardinalidades entre entidades.

El archivo correspondiente quedó guardado como: `clase/modelo-er-borrador.drawio`

---

## Tareas definidas para complementar el taller

| Tarea asignada                     | Responsable | Fecha estimada |
|------------------------------------|-------------|----------------|
| Refinar modelo ER final            | Juan David González | 16/02/2026     |
| Elaborar diagrama de contexto final| Josue Sarmiento           | 17/02/2026     |
| Redactar informe técnico           | Julián Barragán Pérez y Juan David González    | 18/02/2026     |
| Investigación y referencias        | Julián Barragán Pérez     | 18/02/2026     |
| Revisión general y ajustes finales | Todo el equipo            | 19/02/2026 |

---

Este documento resume el trabajo colaborativo realizado durante la sesión del Taller 2 en el curso AREM - Universidad de La Sabana.

