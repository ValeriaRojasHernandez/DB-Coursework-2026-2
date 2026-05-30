# La Casita - Mini Súper Web con Laravel

## Descripción

**La Casita** es una aplicación web desarrollada con **Laravel** para administrar de forma básica un mini súper. Permite gestionar productos, clientes, empleados, proveedores, sucursales, promociones, inventario, ventas y preguntas frecuentes.

El proyecto incluye autenticación, registro de clientes, control de sesiones, roles de usuario y paneles diferentes para administrador, empleado y cliente.

---

## Tecnologías utilizadas

- Laravel 12
- PHP 8.2 o superior
- MySQL / MariaDB
- Composer
- Blade Templates
- HTML, CSS y JavaScript
- XAMPP
- phpMyAdmin

---

## Funcionalidades principales

- Página pública del negocio.
- Registro e inicio de sesión.
- Panel de administrador, empleado y cliente.
- Gestión de productos, categorías, clientes, empleados y proveedores.
- Gestión de sucursales, promociones y preguntas frecuentes.
- Consulta de inventario y ventas.
- Catálogo e historial de compras para clientes.
- Protección de rutas por sesión y rol.

---

## Roles del sistema

| Rol | Descripción |
|---|---|
| Administrador | Acceso completo a la administración del sistema. |
| Empleado | Acceso operativo a productos, inventario y ventas. |
| Cliente | Consulta catálogo y compras realizadas. |

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
├── public/
├── resources/
├── routes/
├── storage/
├── capturas/
├── artisan
├── composer.json
├── composer.lock
└── README.md
```

---

## Instalación local

1. Colocar el proyecto en:

```txt
C:\xampp\htdocs\LaCasita
```

2. Encender en XAMPP:

```txt
Apache
MySQL
```

3. Crear en phpMyAdmin una base de datos llamada:

```txt
lacasita_laravel
```

4. Configurar el archivo `.env`:

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

5. Ejecutar los comandos:

```bash
cd C:\xampp\htdocs\LaCasita
composer install
php artisan key:generate
php artisan migrate:fresh --seed
php artisan optimize:clear
php artisan serve
```

6. Abrir en el navegador:

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
| `/cliente/catalogo` | Catálogo del cliente |
| `/cliente/compras` | Compras del cliente |

---

## Seguridad implementada

- Autenticación de usuarios.
- Protección de rutas privadas.
- Control de acceso por rol.
- Contraseñas cifradas con hash.
- Protección CSRF en formularios.
- Validaciones del lado del servidor.
- Uso de Eloquent ORM.

---

## Notas importantes

- No subir `.env` a GitHub.
- No subir `vendor` ni `node_modules`.
- En producción usar `APP_DEBUG=false`.
- Conservar la carpeta `capturas` para que las imágenes del README se visualicen correctamente.

---

## Conclusión

**La Casita** es un proyecto web funcional desarrollado con Laravel y MySQL. Integra autenticación, roles, operaciones CRUD y paneles diferenciados para administrar un mini súper de manera sencilla
