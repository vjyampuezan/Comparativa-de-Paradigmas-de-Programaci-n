# Comparativa de Paradigmas de Programación - ESPE-Tech

Este proyecto implementa un sistema de gestión de inventario para laboratorios tecnológicos, resolviendo un problema algorítmico mediante dos enfoques: **Imperativo** y **Funcional (Declarativo)**.

## 🚀 Tecnologías Utilizadas
* **Java 21** (Amazon Corretto)
* **Spring Boot 3.4+**
* **Spring Data JPA** (Persistencia)
* **Lombok** (Productividad)
* **H2 Database** (Memoria)

## 📊 Análisis Comparativo de Paradigmas

### 1. Paradigma Imperativo (Estructura Tradicional)
* **Legibilidad:** Requiere seguir el flujo paso a paso (bucles `for`, condicionales `if` anidados). Es más "ruidoso" visualmente.
* **Mantenibilidad:** Difícil de escalar. Si se añaden más reglas de filtrado, el código tiende a volverse un "espagueti" de lógica.
* **Control:** Ofrece un control total sobre el estado y los acumuladores manuales, pero es propenso a errores de "fuera de índice" o estados mutables.

### 2. Paradigma Funcional (Java Streams API)
* **Legibilidad:** Altamente declarativo. El código dice *qué* se quiere hacer (`filter`, `groupingBy`, `map`) en lugar de *cómo* hacerlo. Reduce las líneas de código significativamente.
* **Mantenibilidad:** Muy alta. Añadir un nuevo filtro es tan simple como agregar una línea `.filter()`.
* **Eficiencia:** Permite el uso de `.parallelStream()` de forma nativa, facilitando el procesamiento de grandes volúmenes de datos (como los 10,000 registros solicitados) sin cambiar la estructura del código.

## ⚙️ Arquitectura
El proyecto sigue una arquitectura de capas limpia y desacoplada:
1. **Controller:** Expone endpoints REST y métricas de eficiencia.
2. **Service:** Contiene la lógica algorítmica de ambos paradigmas.
3. **Model (Entity):** Define la persistencia del Hardware.
4. **DTO:** Facilita la transferencia de resultados procesados.
5. **AI Service:** Genera mensajes dinámicos basados en los resultados analíticos.

## 🛠️ Cómo Probar la API
El proyecto incluye un endpoint de demostración que se puede probar directamente en el navegador:
`http://localhost:8080/api/inventario/demo/funcional`
