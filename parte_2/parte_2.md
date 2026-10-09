# Parte 2

## 1. Flujo colaborativo

**Planteamiento:** Ordenar las operaciones necesarias para colaborar en el repositorio de otro desarrollador: Push, Fork, Pull Request, Clone, Merge, Commit, Review, Branch y Modificar archivos. Se incluyen las operaciones auxiliares necesarias.

**Explicación:**

1. **Fork:** En GitHub, creo una copia del repositorio original bajo mi propia cuenta. Esto me permite proponer cambios sin tener permisos de escritura en el proyecto original.
2. **Clone:** Descargo mi Fork a la computadora para trabajar con una copia local.
3. **Branch:** Creo y cambio a una rama de trabajo para aislar mis cambios de la rama principal.
4. **Modificar archivos:** Edito el código o los documentos necesarios y compruebo que los cambios sean correctos.
5. **Commit:** Guardo un conjunto coherente de cambios en el historial local, acompañado de un mensaje descriptivo.
6. **Push:** Subo la rama local a mi Fork en GitHub.
7. **Pull Request:** Desde GitHub, solicito integrar los cambios de mi rama del Fork en una rama del repositorio original. El Pull Request (PR) permite discutir y revisar la propuesta; no incorpora los cambios por sí solo.
8. **Review:** El propietario o los colaboradores revisan el PR. Pueden aprobarlo, solicitar cambios o rechazarlo.
9. **Modificar, Commit y Push nuevamente (si se solicitan cambios):** Actualizo la misma rama y esos nuevos commits se reflejan en el PR existente.
10. **Merge:** Una vez aprobado y cumplidas las condiciones del proyecto, se integra el PR en la rama de destino del repositorio original.

Como operación complementaria, después de que el repositorio original recibe cambios, puedo actualizar mi Fork y mi copia local para trabajar con la versión más reciente.

## 2. Fork y Clone

**Planteamiento:** Analizar la afirmación: “Clone crea una copia del proyecto dentro de mi cuenta de GitHub”. Explicar si es correcta y distinguir Fork de Clone.

**Explicación:** La afirmación es incorrecta. **Clone** copia el repositorio desde GitHub a un directorio de mi computadora; por sí solo no crea ningún repositorio dentro de mi cuenta de GitHub. **Fork** crea en GitHub una copia del repositorio bajo mi cuenta. En un flujo colaborativo normalmente primero hago Fork y después clono ese Fork para trabajar localmente.

## 3. Pull Request

**Planteamiento:** Después de realizar Fork, Clone, Branch, modificar archivos, Commit y Push, determinar si los cambios ya forman parte del repositorio original y qué falta para incorporarlos.

**Explicación:** No. El Push sube los cambios a mi Fork, no al repositorio original. Debo abrir un Pull Request dirigido a la rama correspondiente del repositorio original. El propietario o los colaboradores revisan la propuesta y, si la aprueban, realizan Merge para incorporar los cambios.

## 4. Request Changes

**Planteamiento:** El propietario revisa mi Pull Request y selecciona **Request Changes**. Explicar qué debo hacer, si necesito crear otro Pull Request y qué sucede al volver a hacer Push.

**Explicación:** Debo atender los comentarios, modificar los archivos en la misma rama local asociada al Pull Request, crear uno o más commits con las correcciones y hacer Push de esa rama a mi Fork. No necesito abrir otro Pull Request: el existente se actualiza automáticamente con los nuevos commits. Después, el propietario puede revisar nuevamente los cambios.

## 5. Merge y repositorio local

**Planteamiento:** Un Pull Request fue aceptado y se realizó Merge en GitHub, pero el repositorio local del propietario todavía no contiene los cambios. Explicar por qué y qué operación debe realizarse.

**Explicación:** El Merge actualizó la rama del repositorio remoto en GitHub, pero no modifica automáticamente las copias locales de los colaboradores. El propietario debe traer esos cambios a su repositorio local; por ejemplo, estando en la rama correspondiente puede ejecutar `git pull origin main` (si la rama de destino se llama `main`). `git pull` obtiene los cambios remotos y los integra en la rama local.

## 6. Sync Fork

**Planteamiento:** Mi Fork se creó varios días atrás y el repositorio original recibió nuevos commits. Indicar qué herramienta usar, qué repositorio se actualiza y en qué se diferencia **Sync Fork** de `git pull`.

**Explicación:** Puedo usar la opción **Sync fork** de GitHub para incorporar al Fork los cambios recientes del repositorio original. La herramienta actualiza el repositorio remoto de mi Fork en GitHub; no actualiza directamente mi copia local. En cambio, `git pull` se ejecuta en el repositorio local: obtiene cambios de un remoto configurado (por ejemplo, mi Fork o el repositorio original, si está configurado como `upstream`) y los integra en la rama local actual. Por eso, después de sincronizar el Fork en GitHub, también debo hacer `git pull` desde el remoto de mi Fork para actualizar mi copia local.
