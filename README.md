# YASSER-BELOUAFI-PT2

Este repositorio documenta la práctica de instalación y configuración de ownCloud en una máquina virtual desplegada con IsardVDI.

## Estructura del repositorio

- **INSTALLATION.md**: Guía detallada de creación de la VM, instalación de dependencias y despliegue de ownCloud.
- **CONFIGURATION.md**: Manual de configuración de usuarios, roles, permisos y gestión de archivos en ownCloud.
- **README.md**: Resumen del proyecto, enlaces a los manuales y retos encontrados.

## Descripción del proyecto

El objetivo de esta práctica es:
1. Configurar un entorno de virtualización (IsardVDI) para alojar ownCloud.
2. Instalar y poner en marcha ownCloud (Apache, PHP, MySQL).
3. Crear usuarios con distintos roles (administrador, editor, visualizador) y asignar permisos.
4. Probar funcionalidades básicas: subida de archivos, creación de carpetas, organización y compartición.

Para seguir el desarrollo paso a paso, consulta los manuales:

- [Manual de instalación](INSTALLATION.md)
- [Manual de configuración](CONFIGURATION.md)

---

## Retos encontrados

- **Compatibilidad de PHP**: La versión stable de ownCloud (20240724) requiere PHP ≤7.4, por lo que fue necesario bajar desde PHP 8.0.
- **Permisos en /var/www/html**: Ajustar ownership y permisos a `www-data` para evitar errores de escritura.
