# INSTALLATION.md

## 1. Configuración de la máquina virtual (IsardVDI)

1. Accede al portal de IsardVDI y crea un nuevo escritorio:
   
   ```
   - Selecciona Ubuntu Desktop como plantilla.
   - Asigna un nombre descriptivo (ej. `Gestor de Archivos Web`).
   ```

   ![Creación de la máquina virtual](instalaciones/creacio_de_la_maquina_virtual.png)
   ![Escritorio nuevo](instalaciones/creacio_de_la_maquina_virtual_escriptori_nou.png)
   ![Configuración de recursos](instalaciones/configurar_una_maquina_virtual_per_allotjar_owncloud.png)

2. Configura recursos de la VM:
   - CPU: 8 vCPUs
   - Memoria: 32 GB RAM

3. Inicia la VM y conéctate vía VNC o SPICE.

---

## 2. Actualización del sistema e instalación de dependencias

1. Actualiza el índice de paquetes e instala actualizaciones:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
   
   ![Actualizar sistema](instalaciones/01_actualizar_sistema.png)

2. Instala Apache2:
   ```bash
   sudo apt install -y apache2
   ```

   ![Instalación de Apache2](instalaciones/02_instalacion_apache2.png)

3. Instala MySQL Server:
   ```bash
   sudo apt install -y mysql-server
   ```

   ![Instalación de MySQL](instalaciones/03_instalacion_mysql.png)

4. Instala PHP y librerías necesarias para OwnCloud:
   ```bash
   sudo apt install -y php libapache2-mod-php
   ```

   ![Librerías PHP](instalaciones/04_sudo_apt_install_php_libapache2_mod_php_php_mysql_librerias_php.png)

5. Reinicia Apache para aplicar cambios:
   ```bash
   sudo systemctl restart apache2
   ```

   ![Reiniciar Apache](instalaciones/05_sudo_systemctl_restart_apache2_reinicio_apache.png)

---

## 3. Configuración de la base de datos MySQL

1. Accede a la consola de MySQL:
   ```bash
   sudo mysql
   ```
   ![MySQL root login](instalaciones/06_mysql_u_root_p.png)

2. Crea la base de datos `bbdd`:
   ```sql
   CREATE DATABASE bbdd;
   ```
   ![Crear base de datos](instalaciones/07_create_database_owncloud.png)

3. Crea un usuario dedicado y asigna contraseña:
   ```sql
   CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
   ```
   ![Crear usuario](instalaciones/08_create_user_usuario_at_localhost_identified_by_password_creacion_usuario_base_de_datos.png)

4. Concede privilegios al nuevo usuario:
   ```sql
   GRANT ALL ON bbdd.* TO 'usuario'@'localhost';
   ```
   ![Conceder privilegios](instalaciones/09_grant_all_privileges_on_owncloud_to_usuario_at_localhost_conceder_privilegios.png)

5. Sal de MySQL:
   ```sql
   exit
   ```
   ![Salir de MySQL](instalaciones/10_exit_salir_de_mysql.png)

6. Verifica la conexión con el nuevo usuario:
   ```bash
   mysql -u usuario -p
   ```
   ![Verificar MySQL](instalaciones/11_mysql_u_usuario_p_owncloud_comprobacion_mysql.png)

---

## 4. Despliegue de ownCloud

1. Sitúate en el directorio raíz de Apache:
   ```bash
   cd /var/www/html
   ```
   ![Acceso a /var/www/html](instalaciones/12_cd_var_www_html_acceso_directori.png)

2. Descarga y descomprime ownCloud (asegúrate de usar la versión estable adecuada):
   ```bash
   wget https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip
   unzip owncloud-complete-20240724.zip
   rm owncloud-complete-20240724.zip
   mv owncloud/* .
   rmdir owncloud
   rm index.html
   ```

3. Ajusta propietarios y permisos:
   ```bash
   sudo chown -R www-data:www-data /var/www/html
   sudo find /var/www/html -type d -exec chmod 750 {} \;
   sudo find /var/www/html -type f -exec chmod 640 {} \;
   ```
   ![Permisos](instalaciones/19_permisos_www_data_html.png)

4. Preparar PPA para PHP ≤ 7.4 y cambiar versión si es necesario:
   ```bash
   sudo apt install software-properties-common -y
   sudo add-apt-repository ppa:ondrej/php
   sudo apt update
   sudo apt install php7.4 php7.4-{fpm,cli,gd,xml,mbstring,curl,mysql} -y
   sudo a2dismod php8.0 && sudo a2enmod php7.4
   sudo systemctl restart apache2
   ```

   ![PPA prerequisites](instalaciones/21_instalar_software_properties_common.png)
   ![Añadir repo PHP](instalaciones/22_add_apt_repository_ondrej_php.png)

5. Accede desde el navegador a `http://localhost/` y finaliza la instalación a través del asistente.

   ![Captura final de instalación](instalaciones/23_owncloud_instalado_captura_final_de_instalacion.png)

---

**¡Listo!** La VM y ownCloud están instalados y accesibles. Continúa con la configuración de usuarios y permisos en `CONFIGURATION.md`.
