# 🛍️ MiniStockly API ✨

> *(≧◡≦) ♡ ¡Bienvenido a MiniStockly! Un mini proyecto hecho con amor para aprender sobre APIs REST)*

---

## 🌟 ¿Qué es esto?

🌱 **MiniStockly** es una **versión reducida y simplificada** de un sistema de inventario inspirado en **Stockly**, pero diseñado exclusivamente para:

- 📚 Aprender cómo funcionan las **API REST**
- 🧠 Comprender los métodos HTTP: `GET`, `POST`, `PUT`, `DELETE`
- 💻 Hacer pruebas con **Postman**
- 🖥️ Conectar **front-end con back-end** usando PHP y JavaScript

> ⚠️ **Este proyecto no es el sistema completo de Stockly**, solo es una versión mini 🌱 para fines académicos y de práctica.

---

## 🛠️ Tecnologías utilizadas

- 🐘 PHP (puro, sin frameworks)
- 🛢️ MySQL (vía XAMPP)
- 📬 Postman (para probar la API)
- 🎨 HTML + CSS + JS para la interfaz gráfica
- 💡 Fetch API para conectar con PHP desde el front

---

## 🧩 Estructura del proyecto

miniStocklyApi/
├── backEnd/
│ ├── create.php
│ ├── read.php
│ ├── update.php
│ ├── delete.php
│ └── config/database.php
├── frontEnd-miniStockly/
│ ├── index.html
│ ├── app.js
│ └── style.css
└── miniStockly_api.sql

---

## 🚀 ¿Cómo probar esta API?

1. 🧰 Instala [XAMPP](https://www.apachefriends.org/index.html)
2. 🗂️ Coloca la carpeta `miniStocklyApi` en `htdocs`
3. 🧠 Importa el archivo `miniStockly_api.sql` en **phpMyAdmin**
4. ▶️ Inicia Apache y MySQL
5. 🌐 Abre en el navegador:
http://localhost:8012/miniStocklyApi/frontEnd-miniStockly/index.html


6. 🔁 Prueba la API desde Postman:

| Método  | Endpoint                                     | Descripción              |
|---------|----------------------------------------------|--------------------------|
| `GET`   | `/backEnd/read.php`                          | Obtener todos los productos |
| `POST`  | `/backEnd/create.php`                        | Crear nuevo producto     |
| `PUT`   | `/backEnd/update.php`                        | Actualizar producto      |
| `DELETE`| `/backEnd/delete.php`                        | Eliminar producto        |

---

## 🧪 Cómo hacer pruebas (tests) en Postman 🛠️🐾

> (๑•̀ㅂ•́)و✧ ¡Vamos a verificar que todo funcione correctamente con Postman!

### 🛑 Antes de comenzar:
- Asegúrate de que **Apache y MySQL estén corriendo** en XAMPP.
- Accede a tus endpoints usando el puerto correcto (ej: `8012` si es tu caso).
- Ten tu base de datos importada desde `miniStockly_api.sql`.

---

### 📘 Ejemplo 1: Test para `GET` (read.php)

  1. Método: `GET`  
  2. URL: `http://localhost:8012/miniStocklyApi/backEnd/read.php`
  3. Ve a la pestaña **"Tests"**
  4. Agrega este código:
     
    pm.test("Status code is 200", function () {
      pm.response.to.have.status(200);
    });
    
    pm.test("La respuesta contiene productos", function () {
      var jsonData = pm.response.json();
      pm.expect(jsonData.length).to.be.above(0);
    });

---

### 📘 Ejemplo 2: Test para POST (create.php)
1. Método: POST
2. URL: http://localhost:8012/miniStocklyApi/backEnd/create.php
3. Body → raw → JSON:
   
               {
                 "nombre": "Café",
                 "cantidad": 20,
                 "precio": 4500
               }

5. En la pestaña "Tests", escribe:
   
          pm.test("Producto creado con éxito", function () {
            var jsonData = pm.response.json();
            pm.expect(jsonData.mensaje).to.include("éxito");
          });

---

###📘 Ejemplo 3: Test para PUT (update.php)
1. Método: PUT
2. URL: http://localhost:8012/miniStocklyApi/backEnd/update.php
3. Body → raw → JSON:
        
        {
          "id": 1,
          "nombre": "Café molido",
          "cantidad": 25,
          "precio": 4800
        }

4. En la pestaña "Tests":

          pm.test("Producto actualizado correctamente", function () {
            var jsonData = pm.response.json();
            pm.expect(jsonData.mensaje).to.include("actualizado");
          });

---

###📘 Ejemplo 4: Test para DELETE (delete.php)
1. Método: DELETE
2. URL: http://localhost:8012/miniStocklyApi/backEnd/delete.php
3. Body → raw → JSON:
        
        {
          "id": 1
        }

4. En la pestaña "Tests":

        pm.test("Producto eliminado correctamente", function () {
          var jsonData = pm.response.json();
          pm.expect(jsonData.mensaje).to.include("eliminado");
        });

---
      🧸 Autor y propósito
      Este proyecto fue creado por 💻 un estudiante entusiasta como parte de su aprendizaje en desarrollo de software.
      
    (*＾▽＾)／ ¡Aprender haciendo es lo más poderoso!

      💖 Agradecimientos
      A ti, por leer esto 💕
      
      A los errores que me enseñaron más que los aciertos (╥﹏╥)

      Y a las APIs, por conectar el mundo 🌐

> 🐾 Notas finales
Este proyecto es 100% educativo.
Si lo usas o mejoras, ¡dale una estrella! ⭐

 ---

(ﾉ◕ヮ◕)ﾉ*:･ﾟ✧ Gracias por visitar MiniStockly ✧･ﾟ: *ヽ(◕ヮ◕ヽ)


