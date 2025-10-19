---
space: "[[Servidores]]"
topic:
  - "[[XAMPP]]"
Tipo: Configuración
updated: 2025-10-18T19:59
created: 2025-10-08T09:46
---
## Gestión y Solución de Conflictos de Puertos

El conflicto de puertos es común, ya que aplicaciones como Skype, TeamViewer o VMware pueden estar usando los puertos 80 y 443, lo que provoca que Apache o MySQL no puedan arrancar.

### 2.1 Identificación de Puertos Ocupados

- Utilice la herramienta **Netstat** que se incluye en el Panel de Control de XAMPP para verificar qué puertos están siendo utilizados y por qué aplicaciones.

### 2.2 Cambio del Puerto de Apache (Puerto 80)

El puerto **80** es el puerto habitual para servidores web HTTP.

1. **Detener Apache:** Antes de modificar, detenga el servicio de Apache.
2. **Modificar `httpd.conf`:** Acceda al archivo de configuración de Apache (`C:\xampp\apache\conf\httpd.conf`) haciendo clic en **Config** en la fila de Apache.
3. **Cambiar `Listen`:** Busque la línea `Listen 80` y cámbiela a un puerto alternativo, como `Listen 8080`.
4. **Cambiar `ServerName`:** Busque la línea `ServerName localhost:80` y actualícela con el nuevo puerto: `ServerName localhost:8080`.
5. **Reiniciar Apache:** Guarde el archivo y reinicie Apache para aplicar los cambios.
6. **Acceso:** Para acceder a su sitio, deberá incluir el nuevo puerto en la dirección: `http://localhost:8080`.

### 2.3 Cambio del Puerto SSL de Apache (Puerto 443)

El puerto **443** es el puerto estándar para conexiones seguras HTTPS/SSL.

1. **Modificar `httpd-ssl.conf`:** Acceda al archivo de configuración SSL de Apache (`...\xampp\apache\conf\extra\httpd-ssl.conf`) haciendo clic en **Config**.
2. **Cambiar `Listen`:** Busque `Listen 443` y cámbielo a un puerto alternativo, como `Listen 4433` o `Listen 448`.
3. **Cambiar `VirtualHost`:** Busque la instancia `<VirtualHost _default_:443>` y cámbiela al nuevo puerto, por ejemplo, `<VirtualHost _default_:4433>`.
4. **Otras Referencias:** Busque y modifique todas las referencias restantes al puerto 443 dentro de ese archivo (incluyendo `ServerName www.example.com:443`).
5. **Reiniciar Apache:** Detenga y reinicie Apache para que los nuevos puertos SSL surtan efecto.

### 2.4 Cambio del Puerto de MySQL (Puerto 3306)

El puerto por defecto de MySQL es el **3306**.

1. **Detener MySQL:** Detenga el servicio de MySQL.
2. **Modificar `my.ini`:** Acceda al archivo de configuración de MySQL (`my.ini`) desde el botón **Config** en la fila de MySQL.
3. **Cambiar Puertos:** Debe cambiar el número de puerto (por ejemplo, a **3307** o **3310**) en dos lugares dentro de `my.ini`: en la sección `[client]` y en la sección `[mysqld]`.
4. **Actualizar phpMyAdmin:** Para que phpMyAdmin funcione con el nuevo puerto, es necesario modificar el archivo `config.inc.php` (accesible desde el **Config** de Apache). (_este paso no me cuadra_)
	- **Host Redireccionado:** En este archivo, busque la IP del servidor local (`127.0.0.1`) y añada el nuevo puerto (e.g., `127.0.0.1:3307`).
5. Actualizar `php.ini`: es el archivo de configuración global de PHP. Aunque el cambio de puerto principal de MySQL no se hace directamente aquí, algunas fuentes recomiendan modificarlo para **asegurar la comunicación de PHP con MySQL**
6. **Reiniciar:** Reinicie el servicio de MySQL. El nuevo puerto aparecerá en el Panel de Control.
