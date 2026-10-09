# Parte 3

## 1. Analiza

**Planteamiento:**


git status
git add README.md
git commit -m "Actualiza documentación"
git push


**Explicación:**

1. `git status` muestra el estado del repositorio local: la rama actual, los cambios sin preparar, los archivos preparados para el próximo commit y, cuando corresponde, si la rama está adelantada o atrasada respecto al remoto.
2. `git add README.md` prepara los cambios actuales de `README.md` para incluirlos en el próximo commit. No los guarda todavía en el historial ni los sube a GitHub.
3. `git commit -m "Actualiza documentación"` crea un commit local con los cambios preparados y les asigna el mensaje indicado. El commit registra los cambios en el historial local.
4. `git push` envía al repositorio remoto configurado los commits locales que todavía no se han publicado, actualizando la rama remota correspondiente.

## 2. Identifica qué falta

### Caso A

**Planteamiento:**


Modificar archivo
↓
git add .
↓
¿?
↓
git push


**Explicación:** Falta ejecutar `git commit -m "mensaje descriptivo"`. `git add .` prepara los cambios, pero para que `git push` pueda publicarlos primero deben registrarse en un commit. El commit guarda los cambios preparados en el historial local; después, `git push` puede enviarlo al remoto.

### Caso B

**Planteamiento:**


Repositorio GitHub
↓
¿?
↓
Repositorio local


**Explicación:** Si todavía no existe una copia local, se utiliza `git clone <URL-del-repositorio>`. `git clone` descarga el repositorio de GitHub, incluidos su historial y ramas, y crea una copia de trabajo local conectada al remoto.

### Caso C

**Planteamiento:**


Repositorio remoto actualizado
↓
¿?
↓
Repositorio local actualizado


**Explicación:** Se utiliza `git pull` desde el repositorio local y en la rama que se desea actualizar. `git pull` obtiene los commits nuevos del remoto configurado y los integra en la rama local. A diferencia de `git clone`, que crea una copia local inicial, `git pull` actualiza una copia local que ya existe.
