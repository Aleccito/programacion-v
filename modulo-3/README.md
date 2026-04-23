<div align="center">

# ☁️ AWS S3 + IAM  
## 📦 Módulo #3 - Almacenamiento en la Nube

<img src="https://img.shields.io/badge/AWS-S3-orange?style=for-the-badge&logo=amazonaws" />
<img src="https://img.shields.io/badge/IAM-Security-blue?style=for-the-badge&logo=amazonaws" />
<img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge" />

---

### 🚀 Implementación de bucket tipo objeto con versionado y acceso seguro

</div>

---

# 📚 Descripción

En esta práctica se configuró un sistema de almacenamiento en la nube utilizando **Amazon Web Services (AWS)**.

Se realizaron las siguientes tareas:

✅ Creación de bucket en Amazon S3  
✅ Activación del versionado  
✅ Carga de archivo de prueba  
✅ Creación de usuario IAM  
✅ Permisos de solo lectura para un bucket específico

---

# 🗂️ Arquitectura del Proyecto

```text
                ┌─────────────────────┐
                │     Usuario AWS     │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   AWS Management    │
                │      Console        │
                └──────────┬──────────┘
                           │
         ┌─────────────────┴─────────────────┐
         ▼                                   ▼
┌──────────────────┐               ┌──────────────────┐
│   Amazon S3      │               │      AWS IAM     │
│  Bucket Storage  │               │ User Permissions │
└──────────────────┘               └──────────────────┘
         │                                   │
         ▼                                   ▼
 File Uploads                        Read-Only Access
 Versioning Enabled                 Specific Bucket
🎯 Objetivos
Objetivo	Estado
Crear bucket S3	✅
Activar versionado	✅
Subir archivo	✅
Crear usuario IAM	✅
Asignar permisos lectura	✅
🧰 Servicios Utilizados
Servicio	Uso
Amazon S3	Almacenamiento de objetos
AWS IAM	Gestión de usuarios y permisos
⚙️ Paso 1 - Crear Bucket en S3
📍 Ruta:
AWS Console > S3 > Create Bucket
Configuración:
Parámetro	Valor
Tipo	Uso general
Región	us-east-2
Acceso público	Bloqueado
ACL	Deshabilitadas
Ejemplo de nombre:
bucket-alec-modulo3

📸 Captura sugerida: Pantalla de creación del bucket.

🔄 Paso 2 - Activar Versionado
📍 Ruta:
Bucket > Properties > Bucket Versioning
Acción:

✅ Enable Versioning

Beneficios:
Conserva versiones antiguas
Recuperación de archivos
Protección ante cambios accidentales

📸 Captura sugerida: Versioning Enabled.

📤 Paso 3 - Subir Archivo de Prueba
📍 Ruta:
Bucket > Upload
Acción:
Seleccionar archivo local
Subir archivo
Verificar en lista

📸 Captura sugerida: Archivo cargado dentro del bucket.

👤 Paso 4 - Crear Usuario IAM
📍 Ruta:
AWS Console > IAM > Users > Create User
Nombre usado:
alecuser

📸 Captura sugerida: Pantalla creación del usuario.

🔐 Paso 5 - Política Solo Lectura para Bucket
Política JSON aplicada
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "ListBucket",
      "Effect": "Allow",
      "Action": ["s3:ListBucket"],
      "Resource": "arn:aws:s3:::bucket-alec-modulo3"
    },
    {
      "Sid": "ReadObjects",
      "Effect": "Allow",
      "Action": ["s3:GetObject"],
      "Resource": "arn:aws:s3:::bucket-alec-modulo3/*"
    }
  ]
}

📸 Captura sugerida: Política creada.

🔗 Paso 6 - Asignar Política al Usuario
Resultado Final
Usuario: alecuser
Permiso: SoloLecturaBucket

📸 Captura sugerida: Usuario mostrando permisos.

📁 Evidencias Recomendadas
capturas/
├── 01-crear-bucket.png
├── 02-versionado.png
├── 03-bucket-creado.png
├── 04-subir-archivo.png
├── 05-archivo-listado.png
├── 06-crear-usuario.png
├── 07-politica-json.png
├── 08-permisos-finales.png
🛡️ Seguridad Implementada
Configuración	Estado
Acceso público bloqueado	✅
ACL deshabilitadas	✅
Usuario restringido	✅
Solo lectura	✅
🧠 Aprendizajes Obtenidos

✅ Gestión de almacenamiento cloud
✅ Seguridad con IAM
✅ Principio de mínimo privilegio
✅ Administración de buckets S3
✅ Control de versiones

✅ Resultado Final
Bucket funcionando ✔
Archivo cargado ✔
Versionado activo ✔
Usuario IAM creado ✔
Solo lectura aplicada ✔
🏁 Conclusión

Se implementó exitosamente un entorno de almacenamiento en la nube mediante Amazon S3, aplicando controles de seguridad con IAM y buenas prácticas como el versionado y el acceso restringido por políticas.

Esto fortalece conocimientos fundamentales en Cloud Computing y AWS.

<div align="center">
👨‍💻 Autor

Alec
Programación V
Módulo #3

⭐ Proyecto académico usando AWS

</div> ```
