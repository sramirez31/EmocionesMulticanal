# ?? EmocionesMulticanal - Sistema de Detecci�n Emocional Multimodal

Sistema de an�lisis emocional en tiempo real para videollamadas que combina visi�n por computadora y procesamiento de lenguaje natural.

## ?? Descripci�n

EmocionesMulticanal es un sistema web que analiza emociones durante videollamadas mediante:
- **An�lisis facial**: Detecci�n de emociones a trav�s de expresiones faciales usando MediaPipe
- **An�lisis textual**: Transcripci�n de voz y an�lisis de sentimientos
- **Fusi�n multimodal**: Combinaci�n inteligente de ambas modalidades para mayor precisi�n

## ?? Caracter�sticas

- ? **100% Web**: No requiere instalaci�n, funciona en navegador
- ? **Tiempo Real**: An�lisis instant�neo durante la videollamada
- ? **Privacidad**: Procesamiento local, datos no enviados a servidores
- ? **Multimodal**: Combina an�lisis visual y textual
- ? **Exportaci�n**: Descarga de transcripciones, m�tricas y reportes
- ? **Gratuito**: Usa solo herramientas y servicios gratuitos

## ??? Tecnolog�as Utilizadas

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Visi�n**: MediaPipe Face Mesh, ONNX Runtime Web
- **Audio**: Web Speech API, MediaRecorder API
- **Videollamada**: Jitsi Meet (IFrame API)
- **Gr�ficos**: Chart.js
- **Hosting**: GitHub Pages (gratuito)

## ?? Instalaci�n y Configuraci�n

### Paso 1: Clonar o Descargar

```bash
# Opci�n 1: Clonar repositorio
git clone https://github.com/tu-usuario/EmocionesMulticanal-sistema.git
cd EmocionesMulticanal-sistema

# Opci�n 2: Descargar ZIP y extraer
```

### Paso 2: Estructura de Archivos

Aseg�rate de tener esta estructura:

```
EmocionesMulticanal-sistema/
+-- index.html              # P�gina principal
+-- css/
�   +-- styles.css          # Estilos CSS
+-- js/
�   +-- main.js            # Script principal
�   +-- vision.js          # M�dulo de visi�n
�   +-- audio.js           # M�dulo de audio
�   +-- fusion.js          # M�dulo de fusi�n
�   +-- export.js          # M�dulo de exportaci�n
+-- manual/
�   +-- manual-usuario.html # Manual de usuario
+-- README.md              # Este archivo
```

### Paso 3: Configurar GitHub Pages

1. **Crear repositorio en GitHub**:
   - Ve a [github.com](https://github.com) y crea una cuenta
   - Crea un nuevo repositorio p�blico llamado `EmocionesMulticanal-sistema`

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
   - Tu sitio estar� en: `https://tu-usuario.github.io/EmocionesMulticanal-sistema`

### Paso 4: Configuraci�n Alternativa (Local)

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

1. **Configurar sesi�n**:
   - Comparte el enlace del sistema con los participantes
   - Proporciona el nombre de la sala (por defecto: "EmocionesMulticanal-demo")

2. **Monitorear sesi�n**:
   - Los datos se procesan localmente en cada participante
   - Los reportes se generan individualmente

### Para Usuarios

1. **Acceder al sistema**: Abrir enlace proporcionado
2. **Otorgar permisos**: Permitir acceso a c�mara y micr�fono
3. **Iniciar an�lisis**: Hacer clic en "Iniciar An�lisis"
4. **Participar**: Usar la videollamada normalmente
5. **Finalizar**: Descargar resultados y cerrar sesi�n

Ver [Manual de Usuario](manual/manual-usuario.html) para instrucciones detalladas.

## ?? Datos Exportados

El sistema genera los siguientes archivos:

- **`transcripcion.txt`**: Texto plano de la transcripci�n
- **`transcripcion.json`**: Transcripci�n con timestamps
- **`metricas.csv`**: Datos de an�lisis facial (yaw, pitch, estabilidad)
- **`sentimiento.csv`**: An�lisis de sentimientos por segmento
- **`reporte.html`**: Reporte visual completo con gr�ficos

## ?? Configuraci�n Avanzada

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

### Ajustar Pesos de Fusi�n

En `js/fusion.js`, modifica:

```javascript
this.weights = {
    visual: 0.6,    // Peso para emociones visuales
    textual: 0.4    // Peso para sentimiento textual
};
```

### Cambiar Idioma de Transcripci�n

En `js/audio.js`, modifica:

```javascript
this.speechRecognition.lang = 'es-ES'; // Espa�ol
// this.speechRecognition.lang = 'en-US'; // Ingl�s
```

## ?? Soluci�n de Problemas

### Problemas Comunes

1. **No aparece video**:
   - Verificar permisos de c�mara
   - Cerrar otras aplicaciones que usen la c�mara
   - Probar en modo inc�gnito

2. **No funciona el micr�fono**:
   - Verificar permisos de micr�fono
   - Comprobar configuraci�n del sistema
   - Usar auriculares con micr�fono

3. **Rendimiento lento**:
   - Cerrar pesta�as innecesarias
   - Usar Google Chrome
   - Verificar conexi�n a internet

4. **Error en transcripci�n**:
   - Verificar soporte de Web Speech API
   - Hablar m�s claramente
   - Comprobar configuraci�n de idioma

### Logs de Depuraci�n

Abrir Herramientas de Desarrollador (F12) y revisar la consola para mensajes de error.

## ?? Privacidad y Seguridad

- **Procesamiento local**: Los datos se analizan en el navegador del usuario
- **No almacenamiento**: No se guardan datos en servidores externos
- **Consentimiento**: Se solicita permiso expl�cito para c�mara y micr�fono
- **Limpieza**: Los datos temporales se eliminan al cerrar sesi�n

## ?? M�tricas y Evaluaci�n

### M�tricas T�cnicas

- **Precisi�n facial**: Basada en detecci�n de landmarks
- **Confianza de transcripci�n**: Proporcionada por Web Speech API
- **Tasa de detecci�n**: Porcentaje de frames con rostro detectado

### M�tricas de Usuario

- **Satisfacci�n**: Encuestas post-sesi�n (implementar por separado)
- **Usabilidad**: Tiempo de configuraci�n, errores de usuario
- **Utilidad**: Coherencia percibida de los resultados

## ?? Roadmap y Mejoras Futuras

### Versi�n 1.1
- [ ] Integraci�n con Whisper WASM para mejor transcripci�n
- [ ] Modelo ONNX entrenado para emociones faciales
- [ ] Soporte para m�ltiples participantes

### Versi�n 1.2
- [ ] An�lisis de tono de voz
- [ ] Detecci�n de gestos corporales
- [ ] Dashboard en tiempo real para facilitadores

### Versi�n 2.0
- [ ] Integraci�n con plataformas existentes (Zoom, Teams)
- [ ] An�lisis de grupo y din�micas
- [ ] IA generativa para insights autom�ticos

## ?? Contribuir

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit tus cambios (`git commit -am 'Agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Crea un Pull Request

## ?? Licencia

Este proyecto est� bajo la Licencia MIT. Ver `LICENSE` para m�s detalles.

## ?? Equipo

- **Desarrollo**: [Tu Nombre]
- **Metodolog�a**: Design Thinking + Scrum + Lean
- **Evaluaci�n**: M�tricas t�cnicas y perceptivas

## ?? Soporte

- **Issues**: [GitHub Issues](https://github.com/tu-usuario/EmocionesMulticanal-sistema/issues)
- **Email**: soporte@EmocionesMulticanal.com
- **Documentaci�n**: [Manual de Usuario](manual/manual-usuario.html)

---

**EmocionesMulticanal v1.0** - Sistema de Detecci�n Emocional Multimodal para Videollamadas