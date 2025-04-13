# 🐍 Guía Rápida de Expresiones Regulares en Python

Las expresiones regulares en Python se escriben como cadenas crudas usando `r"..."`, lo que permite evitar conflictos con caracteres especiales.

---

## 📌 Ejemplos prácticos

### 🔹 1. Comodín `.`
```python
patron = r"H.la"
```
- El `.` equivale a cualquier carácter.
- Coincide con palabras como `Hola`, `Hila`, `H1la`, etc.

---

### 🔹 2. Escapar un punto `.`
```python
patron = r"\."
```
- Se usa `\.` para buscar un punto literal.

---

### 🔹 3. Números: `\d`
```python
patron = r"\d{9}"
```
- `\d` representa un dígito.
- `{9}` indica exactamente 9 dígitos.

```python
# Teléfono con prefijo internacional
patron = r"\+34 \d{9}"  # Coincide con "+34 657553345"
```

---

### 🔹 4. Caracteres alfanuméricos: `\w`
```python
patron = r"\w"
```
- Coincide con letras, números y el guion bajo `_`.

---

### 🔹 5. Espacios en blanco: `\s`
```python
patron = r"\s"
```
- Coincide con espacios, tabulaciones o saltos de línea.

---

### 🔹 6. Inicio de cadena: `^`
```python
patron = r"^\w"
```
- Verifica si la cadena comienza con un carácter alfanumérico.

---

### 🔹 7. Validación de teléfono internacional
```python
patron = r"^\+\d{1,3}"     # Empieza con '+' seguido de 1 a 3 dígitos
patron = r"^\+\d{1,}"      # '+' seguido de 1 o más dígitos
```

---

### 🔹 8. Fin de cadena: `$`
```python
patron = r"mundo$"
```
- Coincide si la cadena termina en "mundo".

---

### 🔹 9. Coincidencia exacta de palabras con comodines
```python
import re

texto = "casa cosa casadc calada"
patron = r"\bc.sa\b"

encontrado = re.search(patron, texto)
print(encontrado)
```
- `\b` indica límites de palabra.
- `.` actúa como comodín para un carácter cualquiera.

---

### 🔹 10. Alternativas: `|`
```python
patron = r"platano|naranja|\b\w{7}\b"
```
- Coincide con "platano", "naranja" o cualquier palabra de exactamente 7 caracteres.

---

### 🔹 11. Repeticiones: `+`
```python
patron = r"a+"
```
- Coincide con una o más repeticiones de la letra `a`: `a`, `aa`, `aaa`, etc.

---

## 🧪 Extra: prueba tus patrones

Puedes probar tus expresiones regulares en [regex101.com](https://regex101.com)

---

¡Y recuerda! Las regex pueden parecer confusas al principio... pero con práctica, se vuelven herramientas poderosísimas. 💪✨

------

