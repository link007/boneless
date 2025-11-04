# 🦴 BONELESS — Human-Readable Data Format  

**Extensión:** `.boneless`  
**Pronunciación:** _/ˈboʊnləs/_  
**Significado:** “Sin huesos” → sin rigidez, sin peso innecesario.  

---

## 💭 Introducción

**BONELESS** nació de una idea sencilla:  
> los datos no deberían sentirse como un castigo.  

Fue creado **por desarrolladores, para desarrolladores**, cansados de pelear con llaves, comas y comillas.  
Cansados de perder tiempo en sintaxis, cuando lo que realmente quieren es **expresar estructuras, no escribir fórmulas**.  

Este formato no intenta reemplazar a JSON — lo **libera**.  
Le quita los huesos, las capas innecesarias, la frialdad de la máquina.  
Porque un programador **no es un autómata**, es una persona con creatividad, con cansancio, con noches sin dormir y una taza de café al lado.  

BONELESS es un recordatorio de que **los datos también pueden tener alma**.  
Que el código puede ser más humano.  
Que a veces, **lo simple también puede ser poderoso**.

---

## 📘 Descripción general

**BONELESS** es un formato de intercambio de datos **legible, expresivo y humano**, inspirado en JSON y YAML, pero diseñado desde cero con tres ideales:

1. **Evitar la rigidez de los formatos tradicionales.**  
2. **Facilitar el mockeo rápido y la experimentación libre.**  
3. **Recordar que los desarrolladores no somos robots.**  

Está pensado para quienes escriben datos a mano, configuran servicios, o crean prototipos sin tener que pensar en cada coma.

---

## 📄 Ejemplo básico

### JSON tradicional
```json
{
  "user": {
    "name": "Tomas",
    "age": 29,
    "verified": true,
    "skills": ["JavaScript", "ZF Transmissions", "Diagnostics"]
  }
}
```

### Equivalente en BONELESS
```boneless
user {
  name: Tomas
  age: 29
  verified: true
  skills:
    - JavaScript
    - ZF Transmissions
    - Diagnostics
}
```

🟢 **Ventajas:**
- No requiere comillas ni comas innecesarias.  
- Soporta comentarios.  
- Usa indentación natural.  
- Se lee como una conversación, no como un dictado.  

---

## 🔤 Sintaxis general

| Elemento | Descripción | Ejemplo |
|-----------|--------------|----------|
| **Bloque de objeto** | Se abre con `{` y se cierra con `}`. | `config { theme: dark }` |
| **Lista** | Se marca con `-` o `[ ... ]`. | `items: - a - b - c` |
| **Strings** | Sin comillas si no contienen espacios o símbolos. | `name: Tomas` |
| **Comentarios** | `#` o `###` (bloques). | `# Comentario` |
| **Tipos explícitos** | Prefijos y sufijos para valores especiales. | `date: @2025-11-04` |

---

## 🧠 Tipos soportados

```boneless
types_demo {
  date: @2025-11-04T14:25:00Z
  temperature: °36.7
  binary_data: b64:U29tZUJhc2U2NERhdGE=
  regex: /ZF\d{4}/
  distance: 24.5m
  color: #ff9933
  currency: $42.50
}
```

| Prefijo / Sufijo | Tipo | Ejemplo |
|-------------------|------|----------|
| `@` | Fecha o timestamp | `@2025-11-04T14:25:00Z` |
| `°` | Temperatura | `°36.7` |
| `b64:` | Binario | `b64:U29tZUJhc2U2NERhdGE=` |
| `/.../` | Expresión regular | `/ZF\d{4}/` |
| `#rrggbb` | Color | `#ff9933` |
| `$` | Moneda | `$42.50` |
| `m`, `v`, `Ω`, `kg`, etc. | Unidad | `12.6v`, `5.1Ω` |

---

## 💬 Comentarios

```boneless
### Información del usuario ###
user {
  name: Tomas   # Nombre del técnico
  role: "ZF Specialist"
  experience_years: 8
}
```

Comentarios que se leen como notas entre colegas, no advertencias del compilador.

---

## 🧩 Ejemplo avanzado

```boneless
### Configuración de diagnóstico BONELESS ###

app {
  name: "ZF Analyzer"
  version: 1.3.2
  author: Tomas
  last_update: @2025-11-04
}

settings {
  logging: true
  theme: dark
  thresholds {
    temperature: °90
    voltage: 12.6v
  }
}

solenoids {
  - id: A
    resistance: 5.1Ω
    type: linear
  - id: B
    resistance: 5.3Ω
    type: on/off
}
```

---

## 🧩 Filosofía

> “El código también puede ser poesía.”  

BONELESS no es solo un formato: es un pequeño acto de rebeldía contra la rigidez.  
Es para quienes escriben a las 3 a.m. con música lo-fi, que buscan que los datos **tengan sentido, no solo estructura**.  
Para quienes saben que **la productividad también nace del descanso, del orden y de la belleza**.

BONELESS recuerda que programar es un arte hecho por personas — no por autómatas.
