# 🚀 FTSApp - File Transfer Secure

**Sistema de transferencia de archivos seguro** con comunicación TLS/SSL entre cliente y servidor, interfaz web moderna con animaciones de estrellas.

## 📋 Descripción

FTSApp es una aplicación completa de transferencia de archivos que implementa:
- **Servidor TLS seguro** para almacenamiento de archivos
- **Servidor web HTTPS** con interfaz de usuario
- **Comunicación cifrada** extremo a extremo
- **Interfaz web moderna** con animaciones CSS

## 🛠️ Tecnologías Utilizadas

- **Node.js** - Runtime JavaScript
- **Express.js** - Framework web
- **TLS/SSL** - Comunicación segura
- **Multer** - Manejo de archivos multipart
- **HTML5/CSS3** - Interfaz de usuario
- **JavaScript Vanilla** - Lógica del frontend

## 📁 Estructura del Proyecto

```
FTSAPP_5/
├── src/
│   ├── secure-server.js     # Servidor TLS para archivos
│   ├── web-server.js        # Servidor web HTTPS
│   ├── tls-client.js        # Cliente TLS (módulo)
│   ├── certs/               # Certificados SSL/TLS
│   │   ├── server-cert.pem
│   │   ├── server-key.pem
│   │   └── server-csr.pem
│   ├── files/               # Archivos almacenados
│   └── uploads/             # Archivos temporales
├── public/                  # Interfaz web
│   ├── index.html          # Página principal
│   ├── style.css           # Estilos principales
│   ├── estrellas.css       # Animación de estrellas
│   └── main.js             # Lógica del frontend
├── package.json            # Dependencias del proyecto
└── README.md              # Este archivo
```

## ⚡ Instalación y Configuración

### 1. Clonar el repositorio
```bash
git clone <url-del-repositorio>
cd FTSAPP_5
```

### 2. Instalar dependencias
```bash
npm install
```

### 3. Verificar certificados
Asegúrate de que los certificados estén en `src/certs/`:
- `server-cert.pem` - Certificado del servidor
- `server-key.pem` - Clave privada
- `server-csr.pem` - Solicitud de certificado

## 🚀 Instrucciones de Ejecución

### Método 1: Ejecución Manual

#### Terminal 1 - Servidor TLS (Puerto 6000)
```bash
cd src
node secure-server.js
```
**Salida esperada:**
```
[SERVER] Directorio E:\Proyectos\FTSAPP_5\src\files creado.
[SERVER] Servidor TLS escuchando en puerto 6000
```

#### Terminal 2 - Servidor Web (Puerto 3000)
```bash
cd src
node web-server.js
```
**Salida esperada:**
```
🔐 UI web segura disponible en https://localhost:3000
```


## 🌐 Acceso a la Aplicación

1. **Abrir navegador** en: `https://localhost:3000`
2. **Aceptar certificado** (si aparece advertencia de seguridad)
3. **¡Listo!** La interfaz web estará disponible

## 📖 Ejemplos de Uso

### 1. 📤 Subir un Archivo

**Pasos:**
1. Hacer clic en "**Elegir archivo**"
2. Seleccionar archivo desde tu computadora
3. Hacer clic en "**Subir**"
4. El archivo aparecerá automáticamente en la lista

**Log del servidor esperado:**
```bash
# secure-server.js
[SERVER] Nueva conexión desde ::1
[SERVER] Comando recibido: PUT archivo.jpg
[SERVER][PUT] Preparado para recibir archivo: archivo.jpg
[SERVER][PUT] Archivo escrito correctamente

# web-server.js
[PUT] Archivo leído: ..., tamaño: 115567 bytes
[PUT] Recibido del servidor: READY: PUT
[PUT] Servidor listo, enviando archivo...
[PUT] Archivo y delimitador enviados, esperando confirmación...
[PUT] Recibido del servidor: OK: PUT complete
[PUT] Confirmación recibida, cerrando conexión...
[PUT] Subida exitosa, borrando archivo temporal
```

### 2. 📥 Descargar un Archivo

**Pasos:**
1. Localizar archivo en la tabla
2. Hacer clic en "**Descargar**"
3. El archivo se descargará automáticamente

### 3. ✏️ Renombrar un Archivo

**Pasos:**
1. Hacer clic en "**Renombrar**" junto al archivo
2. Escribir el nuevo nombre en el prompt
3. Confirmar - el archivo se renombrará instantáneamente

### 4. 🗑️ Eliminar un Archivo

**Pasos:**
1. Hacer clic en "**Eliminar**" junto al archivo
2. Confirmar la eliminación en el diálogo
3. El archivo se eliminará y desaparecerá de la lista

## 🧪 Pruebas Realizadas

### ✅ Pruebas de Funcionalidad

| Funcionalidad | Estado | Descripción |
|---------------|--------|-------------|
| **Subida de archivos** | ✅ Exitosa | Archivos de diferentes tamaños y tipos |
| **Descarga de archivos** | ✅ Exitosa | Descarga directa desde navegador |
| **Listado de archivos** | ✅ Exitosa | Actualización automática en tiempo real |
| **Renombrar archivos** | ✅ Exitosa | Cambio de nombre instantáneo |
| **Eliminar archivos** | ✅ Exitosa | Eliminación con confirmación |
| **Interfaz responsiva** | ✅ Exitosa | Funciona en diferentes tamaños de pantalla |
| **Animaciones CSS** | ✅ Exitosa | Lluvia de estrellas fluida |

### ✅ Pruebas de Seguridad

| Aspecto | Estado | Descripción |
|---------|--------|-------------|
| **Comunicación TLS** | ✅ Segura | Cifrado entre web-server y secure-server |
| **HTTPS Frontend** | ✅ Segura | Interfaz web servida por HTTPS |
| **Certificados SSL** | ✅ Válidos | Certificados autofirmados funcionando |
| **Validación archivos** | ✅ Implementada | Verificación de existencia y tamaño |

### ✅ Pruebas de Rendimiento

| Tipo de Archivo | Tamaño | Resultado | Tiempo Aprox. |
|-----------------|--------|-----------|---------------|
| **Imagen JPG** | 115 KB | ✅ Exitosa | < 1 segundo |
| **Imagen PNG** | 261 KB | ✅ Exitosa | < 2 segundos |
| **Documento PDF** | 1.2 MB | ✅ Exitosa | < 3 segundos |
| **Video MP4** | 15 MB | ✅ Exitosa | < 10 segundos |


### Problema: "No se puede conectar al servidor"
**Solución:**
1. Verificar que ambos servidores estén ejecutándose
2. Comprobar que no haya errores en las consolas
3. Reiniciar ambos servidores en orden: primero secure-server, luego web-server

### Problema: "Archivos no aparecen"
**Solución:**
1. Verificar que el directorio `src/files/` exista
2. Comprobar permisos de escritura
3. Revisar logs del servidor para errores

## 🎨 Características de la Interfaz

### 🌟 Animación de Estrellas
- **28 estrellas** distribuidas por toda la pantalla
- **Movimiento diagonal** con rotación de 315°
- **Velocidades variables** para efecto natural
- **Estelas luminosas** con gradiente
- **Responsive** - se adapta a cualquier tamaño de pantalla

### 💫 Diseño Moderno
- **Colores temáticos** con tonos azules y blancos
- **Efectos de hover** en botones
- **Tabla responsiva** para listado de archivos
- **Formularios intuitivos** para subida de archivos

## 📊 Arquitectura del Sistema

```
┌─────────────────┐    HTTPS     ┌──────────────────┐
│   Navegador     │ ◄──────────► │   web-server.js  │
│  (Frontend)     │              │   (Puerto 3000)  │
└─────────────────┘              └──────────────────┘
                                          │
                                          │ TLS
                                          ▼
                                 ┌──────────────────┐
                                 │ secure-server.js │
                                 │   (Puerto 6000)  │
                                 └──────────────────┘
                                          │
                                          ▼
                                 ┌──────────────────┐
                                 │   src/files/     │
                                 │ (Almacenamiento) │
                                 └──────────────────┘
```


## 📝 Notas Adicionales

- Los certificados incluidos son **autofirmados** para desarrollo
- Para producción, usar certificados de una CA reconocida
- El sistema está optimizado para archivos de hasta **50MB**
- Compatible con **todos los navegadores modernos**

¡Disfruta usando FTSApp! 🚀✨
