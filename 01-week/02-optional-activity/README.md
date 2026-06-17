# Proyecto Móvil – IceCream-App

**Asignatura:** Programación Móvil  
**Semana:** 1 – Fundamentos y planificación de proyectos móviles  
**Estudiantes:**

- Brandow Stivent Claros Polania
- Jeronimo Artunduaga Diaz
- Victor Manuel Brand Cepeda
- Ilder Brandow Sanchez

**Institución:** Corporacion Universitaria del Huila "CORHUILA"

---

# 1 Mapa del Proyecto

## 1.1 Nombre del Proyecto

IceCream-App

## 1.2 Problema que Resuelve

IceCream-App va a resolver la ineficiencia en la gestión tradicional de pedidos en heladerías físicas, donde los clientes deben hacer filas, no pueden personalizar fácilmente sus productos de forma digital y el negocio carece de automatización en la recepción y control de pedidos. Ademas, reduce la dependencia de plataformas intermediarias como Rappi o Uber, que estas implican comisiones elevadas y menor control sobre la experiencia del cliente. Lo que busca la aplicación es eliminar los errores operacionales y mejorar la satisfacción del cliente mediante una experiencia de compra fluida y directa.

## 1.3 Usuario Objetivo

### Clientes Finales

Personas entre 15 y 45 años con hábitos digitales activos, que buscan rapidez, comodidad y personalización en sus pedidos. Este segmento valora la capacidad de diseñar productos personalizados, visualizar opciones antes de comprometer su compra y evitar esperas innecesarias.

### Administradores de la Heladería

Propietarios o encargados responsables de la operación diaria que necesitan optimizar procesos, controlar ventas en tiempo real, mejorar la eficiencia operativa y reducir costos derivados de intermediarios. Requieren herramientas para gestionar inventario, procesar pedidos de forma organizada y obtener análisis de comportamiento del cliente.

## 1.4 Objetivo General

Diseñar y desarrollar una aplicación móvil que permita a los clientes consultar el menú digital, personalizar sus helados, realizar pedidos en línea y enviarlos directamente al establecimiento, optimizando la experiencia del usuario y aumentando la eficiencia operativa del negocio. De esta forma, se busca crear un ecosistema digital completo que beneficie tanto a consumidores como al comercio.

## 1.5 Propuesta de Valor

IceCream-App digitaliza la experiencia de compra en heladerías, permitiendo pedidos rápidos, personalizados y sin intermediarios, mejorando tanto la experiencia del cliente como la rentabilidad del negocio.

## 1.6 Plataforma Objetivo

Android

---

# 2. MVP y Fuera de Alcance

## MVP (Funcionalidades Mínimas)

- Visualización del menú de helados con detalles (nombre, descripción, imagen, precio,)
- Sistema de personalización de helados
  - selección de sabores (chocolate, vainilla.)
  - toppings (chip de chocolate, nutella, flips)
  - tamaño de vaso (por onzas "con o sin galleta")
- Carrito de compras funcional con opcion de modificar cantidades
- Confirmación de pedido con resumen detallado en la plataforma.
- Servicio a Domicilio.
- Panel básico de administrador para gestionar productos.

## Fuera de Alcance (No se implementa aún)

- Pagos en línea integrados.
- Sistema de fidelización o puntos de recompensa.
- Notificacion de entrega de pidido detallado al whatsapp e Email.
- Registro del Uusuario a la App.

---

# 3. Funcionalidades (Priorización MoSCoW)

| Funcionalidad                                          | Prioridad | Descripción (P)                                                      |
| ------------------------------------------------------ | --------- | -------------------------------------------------------------------- |
| Visualizar menú de helados                             | MUST      | Mostrar catálogo completo con imágenes, precios y descripción        |
| Panel básico de administrador para gestionar productos | MUST      | Hacer el ingreso del administrador a el panel y listar sus productos |
| Agregar al carrito y personalizar                      | MUST      | Permitir seleccionar productos y personalizar características        |
| Confirmar pedido                                       | SHOULD    | Generar confirmación y enviarla al establecimiento                   |

---

# 4. Riesgos Iniciales y Mitigación

| Riesgo                          | Tipo    | Probabilidad | Impacto | Mitigación                                                                                 |
| ------------------------------- | ------- | ------------ | ------- | ------------------------------------------------------------------------------------------ |
| Alcance demasiado grande        | Alcance | Alta         | Alto    | Definir claramente el MVP y dejar funcionalidades extras fuera del cronograma              |
| Problemas con base de datos     | Técnico | Media        | Alto    | Probar conexión desde etapas tempranas, usar base de datos confiable (Firebase)            |
| Falta de tiempo                 | Gestión | Media        | Alto    | Planificar por sprints semanales y priorizar funcionalidades MUST                          |
| Problemas en diseño de interfaz | UX      | Media        | Medio   | Crear wireframes y prototipos antes de comenzar programación                               |
| Errores en autenticación        | Técnico | Media        | Alto    | Implementar login simple primero, usar librerías de autenticación probadas                 |
| Compatibilidad en Android       | Técnico | Media        | Medio   | Usar framework multiplataforma (React Native) o desarrollar nativamente con sincronización |

---

# 5. Ruta de Trabajo (4 Semanas)

La planificación se basa en el desarrollo incremental del MVP de IceCream-App, priorizando primero la estructura del sistema, luego el catálogo, posteriormente la personalización y finalmente el flujo completo de pedidos y administración.

---

## Semana 1: Diseño del Sistema y Base del Proyecto

- Definición técnica del MVP y arquitectura de la aplicación
- Creación de wireframes de cliente (menú, personalización, carrito)
- Wireframe del panel administrador
- Diseño del modelo de base de datos (productos, opciones, pedidos)
- Configuración del repositorio y entorno de desarrollo Android
- Creación de la estructura base del proyecto (pantallas vacías y navegación)

**Resultado esperado:**  
Estructura inicial de la app funcionando con navegación básica y diseño definido.

---

## Semana 2: Catálogo de Productos (Menú)

- Implementación de la base de datos de productos
- Pantalla de visualización del menú de helados
- Mostrar imagen, nombre, descripción y precio
- Conexión app → base de datos
- Carga dinámica de productos desde el administrador
- Pruebas de visualización y rendimiento del catálogo

**Resultado esperado:**  
Menú de helados funcional cargado desde base de datos.

---

## Semana 3: Personalización y Carrito

- Sistema de personalización de helados:
  - selección de sabores
  - toppings
  - tamaño
- Cálculo dinámico de precio según personalización
- Implementación del carrito de compras
- Modificación de cantidades en carrito
- Persistencia temporal del carrito
- Interfaz intuitiva de personalización

**Resultado esperado:**  
Usuario puede personalizar productos y agregarlos al carrito correctamente.

---

## Semana 4: Pedido y Panel Administrador

- Confirmación de pedido con resumen detallado
- Registro del pedido en base de datos
- Panel administrador básico:
  - crear producto
  - editar producto
  - listar productos
- Flujo completo: catálogo → personalización → carrito → pedido
- Pruebas funcionales completas del MVP
- Ajustes de interfaz y estabilidad
- Preparación de documentación y entrega

**Resultado esperado:**  
MVP completo de IceCream-App funcional para cliente y administrador.
