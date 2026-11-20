# Música con las manos

Instrumentos virtuales que se tocan en el aire con la cámara web: **arpa llanera**, **xilófono**, **tambores** y **cuerdas libres**. Todo corre en el navegador.

- Detección de manos en tiempo real con [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe/solutions/vision/hand_landmarker) (HandLandmarker).
- Sonido sintetizado con WebAudio: cuerda pulsada (Karplus-Strong) para la arpa, tonos de barra para el xilófono y síntesis de batería.

## Cómo usarla

1. Descarga `index.html` y ábrelo con un servidor local (la cámara necesita `localhost` o HTTPS):
   ```
   python3 -m http.server 8000 --bind 127.0.0.1
   ```
2. Abre `http://localhost:8000` en Chrome y permite la cámara.
3. Para formato vertical 9:16 usa `http://localhost:8000/?reel=1`.

## Controles

| Tecla | Acción |
|---|---|
| H | Arpa llanera |
| X | Xilófono |
| D | Tambores |
| A | Cuerdas automáticas entre dedos (modo libre) |
| ↑ / ↓ | Subir o bajar un semitono la cuerda seleccionada |
| Backspace | Borrar la última cuerda creada |
| C | Borrar todas las cuerdas |
| F | Pantalla completa |

En **Cuerdas libres**, junta pulgar e índice de las dos manos a la vez y mantén unos 0.35 s para crear una cuerda fija.

## Notas

- La arpa usa 22 notas diatónicas de Do3 a Do6; la longitud de cada cuerda se calcula para su nota.
- El xilófono tiene 15 barras de Do4 a Do6.
- Los tambores son 6 piezas; cada una suena al cruzarla con un dedo.
- Probado en Chrome. No probado en Safari.

## Privacidad

La cámara se usa solo en el navegador. Ningún fotograma sale de tu equipo: el modelo de detección se descarga una vez desde Google y todo lo demás corre localmente.
