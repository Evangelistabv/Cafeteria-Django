# Cafetería — Proyecto de aprendizaje con Django

Aplicación web desarrollada con Python y Django cuya presentación visual final está orientada a una **cafetería**. Reúne un catálogo de productos, un carrito de compras, un blog, una sección de servicios y un formulario de contacto.

**[Ver la cafetería en Render](https://primera-pagina-d8so.onrender.com/)**

Este proyecto forma parte de mi aprendizaje de desarrollo web. Lo construí desde cero siguiendo cursos de YouTube como guía y poniendo en práctica la organización de aplicaciones, el manejo de datos y la lógica del servidor con Django.

## Desarrollo y uso de inteligencia artificial

Implementé personalmente la lógica del proyecto desde cero durante el proceso de aprendizaje: modelos, vistas, rutas, formularios y comportamiento del backend, apoyándome en los cursos y en las herramientas del framework.

Posteriormente utilicé inteligencia artificial como apoyo para modificar el frontend y adaptar su presentación visual a una cafetería. Esa fue la apariencia elegida para la versión desplegada en Render. La asistencia se centró en la interfaz; el proyecto mantiene la lógica del backend que desarrollé durante el aprendizaje y su funcionamiento dinámico con Django.

## Funcionalidades

- **Catálogo de productos:** consulta de productos con nombre, precio e imagen y categorías asociadas en el modelo de datos.
- **Carrito de compras:** almacenamiento en la sesión del usuario; permite agregar productos, reducir cantidades, eliminar artículos y vaciar el carrito.
- **Blog:** listado de publicaciones y consulta por categoría.
- **Servicios:** presentación de los servicios registrados.
- **Contacto:** formulario validado con Django y envío de mensajes mediante correo electrónico, sujeto a la configuración SMTP.
- **Usuarios:** registro, inicio y cierre de sesión mediante el sistema de autenticación de Django.
- **Administración:** ruta del panel de Django habilitable mediante una variable de entorno.

El alcance documentado es una aplicación de aprendizaje con catálogo y carrito; no se presenta como una tienda con pagos y pedidos completos.

## Tecnologías

- Python y Django.
- SQLite como base de datos configurada.
- Plantillas de Django, HTML y CSS para la interfaz.
- Django Crispy Forms y Bootstrap 4 para formularios.
- Integraciones de Django CMS y CKEditor incluidas en la configuración.
- WhiteNoise para archivos estáticos y Gunicorn incluido entre las dependencias.

## Estructura

```text
MiTienda/        Configuración general, rutas y puntos de entrada del proyecto
MiTiendaApp/     Página principal, registro y autenticación
TiendaApp/       Productos, categorías y carrito basado en sesiones
BlogApp/        Publicaciones y categorías del blog
ServiciosApp/   Modelos y vistas de servicios
ContactoApp/    Formulario y envío de correos
media/          Archivos multimedia
manage.py       Comandos de administración de Django
requirements.txt
```

## Ejecución local

Necesitas Git, Python y pip. Las dependencias del repositorio no fijan versiones; los siguientes pasos describen el flujo de instalación, pero la compatibilidad de una instalación limpia debe comprobarse en tu entorno.

### 1. Clonar el repositorio

```bash
git clone https://github.com/Evangelistabv/primera-p-gina.git
cd primera-p-gina
```

### 2. Crear y activar un entorno virtual

```bash
python -m venv .venv
```

Linux o macOS:

```bash
source .venv/bin/activate
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Instalar dependencias y comprobar la configuración

```bash
python -m pip install -r requirements.txt
python manage.py check
```

La configuración incluye Django CMS, Treebeard y campos de imagen. Si aparecen errores de dependencias, revisa la correspondencia entre los paquetes instalados y `INSTALLED_APPS`, así como la disponibilidad de Pillow. El listado actual de dependencias no constituye un entorno con versiones reproducibles.

### 4. Preparar la base de datos e iniciar el servidor

```bash
python manage.py migrate
python manage.py runserver
```

Abre [la aplicación local](http://127.0.0.1:8000/).

### Panel de administración opcional

Primero crea un usuario administrador:

```bash
python manage.py createsuperuser
```

La ruta administrativa solo se incorpora cuando `ENABLE_ADMIN` tiene el valor `true`. En Linux o macOS:

```bash
ENABLE_ADMIN=true python manage.py runserver
```

En Windows PowerShell:

```powershell
$env:ENABLE_ADMIN="true"
python manage.py runserver
```

Después abre [el panel de administración](http://127.0.0.1:8000/admin/).

### Correo de contacto

El formulario utiliza un servidor SMTP. Antes de probar el envío, revisa `EMAIL_HOST`, `EMAIL_PORT`, `EMAIL_USE_TLS` y `EMAIL_HOST_USER` en `MiTienda/settings.py`. Configura `EMAIL_HOST_PASSWORD` y, si corresponde, `DEFAULT_FROM_EMAIL` en el entorno. El destinatario está definido en la vista de contacto y debe ajustarse para otra instalación.

## Aprendizajes

- Separación de responsabilidades en aplicaciones de Django.
- Modelado de datos y relaciones con el ORM.
- Conexión entre rutas, vistas y plantillas.
- Validación de formularios y autenticación de usuarios.
- Persistencia de un carrito mediante sesiones.
- Integración de archivos multimedia y correo electrónico.
- Mejora de la presentación del frontend con asistencia de inteligencia artificial.

## Despliegue

Desplegué el proyecto en **Render** como parte del proceso de aprendizaje, llevando la aplicación desde el entorno local a un servicio de alojamiento web. La versión publicada presenta el proyecto visualmente como una cafetería.

**[Abrir la aplicación desplegada](https://primera-pagina-d8so.onrender.com/)**

## Estado del proyecto

Proyecto educativo y de portafolio. La configuración revisada mantiene `DEBUG=True` y permite todos los hosts, por lo que requiere ajustes antes de un despliegue de producción. La instalación y el envío de correo no se han validado como parte de esta documentación.

## Autor

**Daniel Evangelista** — [Evangelistabv en GitHub](https://github.com/Evangelistabv)

Desarrollado como práctica personal a partir de cursos de Django en YouTube, con asistencia de inteligencia artificial en la posterior renovación visual del frontend.
