# ?? EmocionesMulticanal - Sistema de Detección Emocional Multimodal

Sistema de análisis emocional en tiempo real para videollamadas que combina visión por computadora y procesamiento de lenguaje natural.

## ?? Descripción

EmocionesMulticanal es un sistema web que analiza emociones durante videollamadas mediante:
- **Análisis facial**: Detección de emociones a través de expresiones faciales usando MediaPipe
- **Análisis textual**: Transcripción de voz y análisis de sentimientos
- **Fusión multimodal**: Combinación inteligente de ambas modalidades para mayor precisión

## ?? Características

- ? **100% Web**: No requiere instalación, funciona en navegador
- ? **Tiempo Real**: Análisis instantáneo durante la videollamada
- ? **Privacidad**: Procesamiento local, datos no enviados a servidores
- ? **Multimodal**: Combina análisis visual y textual
- ? **Exportación**: Descarga de transcripciones, métricas y reportes
- ? **Gratuito**: Usa solo herramientas y servicios gratuitos

## ??? Tecnologías Utilizadas

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Visión**: MediaPipe Face Mesh, ONNX Runtime Web
- **Audio**: Web Speech API, MediaRecorder API
- **Videollamada**: Jitsi Meet (IFrame API)
- **Gráficos**: Chart.js
- **Hosting**: GitHub Pages (gratuito)

## ?? Instalación y Configuración

### Paso 1: Clonar o Descargar

```bash
# Opción 1: Clonar repositorio
git clone https://github.com/tu-usuario/EmocionesMulticanal-sistema.git
cd EmocionesMulticanal-sistema

# Opción 2: Descargar ZIP y extraer
```

### Paso 2: Estructura de Archivos

Asegúrate de tener esta estructura:

```
EmocionesMulticanal-sistema/
+-- index.html              # Página principal
+-- css/
¦   +-- styles.css          # Estilos CSS
+-- js/
¦   +-- main.js            # Script principal
¦   +-- vision.js          # Módulo de visión
¦   +-- audio.js           # Módulo de audio
¦   +-- fusion.js          # Módulo de fusión
¦   +-- export.js          # Módulo de exportación
+-- manual/
¦   +-- manual-usuario.html # Manual de usuario
+-- README.md              # Este archivo
```

### Paso 3: Configurar GitHub Pages

1. **Crear repositorio en GitHub**:
   - Ve a [github.com](https://github.com) y crea una cuenta
   - Crea un nuevo repositorio público llamado `EmocionesMulticanal-sistema`

2. **Subir archivos**:
   ```bash
   git add .
   git commit -m "Inicial: Sistema EmocionesMulticanal"
   git push origin main
   ```

3. **Habilitar GitHub Pages**:
   - Ve a Settings ? Pages
   - Source: "Deploy from a branch"
   - Branch: "main" / "/ (root)"
   - Guarda los cambios

4. **Acceder al sitio**:
   - Tu sitio estará en: `https://tu-usuario.github.io/EmocionesMulticanal-sistema`

### Paso 4: Configuración Alternativa (Local)

Para desarrollo local:

```bash
# Instalar servidor HTTP simple
npm install -g http-server

# Ejecutar servidor local
http-server -p 8080

# Abrir en navegador
# http://localhost:8080
```

## ?? Uso del Sistema

### Para Administradores

1. **Configurar sesión**:
   - Comparte el enlace del sistema con los participantes
   - Proporciona el nombre de la sala (por defecto: "EmocionesMulticanal-demo")

2. **Monitorear sesión**:
   - Los datos se procesan localmente en cada participante
   - Los reportes se generan individualmente

### Para Usuarios

1. **Acceder al sistema**: Abrir enlace proporcionado
2. **Otorgar permisos**: Permitir acceso a cámara y micrófono
3. **Iniciar análisis**: Hacer clic en "Iniciar Análisis"
4. **Participar**: Usar la videollamada normalmente
5. **Finalizar**: Descargar resultados y cerrar sesión

Ver [Manual de Usuario](manual/manual-usuario.html) para instrucciones detalladas.

## ?? Datos Exportados

El sistema genera los siguientes archivos:

- **`transcripcion.txt`**: Texto plano de la transcripción
- **`transcripcion.json`**: Transcripción con timestamps
- **`metricas.csv`**: Datos de análisis facial (yaw, pitch, estabilidad)
- **`sentimiento.csv`**: Análisis de sentimientos por segmento
- **`reporte.html`**: Reporte visual completo con gráficos

## ?? Configuración Avanzada

### Personalizar Emociones

En `js/vision.js`, modifica:

```javascript
this.emotionLabels = {
    'angry': 'Enojado',
    'disgust': 'Disgusto',
    'fear': 'Miedo',
    'happy': 'Feliz',
    'sad': 'Triste',
    'surprise': 'Sorpresa',
    'neutral': 'Neutral'
};
```

### Ajustar Pesos de Fusión

En `js/fusion.js`, modifica:

```javascript
this.weights = {
    visual: 0.6,    // Peso para emociones visuales
    textual: 0.4    // Peso para sentimiento textual
};
```

### Cambiar Idioma de Transcripción

En `js/audio.js`, modifica:

```javascript
this.speechRecognition.lang = 'es-ES'; // Español
// this.speechRecognition.lang = 'en-US'; // Inglés
```

## ?? Solución de Problemas

### Problemas Comunes

1. **No aparece video**:
   - Verificar permisos de cámara
   - Cerrar otras aplicaciones que usen la cámara
   - Probar en modo incógnito

2. **No funciona el micrófono**:
   - Verificar permisos de micrófono
   - Comprobar configuración del sistema
   - Usar auriculares con micrófono

3. **Rendimiento lento**:
   - Cerrar pestañas innecesarias
   - Usar Google Chrome
   - Verificar conexión a internet

4. **Error en transcripción**:
   - Verificar soporte de Web Speech API
   - Hablar más claramente
   - Comprobar configuración de idioma

### Logs de Depuración

Abrir Herramientas de Desarrollador (F12) y revisar la consola para mensajes de error.

## ?? Privacidad y Seguridad

- **Procesamiento local**: Los datos se analizan en el navegador del usuario
- **No almacenamiento**: No se guardan datos en servidores externos
- **Consentimiento**: Se solicita permiso explícito para cámara y micrófono
- **Limpieza**: Los datos temporales se eliminan al cerrar sesión

## ?? Métricas y Evaluación

### Métricas Técnicas

- **Precisión facial**: Basada en detección de landmarks
- **Confianza de transcripción**: Proporcionada por Web Speech API
- **Tasa de detección**: Porcentaje de frames con rostro detectado

### Métricas de Usuario

- **Satisfacción**: Encuestas post-sesión (implementar por separado)
- **Usabilidad**: Tiempo de configuración, errores de usuario
- **Utilidad**: Coherencia percibida de los resultados

## ?? Roadmap y Mejoras Futuras

### Versión 1.1
- [ ] Integración con Whisper WASM para mejor transcripción
- [ ] Modelo ONNX entrenado para emociones faciales
- [ ] Soporte para múltiples participantes

### Versión 1.2
- [ ] Análisis de tono de voz
- [ ] Detección de gestos corporales
- [ ] Dashboard en tiempo real para facilitadores

### Versión 2.0
- [ ] Integración con plataformas existentes (Zoom, Teams)
- [ ] Análisis de grupo y dinámicas
- [ ] IA generativa para insights automáticos

## ?? Contribuir

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -am 'Agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Crea un Pull Request

## ?? Licencia

Este proyecto está bajo la Licencia MIT. Ver `LICENSE` para más detalles.

## ?? Equipo

- **Desarrollo**: [Tu Nombre]
- **Metodología**: Design Thinking + Scrum + Lean
- **Evaluación**: Métricas técnicas y perceptivas

## ?? Soporte

- **Issues**: [GitHub Issues](https://github.com/tu-usuario/EmocionesMulticanal-sistema/issues)
- **Email**: soporte@EmocionesMulticanal.com
- **Documentación**: [Manual de Usuario](manual/manual-usuario.html)

---

**EmocionesMulticanal v1.0** - Sistema de Detección Emocional Multimodal para Videollamadas