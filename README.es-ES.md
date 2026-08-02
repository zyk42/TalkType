<div align="center">

# Voke

**Voke · Asistente de transcripción de voz con IA**
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-green)
[中文](README.md) | [English](README_EN.md)
</div>

<br/>

> Voke es una aplicación multiplataforma desarrollada con Electron, compatible con Windows, macOS y Linux. Al combinar ASR e LLM, no solo puede "transcribir", sino también "comprender", "mejorar" y "hacer preguntas", produciendo así texto de alta calidad de forma eficiente.

---

## ✨ Características principales

- **Soporte multiplataforma**: Construida con el framework Electron, compatible con Windows, macOS y Linux.
- **Configuración sencilla**: **Solo necesita ingresar la API de ASR y la API de IA para comenzar a usarla**. Es compatible con proveedores de servicios que cumplen con la interfaz de OpenAI (por defecto, Alibaba Cloud DashScope).
- **Amigable para desarrolladores**: Ofrece un modo de desarrollo completo, fácil de extender y desarrollar posteriormente.
- **Privacidad y seguridad**: La configuración y los datos del historial se almacenan localmente; las API se comunican directamente con el proveedor de servicios.

## 🎬 Demostración de funciones

### ✨ Modo de mejora
**Active la mejora con IA**, **mantenga presionada la tecla Right Alt** y hable; al soltarla, se optimizará la expresión para que el texto fluya mejor.

<div align="center">
    <img src="figures/zhuanlu.gif" alt="Modo de mejora" width="400" />
</div>

### ⌨️ Modo de instrucciones
**Seleccione el texto**, **mantenga presionada la tecla Right Alt** y dicte la instrucción; al soltarla, se ajustará con precisión el contenido del texto según sus necesidades personalizadas.

<div align="center">
    <img src="figures/zhiling.gif" alt="Modo de instrucciones" width="400" />
</div>

### 💡 Modo de preguntas
**Mantenga presionada la tecla Right Ctrl** y formule su pregunta; al soltarla, recibirá la respuesta de la IA.

<div align="center">
    <img src="figures/tiwen.gif" alt="Modo de preguntas" width="400" />
</div>

### 📸 Vista de la interfaz

<div align="center">
    <table>
        <tr>
            <td align="center" colspan="2">
                <p><b>Interfaz principal</b></p>
                <img src="figures/shouye.png" width="100%" />
            </td>
        </tr>
        <tr>
            <td align="center" width="50%">
                <p><b>Estadísticas de datos</b></p>
                <img src="figures/tongji.png" width="100%" />
            </td>
            <td align="center" width="50%">
                <p><b>Historial</b></p>
                <img src="figures/lishi.png" width="100%" />
            </td>
        </tr>
        <tr>
            <td align="center" width="50%">
                <p><b>Página de configuración - Configuración del modelo</b></p>
                <img src="figures/shezhi1.png" width="100%" />
            </td>
            <td align="center" width="50%">
                <p><b>Página de configuración - Prompt personalizado</b></p>
                <img src="figures/shezhi2.png" width="100%" />
            </td>
        </tr>
    </table>
</div>

## 📥 Descarga e instalación

Voke ofrece paquetes de instalación para las tres plataformas principales: Windows, macOS y Linux.

- **Windows**: [Haga clic para descargar Voke v1.0.2](https://github.com/zyk42/Voke/releases/download/v1.0.2/Voke.Setup.1.0.2.exe)
- **macOS**: *(por publicar)*
- **Linux**: *(por publicar)*

## 🛠️ Modo de desarrollo

Si es un desarrollador o desea probar las funciones más recientes, puede ejecutar la aplicación desde el código fuente:

### 1. Preparación del entorno
- Node.js 18+
- pnpm (recomendado) o npm

### 2. Obtener el código fuente
```bash
git clone https://github.com/zyk/Voke.git
cd Voke
```

### 3. Instalar dependencias
```bash
pnpm install
```

### 4. Iniciar el modo de desarrollo
```bash
pnpm run dev
```
Este comando iniciará simultáneamente el proceso principal de Electron y el proceso de renderizado de Vite, con recarga en caliente (hot reload).

### 5. Compilar y empaquetar
```bash

# Construir la aplicación para una plataforma específica

# Si app-builder no usa el proxy correctamente
# En Windows, ejecute primero los siguientes comandos (7890 es el puerto de su VPN)
#$env:HTTP_PROXY="http://127.0.0.1:7890"
#$env:HTTPS_PROXY="http://127.0.0.1:7890"

# En Mac/Linux, ejecute primero los siguientes comandos
#export HTTP_PROXY="http://127.0.0.1:7890"
#export HTTPS_PROXY="http://127.0.0.1:7890"

pnpm run build:win   # Windows  
pnpm run build:mac   # macOS
pnpm run build:linux # Linux
```

## ⚙️ Configuración rápida

Después de iniciar la aplicación, acceda a la **página de configuración** para realizar una configuración rápida:

1. **Configuración de ASR (reconocimiento de voz)**:
    - Ingrese su ASR API Key.
    - De forma predeterminada se admite Alibaba Cloud DashScope (Qwen-ASR); también puede configurar otros servicios de ASR compatibles con el formato de OpenAI.
2. **Configuración de IA (modelo de lenguaje)**:
    - Ingrese su AI API Key.
    - Configure el Base URL y el nombre del modelo (por ejemplo, `qwen-flash`).

> **Nota**: La información de configuración se almacenará de forma cifrada en su dispositivo local y no se enviará a ningún servidor de terceros.
