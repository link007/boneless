# 🦴 BONELESS — Human-Readable Data Format

**Extensión:** `.boneless`  
**Pronunciación:** _/ˈboʊnləs/_  
**Significado:** “Sin huesos” → sin la rigidez de JSON 🧠

---

## 📘 Descripción general

**BONELESS** es un formato de intercambio de datos estructurado, **legible por humanos**, inspirado en JSON y YAML, pero diseñado desde cero con tres objetivos:

1. **Evitar la verbosidad de JSON** (comas, llaves, comillas innecesarias).  
2. **Permitir comentarios nativos** y **tipos explícitos**.  
3. **Mantener compatibilidad conceptual** con estructuras de objetos y listas, para facilitar su conversión a JSON, XML o TOML.

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

---

## 🔤 Sintaxis general

| Elemento | Descripción | Ejemplo |
|-----------|--------------|----------|
| **Bloque de objeto** | Se abre con `{` y se cierra con `}`. | `config { theme: dark }` |
| **Lista** | Se marca con `-` o con corchetes `[ ... ]`. | `items: - a - b - c` |
| **Strings** | Sin comillas si no contienen espacios o símbolos. | `name: Tomas` |
| **Comentarios** | Se marcan con `#` o `###` (bloques). | `# Comentario` |
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

## 🧬 Gramática básica (pseudo-BNF)

```ebnf
document      ::= (statement | comment)+
statement     ::= key ":" value | key object | "-" object
object        ::= "{" statement* "}"
key           ::= identifier
value         ::= string | number | boolean | special
comment       ::= "#" text | "###" text "###"
special       ::= date | color | regex | binary | unit
date          ::= "@" ISO8601
color         ::= "#" HEX
regex         ::= "/" pattern "/"
binary        ::= "b64:" BASE64
unit          ::= NUMBER UNIT
```
