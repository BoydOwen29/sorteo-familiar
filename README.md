# 🎄 SORTEO NAVIDEÑO FAMILIAR - GUÍA DE USO

## 📋 ARCHIVOS IMPORTANTES

### Archivos de configuración (NO subir a GitHub):
- **`base.xlsx`**: Base de datos con participantes
- **`consideraciones.txt`**: Reglas especiales del sorteo (opcional)
- **`.gitignore`**: Protege archivos sensibles

### Archivos generados (NO subir a GitHub):
- **`links_para_enviar.txt`**: Links personalizados para cada participante

### Scripts principales:
- **`generar_web.py`**: Genera el sorteo y la página web
- **`enviar_whatsapp.py`**: Envía los links por WhatsApp automáticamente

### Solo en GitHub (público):
- **`docs/index.html`**: Página web del sorteo (sin lógica, solo visualización)

---

## 🚀 CÓMO HACER UN SORTEO NUEVO

### Paso 1: Generar el sorteo
```powershell
python generar_web.py
```

### Paso 1: Generar el sorteo
```powershell
python generar_web.py
```

Esto va a:
- ✅ Leer `base.xlsx`
- ✅ Aplicar reglas especiales (si existen en `consideraciones.txt`)
- ✅ Hacer sorteo aleatorio
- ✅ Generar `docs/index.html` (página web)
- ✅ Crear `links_para_enviar.txt` con links únicos

**IMPORTANTE:** Cada vez que ejecutes esto, se sobrescriben los links anteriores.

### Paso 2: Verificar el sorteo (opcional)
Abrí `links_para_enviar.txt` para ver los links generados.

⚠️ **NO abras ningún link** para no ver el sorteo.

### Paso 3: Subir a GitHub Pages
```powershell
git add docs/ .gitignore
git commit -m "Nuevo sorteo"
git push
```

### Paso 3: Subir a GitHub Pages
```powershell
git add docs/ .gitignore
git commit -m "Nuevo sorteo"
git push
```

Solo se sube la página web, NO los links ni la lógica.

### Paso 4: Enviar links por WhatsApp

#### Opción A - Automático (recomendado):
```powershell
python enviar_whatsapp.py
```

Elegí opción:
- **1**: Prueba (4 personas)
- **2**: Enviar a TODOS

Requisitos:
- WhatsApp Web abierto en Chrome
- No tocar el mouse mientras envía

#### Opción B - Manual:
Abrí `links_para_enviar.txt` y copiá/pegá cada link manualmente.

---

## 🔧 MODIFICAR PARTICIPANTES

### Agregar/quitar personas:
1. Editá `base.xlsx`
2. Columnas necesarias:
   - `integrante`: nombre
   - `grupo_familiar`: familia (o vacío si no tiene)
   - `grupo_edad`: categoría del participante
   - `telefono`: formato internacional con +

### Cambiar reglas especiales:
Editá `consideraciones.txt` siguiendo el formato del archivo.
[nombre] -> mayor: [receptor_fijo]
[nombre] -> menor: [receptor_fijo]
```

---

## 📱 ENVÍO POR WHATSAPP

### Mensaje que reciben:
```
🎄 ¡Hola [Nombre]! 🎅

¡Ya está listo el sorteo navideño familiar! 

Hacé click en tu link personal para ver a quién te tocó regalar:

https://boydowen29.github.io/sorteo-familiar?code=XXXXX

¡Felices Fiestas! 🎁✨
```

### Problemas comunes:

**Error: "El número de teléfono no es válido"**
- Verificá formato en Excel: `+5491112345678` (sin espacios)
- Si está como número en Excel, el script lo corrige automáticamente

**Se abren muchas pestañas**
- Es normal con PyWhatKit
- Cada mensaje abre una pestaña nueva que se cierra sola
- Alternativa: envío manual

**WhatsApp Web no responde**
- Refrescá la página
- Volvé a escanear el QR
- Verificá que el celular tenga internet

---

## 🔐 SEGURIDAD

### Archivos que NUNCA deben subirse a GitHub:
- ❌ `base.xlsx` (datos sensibles)
- ❌ `consideraciones.txt` (reglas especiales)
- ❌ `links_para_enviar.txt` (links del sorteo)
- ❌ Scripts de lógica y envío

Estos están protegidos por `.gitignore`.

### Lo único público en GitHub:
- ✅ `docs/index.html` (solo la página de visualización)
- ✅ `README.md` (documentación general)

---

## 🎯 RESUMEN RÁPIDO

Para hacer un sorteo completo:

```powershell
# 1. Generar sorteo
python generar_web.py

# 2. Subir a GitHub
git add docs/ .gitignore
git commit -m "Nuevo sorteo"
git push

# 3. Enviar por WhatsApp
python enviar_whatsapp.py
```

**LISTO!** 🎉

---

**Última actualización:** 16 de Noviembre, 2025
