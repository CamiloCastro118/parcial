# Markov Chains — Proyecto (index.html)

Este repositorio contiene una aplicación de una sola página (`index.html`) que permite:

- Editar una matriz de transición P (6x6) y un vector inicial v0.
- Calcular potencias de P, forma canónica, matriz fundamental N, tiempos y probabilidades de absorción.
- Ejecutar simulaciones Monte Carlo (trayectorias) y visualizar resultados con Chart.js.
- Exportar resultados a Excel (.xlsx) incluyendo hojas: `Instrucciones`, `Cadena`, `Calculos`, `Simulacion`, `Graficas`, `Diagrama`, `ResumenSim`, `PivotTiempoEstado`.
- Generar un informe PDF con los gráficos y resultados resumidos.

Notas para desplegar en GitHub Pages
-----------------------------------
1. GitHub Pages funciona con sitios estáticos. Este proyecto es completamente cliente-side (HTML/CSS/JS), por lo que se puede publicar tal cual en Pages.

2. Asegúrese de incluir todos los archivos que desee servir (por ejemplo `logo.png`, `diagram.png` si los utiliza). Referencias relativas (ej. `logo.png`) funcionarán correctamente.

3. Recomendación de publicación (modo manual):

  a) Cree el repositorio en GitHub (ej. `your-user/markov-project`).
  b) Desde PowerShell, en la carpeta `parcial` ejecute:

```powershell
# inicializar repo local
git init
git add .
git commit -m "Initial commit - Markov single-file app"
# crear remote (reemplazar URL por la de su repo)
git remote add origin https://github.com/<TU_USUARIO>/<TU_REPO>.git
# subir a main
git branch -M main
git push -u origin main
```

  c) En GitHub, vaya a *Settings -> Pages* y seleccione la rama `main` y la carpeta `/ (root)`. Guarde. Su sitio estará disponible en `https://<TU_USUARIO>.github.io/<TU_REPO>/` en unos minutos.

4. Alternativa: usar la rama `gh-pages` y una acción de GitHub Actions para publicar automáticamente. Puedo añadir un `workflow` si lo desea.

5. Recomendaciones y limitaciones

- ExcelJS y las funciones que usan `fetch('logo.png')` o `html2canvas` funcionarán correctamente en GitHub Pages ya que los archivos se sirven por HTTP/HTTPS; no funcionarán si abre `index.html` por `file://` y hay problemas con fetch o canvas.
- Si los usuarios desean exportar una imagen del encabezado o diagrama, deben primero subir el diagrama usando el control de la UI o asegurarse de que `logo.png` está presente en el repo.
- Evite subir datasets extremadamente grandes (muchas trayectorias muy largas) porque el archivo `.xlsx` puede crecer mucho; la UI ya limita las trayectorias exportadas por defecto.

6. Archivos agregados aquí para facilitar Pages

- `.nojekyll` : evita que GitHub Pages procese el sitio con Jekyll (útil si hay rutas que comienzan con `_`).

¿Qué hago ahora?
-----------------
- Puedo crear automáticamente la rama `gh-pages` y preparar un `GitHub Actions` workflow para publicar automáticamente después de push.
- Puedo añadir un `README` más detallado (instrucciones de prueba, ejemplos de matrices) o un `LICENSE`.

Indique si quiere que genere también el `workflow` de GitHub Actions para desplegar automáticamente a `gh-pages` o prefieres publicar desde `main` (root) manualmente.