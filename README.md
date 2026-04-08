# HMBRAKE-ECOMMERCE
HMBRAKE es una plataforma de comercio electrónico desarrollada en PHP y MySQL, orientada a la venta de repuestos de frenos para vehículos. El sistema permite gestionar productos, simular compras y administrar la tienda mediante un panel administrativo.
🎯 Objetivo

Desarrollar una solución web que permita:

Visualizar productos
Gestionar un carrito de compras
Administrar productos (CRUD)
Simular el proceso de compra
Controlar acceso administrativo
🧠 Arquitectura del Sistema

El sistema está basado en una arquitectura cliente-servidor:

Frontend: HTML, CSS, JavaScript, Bootstrap
Backend: PHP
Base de datos: MySQL
🛠️ Tecnologías Utilizadas
PHP 7+
MySQL / MariaDB
HTML5 / CSS3
Bootstrap 4
JavaScript
XAMPP (entorno local)
📂 Estructura del Proyecto

/admin → Panel administrativo
/incluir → Conexión y componentes reutilizables
/recursos → Imágenes
index.php → Página principal
carrito.php → Carrito de compras
pago.php → Simulación de pago

⚙️ Requisitos
Servidor web (Apache)
PHP 7 o superior
MySQL o MariaDB
Navegador web moderno
🚀 Instalación Paso a Paso
1. Clonar el repositorio
git clone https://github.com/dairmona/hmbrake-ecommerce.git
2. Ubicar en servidor local

Copiar la carpeta en:

C:\xampp\htdocs\
3. Iniciar servicios

Abrir XAMPP y activar:

Apache
MySQL
4. Crear base de datos

Ingresar a:

http://localhost/phpmyadmin

Ejecutar:

CREATE DATABASE hmbrake-ecommerce;
5. Crear tablas
CREATE TABLE productos (
    id_producto INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(255),
    descripcion TEXT,
    precio DECIMAL(10,2),
    imagen VARCHAR(255),
    stock INT
);

CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50),
    password VARCHAR(255)
);
6. Crear usuario administrador

Generar contraseña segura:

<?php echo password_hash("12345", PASSWORD_DEFAULT); ?>

Insertar en la base de datos:

INSERT INTO usuarios (usuario, password)
VALUES ('admin', 'HASH_GENERADO');
7. Configurar conexión

Editar archivo:

/incluir/conexion.php
$host = "localhost";
$usuario = "root";
$password = "";
$base_de_datos = "hmbrake-ecommerce";
8. Ejecutar aplicación

Abrir en navegador:

http://localhost/tienda-main/
9. Acceso al panel administrativo
http://localhost/tienda-main/admin/inicio_sesion.php

Credenciales:

Usuario: admin
Contraseña: 12345
🔐 Seguridad Implementada
Encriptación de contraseñas con password_hash
Validación de formularios
Control de acceso al panel administrativo
☁️ Despliegue en AWS (Resumen)
Crear instancia EC2
Instalar Apache, PHP y MySQL
Subir proyecto a /var/www/html
Configurar base de datos
Acceder mediante IP pública
📊 Funcionalidades
Catálogo de productos
Carrito de compras
CRUD de productos
Login administrativo
Simulación de pago
