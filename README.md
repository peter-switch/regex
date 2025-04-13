```markdown
# 📝 Expresiones Regulares en Python - Cheat Sheet

```python
# Sintaxis básica
patron = r"expresion_regular"  # Siempre comienza con 'r'

# 1. Carácter comodín (.)
patron = r"H.la"               # Busca: H + cualquier carácter + la
                               # Ej: "Hola", "Hala", "H9la"

# 2. Buscar caracteres especiales
patron = r"\."                 # Busca el punto literal (.)

# 3. Buscar dígitos numéricos
patron = r"\d{9}"              # 9 dígitos exactos (0-9)
patron = r"\+34 \d{9}"         # Teléfonos españoles: +34 123456789

# 4. Caracteres alfanuméricos
patron = r"\w"                 # Cualquier carácter alfanumérico [a-zA-Z0-9_]

# 5. Espacios en blanco
patron = r"\s"                 # Espacios, tabs, saltos de línea

# 6. Inicio de cadena
patron = r"^\w"                # Cadena que empieza con alfanumérico
patron = r"^\+\d{1,3}"         # Empieza con + y 1-3 dígitos

# 7. Fin de cadena
patron = r"mundo$"             # Cadena que termina con "mundo"

# 8. Límites de palabra
patron = r"\bc.sa\b"           # Palabras completas que coincidan con el patrón
                               # Ej: "casa", "cosa" en "casa cosa casadc"

# 9. Operador OR
patron = r"platano|naranja|\b\w{7}\b"  # Busca "platano" O "naranja" O palabras de 7 letras

# 10. Cuantificadores
patron = r"a+"                 # 1 o más 'a's consecutivas (a, aa, aaa...)

# Uso con el módulo re
import re
texto = "Ejemplo de texto para buscar"
resultado = re.search(patron, texto)
print(resultado)  # Muestra el primer match encontrado
```

## 📌 Ejemplos Prácticos

1. **Validar teléfono español**:  
   `r"^\+34[ -]?\d{9}$"` → +34666555444 o +34 666555444

2. **Buscar palabras específicas**:  
   `r"\bpython\b"` → Encuentra "python" como palabra completa

3. **Extraer emails**:  
   `r"\b[\w.-]+@[\w.-]+\.\w+\b"`

4. **Encontrar hashtags**:  
   `r"#\w+"` → #Python #regex

5. **Capturar fechas**:  
   `r"\d{2}/\d{2}/\d{4}"` → 31/12/2023
```  

💡 **Tip**: Usa [regex101.com](https://regex101.com/) para probar tus patrones interactivamente.

📦 **Módulo re**:  
```python
import re
re.findall(patron, texto)    # Devuelve todas las coincidencias
re.sub(patron, reemplazo, texto)  # Reemplaza coincidencias
```

¡Copia este cheat sheet y pégalo en tu proyecto! 🚀
