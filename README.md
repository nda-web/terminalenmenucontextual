![logo](https://i3.wp.com/raw.githubusercontent.com/nda-web/terminalenmenucontextual/main/terminal.png)

# Menú Contextual: Abrir Terminal Aquí

Este script de PowerShell agrega dos opciones al menú contextual de Windows cuando haces clic derecho en un área en blanco dentro del Explorador de archivos. Las opciones son:

1. **Abrir terminal aquí**: Abre el símbolo del sistema (`cmd.exe`) en la carpeta actual.
2. **Abrir terminal aquí como administrador**: Abre el símbolo del sistema (`cmd.exe`) en la carpeta actual con permisos de administrador.

Estas opciones facilitan el acceso rápido a la terminal directamente desde cualquier directorio en el Explorador de archivos.

## Requisitos

- Windows 10 o superior
- Permisos de administrador para realizar cambios en el Registro de Windows

## Instrucciones de Uso

### Paso 1: Descargar el Script

1. Descarga el archivo `menu.ps1` de este repositorio.

### Paso 2: Ejecutar el Script

1. **Abre PowerShell como administrador**:
   - Haz clic derecho en el botón de Inicio y selecciona **Windows PowerShell (Administrador)**.
   
2. **Ejecuta el script**:
   - Navega hasta el directorio donde guardaste `menu.ps1`.
   - Ejecuta el siguiente comando para agregar las opciones al menú contextual:

     ```powershell
     .\menu.ps1
     ```

3. **Verifica las nuevas opciones**:
   - Abre el Explorador de archivos, navega a cualquier carpeta y haz clic derecho en un área en blanco dentro de la carpeta.
   - Deberías ver las opciones **Abrir terminal aquí** y **Abrir terminal aquí como administrador** en el menú contextual.

## Desinstalación

Si deseas eliminar estas opciones del menú contextual, puedes ejecutar el siguiente script de PowerShell para eliminar las claves de registro agregadas:

```powershell
# Eliminar las entradas del menú contextual
Remove-Item -Path "Registry::HKEY_CLASSES_ROOT\Directory\Background\shell\AbrirTerminalAqui" -Force
Remove-Item -Path "Registry::HKEY_CLASSES_ROOT\Directory\Background\shell\AbrirTerminalAquiAdmin" -Force

Write-Host "Entradas del menú contextual eliminadas exitosamente."
```

## Notas

- **Compatibilidad**: Este script está diseñado para sistemas Windows de 64 bits y se ha probado en Windows 10.
- **Codificación**: Guarda `menu.ps1` en formato UTF-8 para que los caracteres especiales se muestren correctamente en el menú.
  
---

Con este archivo `README.md`, los usuarios tendrán instrucciones claras sobre cómo usar el script, instalar las opciones de menú, y eliminar las entradas si es necesario.
