# Ejercicio 1 – API de Promedio de Calificaciones

API REST desarrollada con Python y Flask que recibe el nombre de un estudiante y una lista de calificaciones, y devuelve el promedio calculado.

---

## Requisitos

- Python 3.8 o superior
- pip

---

## Instalación

### 1. Clonar o descargar el proyecto

```bash
git clone <url-del-repositorio>
cd ejercicio1
```

### 2. Crear y activar el entorno virtual

```bash
python -m venv venv
```

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / Mac:**
```bash
source venv/bin/activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

---

## Ejecución

```bash
python app.py
```

El servidor se iniciará en: `http://127.0.0.1:5000`

---

## Endpoint

### `POST /promedio`

Calcula el promedio de las calificaciones de un estudiante.

**URL:** `http://127.0.0.1:5000/promedio`

**Headers:**
```
Content-Type: application/json
```

**Body (JSON):**
```json
{
  "nombre": "Juan",
  "calificaciones": [80, 90, 85, 70]
}
```

**Respuesta exitosa (200):**
```json
{
  "nombre": "Juan",
  "calificaciones": [80, 90, 85, 70],
  "promedio": 81.25
}
```

**Respuesta de error – datos faltantes (400):**
```json
{
  "error": "Se requiere 'nombre' y 'calificaciones'"
}
```

**Respuesta de error – lista vacía (400):**
```json
{
  "error": "La lista de calificaciones no puede estar vacía"
}
```

---

## Prueba con Postman

1. Abrir Postman
2. Crear una nueva petición
3. Seleccionar método: **POST**
4. Ingresar la URL: `http://127.0.0.1:5000/promedio`
5. En la pestaña **Body** → seleccionar **raw** → elegir **JSON**
6. Pegar el siguiente JSON:

```json
{
  "nombre": "Juan",
  "calificaciones": [80, 90, 85, 70]
}
```

7. Hacer clic en **Send**

---

## Estructura del proyecto

```
ejercicio1/
│
├── venv/               # Entorno virtual (no se sube al repositorio)
├── app.py              # Código principal de la API
├── requirements.txt    # Dependencias del proyecto
├── .gitignore          # Archivos ignorados por Git
└── README.md           # Este archivo
```

---

## Tecnologías utilizadas

- [Python](https://www.python.org/)
- [Flask](https://flask.palletsprojects.com/)

## Prueba en Postman

![Prueba Postman](images/prueba.png)