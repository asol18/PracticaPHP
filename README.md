# Tienda PHP - Mini 
Sistema de inventario simple desarrollado con PHP, MySQL y XAMPP que permite gestionar productos: agregar, listar y marcar como adquiridos.
## Requisitos Previos
Antes de comenzar, tener instalado:
- **XAMPP** (versión 8.0 o superior)
  - Apache 2.4.x
  - MySQL 5.7.x o superior
  - PHP 8.0 o superior
- **Navegador web** moderno (Chrome, Firefox, Edge.)
- **Git** (opcional, para clonar el repositorio)
### Sistemas Operativos Compatibles
- Windows 10/11
- macOS
- Linux (Ubuntu, Debian, Fedora, etc.)

##  Instalación
### Paso 1: Instalar XAMPP
1. Descarga XAMPP desde [https://www.apachefriends.org](https://www.apachefriends.org)
2. Ejecuta el instalador y sigue las instrucciones
3. Instala en la ruta por defecto: `C:\xampp\` (Windows) 
### Paso 2: Iniciar Servicios
1. Abre el **Panel de Control de XAMPP**
2. Inicia los módulos:
   -  **Apache** (servidor web)
   -  **MySQL** (base de datos)
### Paso 3: Crear la Base de Datos
1. Abre tu navegador y accede a **phpMyAdmin**: `http://localhost/phpmyadmin`
2. Haz clic en la pestaña **SQL**
3. Copia y pega el siguiente script:
```sql
CREATE DATABASE tienda CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

USE tienda;

CREATE TABLE productos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(120) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    adquirido TINYINT(1) NOT NULL DEFAULT 0,
    creado_en TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
4. Hacer clic en **Continuar** para ejecutar el script
### Paso 4: Instalar el Proyecto
#### Opción A: Clonar desde GitHub
```bash
cd C:\xampp\htdocs
git clone https://github.com/USUARIO/tienda-php-xampp.git tienda
```
#### Opción B: Descarga Manual
1. Descarga el proyecto como ZIP desde GitHub
2. Extrae el contenido en `C:\xampp\htdocs\tienda`
3. Asegúrate de que el archivo `index.php` esté directamente en la carpeta `tienda`
### Paso 5: Verificar la Configuración
Abre el archivo `index.php` y verifica que las credenciales de la base de datos sean correctas:
```php
$host = "127.0.0.1";  // Host de la base de datos
$user = "root";        // Usuario (por defecto en XAMPP)
$pass = "";            // Contraseña (vacía por defecto en XAMPP)
$db = "tienda";        // Nombre de la base de datos
```
##  Uso
### Acceder a la Aplicación
1. Asegurase de que Apache y MySQL estén **activos** en XAMPP
2. Abrir el navegador web
3. Navega a: `http://localhost:3000/index.php`

### Funcionalidades Principales
#### Agregar Productos
1. En el formulario superior, completa los campos:
   - **Nombre**: Nombre descriptivo del producto
   - **Precio**: Valor numérico (acepta decimales, ej: 15.99)
2. Haz clic en el botón **Agregar**
3. El producto aparecerá en la tabla inferior
#### Visualizar Inventario
- La tabla muestra todos los productos ordenados por ID descendente (más recientes primero)
- Columnas disponibles:
  - **ID**: Identificador único del producto
  - **Nombre**: Nombre del producto
  - **Precio**: Precio formateado con 2 decimales
  - **Adquirido**: Estado (Sí/No)
  - **Acción**: Botón para cambiar el estado
####  Marcar como Adquirido/No Adquirido
1. Haz clic en el botón **Toggle** de cualquier producto
2. El estado cambiará automáticamente:
   - **No** → **Sí** (en verde)
   - **Sí** → **No**
##  Autor
**Allyson Sequeira Solis**
- GitHub: [asol18]
- Institución:Universidad Técnica Nacional
