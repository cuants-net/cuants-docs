# Guía de Edición y Contribución – Cuants Docs

Este documento explica cómo colaborar con el repositorio de documentación `cuants-docs`. Está orientado a quienes quieran aportar nuevos contenidos o mejorar los existentes.

## 1. Estructura general del repositorio

Las secciones están organizadas en carpetas por temática:

- `/conceptos/`: teoría y fundamentos
- `/programacion/`: herramientas, snippets, flujos de código
- `/practicas/`: ejercicios guiados y desafíos técnicos
- `/aplicaciones/`: casos reales o notebooks aplicados
- `/proyectos/`: presentación de proyectos funcionales (con enlaces a sus repositorios independientes)

Cada entrada es un archivo `.md` ubicado dentro de la carpeta correspondiente.

## 2. Reglas de edición

- Escribir en formato Markdown plano.
- Usar enlaces Markdown estándar: `[texto](../carpeta/archivo.md)`
- No usar enlaces de estilo `[[wikilinks]]`.
- Usar títulos consistentes con `#`, `##`, `###` para estructurar el contenido.
- Incluir un encabezado al inicio de cada archivo con los siguientes datos:

```markdown
# Título del documento

  Fecha: AAAA-MM-DD  
  Tags: tema1, tema2, tema3
```

## 3. Convenciones de nombres

* Los archivos `.md` deben tener nombres en minúsculas, usando guiones bajos en lugar de espacios.
  Ejemplo: `series_temporales_basicas.md`

* Evitar tildes, espacios o mayúsculas en los nombres de archivo.

## 4. Cómo agregar contenido

1. Crear o editar un archivo `.md` en la carpeta correspondiente.

2. Agregar enlaces a otras notas si es necesario, usando rutas relativas.

3. Hacer `git add`, `git commit` y `git push` con un mensaje claro:

```
git commit -m "Agrega nota sobre correlación lineal en prácticas"

```

4. Si trabajás desde un fork, crear un Pull Request para que se revisen los cambios.

## 5. Estilo general

* Escribir en tono claro, técnico y directo.

* Priorizar ejemplos aplicados cuando sea posible.

* Mantener un estilo uniforme en títulos, código y secciones.

* Incluir enlaces a recursos externos o a otras entradas del repositorio si aportan valor.

## 6. Licencia

El contenido de este repositorio está disponible bajo la licencia Creative Commons Attribution 4.0 (CC BY 4.0).
Se permite copiar, modificar y reutilizar el contenido siempre que se cite la fuente original.
