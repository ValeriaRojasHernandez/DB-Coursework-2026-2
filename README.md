# La Casita - Mini Súper Web con Laravel

## Descripción

**La Casita** es una aplicación web desarrollada con **Laravel** para la administración básica de un mini súper. Permite gestionar productos, categorías, clientes, empleados, proveedores, sucursales, promociones, inventario, ventas y preguntas frecuentes.

El proyecto cuenta con inicio de sesión, registro de clientes, control de sesiones, roles de usuario y vistas diferentes para administrador, empleado y cliente.

---

## Propósito

El propósito del proyecto es crear una plataforma web funcional para un mini súper, donde se pueda administrar la información principal del negocio y demostrar el uso de Laravel, MySQL, Blade, rutas protegidas, operaciones CRUD, autenticación y control de roles.

---

## Tecnologías utilizadas

- Laravel 12
- PHP 8.2 o superior
- MySQL / MariaDB
- Composer
- Blade Templates
- HTML
- CSS
- JavaScript
- XAMPP
- phpMyAdmin

---

## Funcionalidades principales

- Página pública del negocio.
- Registro e inicio de sesión.
- Panel de administrador.
- Panel de empleado.
- Panel de cliente.
- Gestión de productos.
- Gestión de categorías.
- Gestión de clientes.
- Gestión de empleados.
- Gestión de proveedores.
- Gestión de sucursales.
- Gestión de promociones.
- Gestión de preguntas frecuentes.
- Consulta de inventario.
- Consulta de ventas.
- Catálogo para clientes.
- Historial de compras.
- Protección de rutas por sesión y rol.

---

## Roles del sistema

| Rol | Descripción |
|---|---|
| Administrador | Tiene acceso completo a la administración del sistema. |
| Empleado | Puede consultar y gestionar información operativa. |
| Cliente | Puede consultar el catálogo y revisar sus compras. |

---

## Cuentas de prueba

| Rol | Correo | Contraseña |
|---|---|---|
| Administrador | admin@lacasita.com | 123456 |
| Empleado | empleado@lacasita.com | 123456 |
| Cliente | cliente@lacasita.com | 123456 |

---

## Capturas del proyecto

<details>
<summary>🖼️ Ver capturas de pantalla</summary>

### Página de inicio

![Página de inicio](capturas/Inicio.png)

---

### Catálogo de productos

![Catálogo de productos](capturas/CATALOGO.png)

---

### Promociones

![Promociones](capturas/Oferta.png)

---

### Sucursales

![Sucursales](capturas/Sucursales.png)

---

### Ayuda

![Ayuda](capturas/Ayuda.png)

---

### Panel de administrador

![Panel de administrador](capturas/ADMIN.png)

---

### Panel de empleado

![Panel de empleado](capturas/EMPLEADO.png)

---

### Panel de cliente

![Panel de cliente](capturas/CLIENTE.png)

</details>

---

## Estructura general

```txt
LaCasita/
├── app/
├── bootstrap/
├── config/
├── database/
│   ├── migrations/
│   └── seeders/
├── public/
│   └── assets/
├── resources/
│   └── views/
├── routes/
│   └── web.php
├── storage/
├── capturas/
├── artisan
├── composer.json
├── composer.lock
└── README.md
```

---

## Instalación local

### 1. Colocar el proyecto en XAMPP

El proyecto debe estar en:

```txt
C:\xampp\htdocs\LaCasita
```

Debe existir el archivo:

```txt
C:\xampp\htdocs\LaCasita\artisan
```

---

### 2. Encender servicios

Abrir XAMPP y encender:

```txt
Apache
MySQL
```

---

### 3. Crear base de datos

Entrar a phpMyAdmin:

```txt
http://localhost/phpmyadmin
```

Crear una base de datos llamada:

```txt
lacasita_laravel
```

---

### 4. Configurar `.env`

Abrir el archivo `.env` y colocar:

```env
APP_NAME="La Casita"
APP_ENV=local
APP_DEBUG=true
APP_URL=http://127.0.0.1:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=lacasita_laravel
DB_USERNAME=root
DB_PASSWORD=
```

---

### 5. Instalar dependencias

En CMD:

```bash
cd C:\xampp\htdocs\LaCasita
composer install
```

---

### 6. Generar llave

```bash
php artisan key:generate
```

---

### 7. Crear tablas y datos iniciales

```bash
php artisan migrate:fresh --seed
```

---

### 8. Limpiar caché

```bash
php artisan optimize:clear
```

---

### 9. Ejecutar el proyecto

```bash
php artisan serve
```

Abrir en el navegador:

```txt
http://127.0.0.1:8000
```

---

## Rutas principales

| Ruta | Descripción |
|---|---|
| `/` | Página principal |
| `/login` | Inicio de sesión |
| `/registro` | Registro de cliente |
| `/dashboard` | Panel según el rol |
| `/productos` | Gestión de productos |
| `/inventario` | Consulta de inventario |
| `/ventas` | Consulta de ventas |
| `/cliente/catalogo` | Catálogo para cliente |
| `/cliente/compras` | Compras del cliente |

---

## Seguridad implementada

El proyecto incluye:

- Autenticación de usuarios.
- Protección de rutas privadas.
- Control de acceso por rol.
- Contraseñas cifradas con hash.
- Protección CSRF en formularios.
- Validaciones del lado del servidor.
- Uso de Eloquent ORM para evitar consultas SQL inseguras.

---

## Despliegue en InfinityFree

Para subir el proyecto a InfinityFree se debe preparar localmente, ya que el hosting gratuito no permite ejecutar comandos como `composer install` o `php artisan`.

Pasos generales:

1. Preparar el proyecto en local.
2. Exportar la base de datos desde phpMyAdmin.
3. Crear una base de datos en InfinityFree.
4. Importar el archivo `.sql`.
5. Configurar el archivo `.env` con los datos de InfinityFree.
6. Subir el proyecto a `htdocs`.
7. Verificar que exista `vendor/autoload.php`.
8. Crear un archivo `.htaccess` en `htdocs`.

Contenido del `.htaccess` principal:

```apache
RewriteEngine On
RewriteRule ^(.*)$ public/$1 [L]
```

La estructura en el hosting debe quedar así:

```txt
htdocs/app
htdocs/bootstrap
htdocs/config
htdocs/database
htdocs/public
htdocs/resources
htdocs/routes
htdocs/storage
htdocs/vendor
htdocs/.env
htdocs/artisan
htdocs/composer.json
htdocs/composer.lock
htdocs/.htaccess
```

---

## Notas importantes

- No subir `.env` a GitHub.
- No subir `vendor` a GitHub.
- No subir `node_modules`.
- En producción usar `APP_DEBUG=false`.
- En InfinityFree, el proyecto debe entrar por la carpeta `public`.
- Para GitHub, conservar la carpeta `capturas` para que las imágenes del README se visualicen correctamente.

---

## Conclusión

**La Casita** es un proyecto web funcional desarrollado con Laravel y MySQL. Integra autenticación, roles, operaciones CRUD, vistas administrativas y paneles diferenciados para cada tipo de usuario. Además, puede ejecutarse localmente con XAMPP y documentarse correctamente en GitHub mediante capturas desplegables.
