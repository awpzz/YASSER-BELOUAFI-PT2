# CONFIGURATION.md

## Inicio

1. Crear cuenta en OwnCloud

   ![Crear cuenta](configuraciones/creamos_cuenta_primerisima_captura.png)

3. Inicia sesion

   ![Iniciar sesion](configuraciones/iniciamos_sesion_segunda_captura.png)

## 1. Subida de archivos

1. Haz clic en el icono “+” para desplegar opciones de subida.

   ![Subir archivos](configuraciones/1_icono_mas_subida_archivos.png)

2. Selecciona “Upload” y elige el archivo desde tu equipo.

   ![Opción de subida](configuraciones/2_opcion_subida_archivos.png)

3. Verifica que el fichero aparece en la lista.

   ![Archivo subido correctamente](configuraciones/4_archivo_subido_correctamente.png)

---

## 2. Creación de carpetas

1. Pulsa el icono “+” y selecciona “New folder”.

   ![Crear carpeta](configuraciones/5_icono_mas_crear_carpeta.png)

2. Introduce el nombre deseado.

   ![Nombrar carpeta](configuraciones/6_crear_y_nombrar_carpeta.png)

3. Comprueba que la carpeta se ha creado.

   ![Carpeta creada](configuraciones/8_carpeta_creada_correctamente.png)

---

## 3. Compartir contenido

1. Selecciona el recurso (archivo o carpeta) que quieras compartir.

   ![Seleccionar carpeta para compartir](configuraciones/9_seleccionar_carpeta_para_compartir.png)

2. Elige compartir con grupos o mediante enlace público:
   - Compartir con grupos:

     ![Compartir con grupos](configuraciones/10_opcion_compartir_con_grupos.png)

   - Compartir con enlace público:

     ![Compartir con link público](configuraciones/11_opcion_compartir_con_link_publico.png)

---

## 4. Creación de usuarios

1. Haz clic en tu avatar (esquina superior derecha) y entra en “Users”.

   ![Acceder a usuarios](configuraciones/12_acceso_configuracion_usuarios.png)
   ![Pestaña Users](configuraciones/13_pestana_users_panel_config.png)

2. Rellena el formulario y pulsa “Create user”.

   ![Formulario creación usuario](configuraciones/14_formulario_crear_usuario.png)
   ![Usuarios creados](configuraciones/15_usuarios_creados_correctamente.png)

---

## 5. Asignación de roles y permisos

### 5.1 Crear roles (grupos)

1. Ve a “Groups”.

   ![Acceder a grupos](configuraciones/16_acceder_a_grupos_para_roles.png)

2. Añade un nuevo grupo como rol (ej. ‘editor’, ‘visualizador’).

   ![Crear rol/grupo](configuraciones/17_crear_nombre_de_rol_grupo.png)

3. Asigna roles a los usuarios.

   ![Asignar rol a usuario](configuraciones/19_asignar_rol_a_usuario.png)

### 5.2 Configurar permisos por rol

1. Selecciona el archivo o carpeta deseada y abre el panel de “Sharing”.

   ![Acceder a sharing](configuraciones/20_acceder_archivo_para_permisos.png)
   ![Ir a Sharing](configuraciones/21_ir_a_sharing_archivo.png)

2. En “Users and groups” añade el rol.

   ![Users and groups](configuraciones/22_entrar_users_and_groups.png)
   ![Añadir rol](configuraciones/23_anadir_rol_a_sharing.png)

3. Haz clic en la rueda de configuración y ajusta permisos.

   ![Opciones permisos](configuraciones/24_abrir_opciones_permisos.png)
   ![Configurar permisos por rol](configuraciones/25_configurar_permisos_por_rol.png)

---

## 6. Organización de archivos y carpetas

### 6.1 Mover archivos

1. Selecciona el archivo y arrástralo a la carpeta destino.

   ![Seleccionar para mover](configuraciones/26_seleccionar_archivo_para_mover.png)
   ![Archivo movido](configuraciones/27_archivo_movido_a_carpeta.png)

### 6.2 Favoritos

1. Pasa el ratón sobre el recurso y haz clic en la estrella.

   ![Seleccionar favorito](configuraciones/28_seleccionar_archivo_para_favorito.png)
   ![Ver en favoritos](configuraciones/30_visualizar_en_favoritos.png)

### 6.3 Renombrar para ordenar

1. Pulsa los tres puntos junto al recurso y selecciona “Rename”.

   ![Opción rename](configuraciones/33_opcion_rename.png)
   ![Renombrar recurso](configuraciones/34_renombrar_archivo_para_orden.png)

---

## 7. Políticas de seguridad

1. En “Preferences” (avatar > Preferences) accede a “Sharing”.

   ![Preferencias usuario](configuraciones/35_acceder_preferencias_usuario.png)
   ![Ir a Preferences](configuraciones/36_ir_a_preferencias.png)
   ![Pref. Sharing](configuraciones/37_preferencias_sharing.png)

2. Ajusta políticas: caducidad de enlaces, restricción de dominios, aprobación de compartidos.

   ![Configuración políticas](configuraciones/38_configuracion_politicas_sharing.png)

---

## 8. Acceso desde otra máquina

1. Obtén la IP local de la VM:

   ![Comprobar IP local](configuraciones/39_comprobar_ip_local.png)

2. Verifica que Apache2 está activo:

   ![Reiniciar Apache](configuraciones/3_reiniciar_apache2.png)

3. Edita `config.php` y añade la IP en `trusted_domains`:

   ![Trusted Domains](configuraciones/2_config_trusted_domains_actualizado.png)

5. Accede desde otro equipo a `https://<IP_LOCAL>`.

---

**¡Configuración completada!** Ahora ownCloud está listo para uso colaborativo con usuarios, roles y políticas ajustadas.
