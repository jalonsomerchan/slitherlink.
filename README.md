# Slitherlink

Juego de lógica instalable, con 300 niveles y progreso guardado en el navegador.

## Ejecutar en local

```sh
python3 -m http.server 8000
```

Abre <http://localhost:8000>. Es necesario servir los archivos por HTTP; abrir `index.html` directamente no permite cargar correctamente los niveles ni instalar la PWA.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub y sube estos archivos a la rama `main`.
2. En el repositorio, abre **Settings → Pages** y selecciona **GitHub Actions** como origen de publicación.
3. El flujo incluido en `.github/workflows/deploy.yml` publica automáticamente cada cambio en `main`. También puedes ejecutarlo manualmente desde la pestaña Actions.
4. La URL aparecerá en la ejecución del flujo y en **Settings → Pages**. La aplicación funciona tanto en la raíz de un dominio como en la ruta de un repositorio.

El navegador ofrece la instalación cuando cumple sus requisitos. En iPhone y iPad, abre el juego en Safari y usa **Compartir → Añadir a pantalla de inicio**. Tras la primera visita y la instalación de los recursos, se puede jugar sin conexión. El progreso permanece en el navegador y dispositivo en el que se completa cada nivel.

Los niveles se definen en `levels.json`: cada entrada tiene un `id` único, `name`, `size` y una matriz cuadrada `clues`; usa `null` para las casillas sin pista. Añade los niveles al final para conservar el orden de desbloqueo y los identificadores existentes.
