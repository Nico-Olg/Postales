# Cómo personalizar la ubicación de Google Maps

El mapa de Google Maps ya está integrado en la sección de Ubicación, pero necesitas actualizar la URL con la ubicación exacta de tu proyecto.

## Pasos para obtener el código correcto de Google Maps:

### Opción 1: Usando Google Maps (Recomendado)

1. **Ve a Google Maps**: https://www.google.com/maps

2. **Busca la ubicación exacta** de "Postales del Viñedo":
   - Puedes buscar por dirección exacta
   - O hacer clic en el mapa para marcar la ubicación precisa
   - O buscar coordenadas GPS si las tienes

3. **Haz clic en "Compartir"** (botón en el panel izquierdo)

4. **Selecciona la pestaña "Insertar un mapa"**

5. **Copia el código HTML** que aparece (será algo como):
   ```html
   <iframe src="https://www.google.com/maps/embed?pb=..." ...></iframe>
   ```

6. **Extrae solo la URL** del atributo `src` (la parte que está entre comillas después de `src=`)

7. **Pega esa URL** en el archivo `PostalesDelVinedoLanding.jsx` en la línea donde dice:
   ```jsx
   src="https://www.google.com/maps/embed?pb=!1m18!1m12..."
   ```

### Opción 2: Usando coordenadas GPS

Si tienes las coordenadas GPS exactas del proyecto:

1. Reemplaza la URL del iframe con este formato:
   ```jsx
   src="https://maps.google.com/maps?q=LATITUD,LONGITUD&t=&z=15&ie=UTF8&iwloc=&output=embed"
   ```

   Por ejemplo, si tus coordenadas son `-30.744567, -59.642345`:
   ```jsx
   src="https://maps.google.com/maps?q=-30.750293528738894, -59.61139471952832&t=&z=15&ie=UTF8&iwloc=&output=embed"
   ```

### Personalización adicional del mapa:

Puedes agregar parámetros a la URL para personalizar el mapa:

- **Nivel de zoom**: Cambia `z=15` (valores de 1 a 20, donde 20 es máximo zoom)
- **Tipo de mapa**:
  - `&t=m` - Mapa normal (por defecto)
  - `&t=k` - Vista satélite
  - `&t=h` - Vista híbrida (satélite + nombres)
  - `&t=p` - Vista de terreno

### Ejemplo de ubicación para La Paz, Entre Ríos:

```jsx
src="https://maps.google.com/maps?q=La+Paz,+Entre+Ríos,+Argentina&t=&z=13&ie=UTF8&iwloc=&output=embed"
```

## Ubicación actual del código

El iframe de Google Maps está en el archivo:
- **Archivo**: `PostalesDelVinedoLanding.jsx`
- **Componente**: `Location`
- **Línea aproximada**: 476

## Funcionalidades del mapa embebido:

✅ Zoom interactivo (rueda del mouse o botones +/-)
✅ Arrastrar para mover el mapa
✅ Botón "Ver en Google Maps" para abrir en pantalla completa
✅ Carga optimizada (lazy loading)
✅ Responsive (se adapta a móviles)
✅ Accesible (incluye title para lectores de pantalla)

## Nota importante:

La URL actual en el código es un placeholder genérico para La Paz, Entre Ríos. **Debes reemplazarla con la ubicación exacta de tu proyecto** para que los visitantes puedan encontrar el lugar correcto.
