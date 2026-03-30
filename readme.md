# Microservicio de Gestión de Tareas

API REST desarrollada con Flask para la gestión de tareas.

## Integrantes
- Cristina Silva (cristinaf17)
- [Sebastian antipan] (Seba13)

## Descripción
Microservicio que permite crear, listar, obtener y eliminar tareas mediante una API REST.

## Endpoints disponibles
| Método | Ruta | Descripción |
|--------|------|-------------|
| GET | / | Mensaje de bienvenida |
| GET | /health | Estado del servicio |
| GET | /tasks | Listar todas las tareas |
| GET | /tasks/<id> | Obtener tarea por ID |
| POST | /tasks | Crear nueva tarea |
| DELETE | /tasks/<id> | Eliminar tarea por ID |

## Estrategia de ramificación: GitFlow

Se eligió **GitFlow** porque permite una separación clara entre el código en producción (main) y el código en desarrollo (develop), lo cual es ideal para equipos colaborativos. Además, facilita el trabajo en paralelo mediante ramas feature y la corrección rápida de errores con ramas hotfix.

### Ramas utilizadas
- **main**: Código estable en producción.
- **develop**: Rama de integración para desarrollo.
- **feature/<nombre>**: Nuevas funcionalidades. Se crean desde develop y se integran a develop mediante Pull Request.
- **hotfix/<nombre>**: Correcciones urgentes. Se crean desde main y se integran a main mediante Pull Request.

### Ventajas de GitFlow en este proyecto
1. Trazabilidad clara del código mediante ramas separadas.
2. Permite revisiones de código a través de Pull Requests.
3. Facilita la colaboración sin afectar el código estable.
4. Ideal para proyectos con ciclos de release definidos.

## Convenciones de commits
Se utiliza la convención **Conventional Commits**:

| Prefijo | Uso |
|---------|-----|
| feat: | Nueva funcionalidad |
| fix: | Corrección de errores |
| hotfix: | Corrección urgente en producción |
| ci: | Cambios en el pipeline CI/CD |
| docs: | Cambios en documentación |
| test: | Agregar o modificar pruebas |

Ejemplo: `feat: agregar endpoint para obtener tarea por ID`

## Flujo de merge
1. Crear rama desde develop (features) o main (hotfix).
2. Realizar los cambios y hacer commits.
3. Subir la rama con `git push`.
4. Crear un Pull Request en GitHub.
5. Revisar el código y aprobar.
6. Hacer merge y eliminar la rama.

## Naming de ramas
- `main` → Producción
- `develop` → Desarrollo
- `feature/<descripcion-corta>` → Nueva funcionalidad
- `hotfix/<descripcion-corta>` → Corrección urgente

## Estructura del proyecto

microservicio-tarea/
├── .github/
│ └── workflows/
│ └── ci.yml
├── app.py
├── test_app.py
├── requirements.txt
└── README.md

## Pipeline CI/CD
Se configuró **GitHub Actions** para ejecutar automáticamente:
- Instalación de dependencias
- Ejecución de pruebas con pytest

El pipeline se activa con:
- Push a la rama `develop`
- Pull Request hacia `main`

## Tecnologías
- Python 3.10
- Flask
- Pytest
- GitHub Actions

## Uso de IA
Se utilizó Perplexity AI como apoyo para consultar buenas prácticas de Git, estructura de pipelines CI/CD y resolución de errores técnicos. Todas las decisiones técnicas y justificaciones fueron elaboradas por el equipo.