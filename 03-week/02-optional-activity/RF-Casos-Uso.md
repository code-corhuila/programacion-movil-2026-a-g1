# Documentación de Requerimientos

Tecnologías: Ionic React, Node/Express API, PostgreSQL, Docker

---

# 1. Actores del sistema

| Actor         | Descripción                                                                               |
| ------------- | ----------------------------------------------------------------------------------------- |
| Cliente       | Usuario que navega el menú, personaliza helados y realiza pedidos desde la app móvil.     |
| Administrador | Persona encargada de gestionar el catálogo de helados (crear, editar y listar productos). |
| Sistema       | Backend que procesa pedidos, calcula precios y almacena información en la base de datos.  |

---

# 2. Requerimientos Funcionales (RF)

RF-01: Ver menú de helados  
Descripción: El sistema debe mostrar el catálogo de helados disponibles con imagen, nombre y precio.  
Prioridad: Must  
Criterio de aceptación:  
Dado que el usuario accede al menú  
Cuando la pantalla carga  
Entonces el sistema muestra la lista de helados con imagen, nombre y precio.

---

RF-02: Ver detalle de producto  
Descripción: El sistema debe mostrar la información detallada del helado seleccionado.  
Prioridad: Must  
Criterio de aceptación:  
Dado que el usuario selecciona un helado  
Cuando abre la pantalla de detalle  
Entonces visualiza descripción, precio base y opciones de personalización.

---

RF-03: Personalizar helado  
Descripción: El sistema debe permitir seleccionar sabor, toppings, tipo de envase y tamaño.  
Prioridad: Must  
Criterio de aceptación:  
Dado que el usuario está en la pantalla de detalle  
Cuando selecciona sabor, toppings y tamaño  
Entonces el sistema guarda la personalización temporal.

---

RF-04: Calcular precio dinámico  
Descripción: El sistema debe actualizar el precio según las opciones seleccionadas.  
Prioridad: Must  
Criterio de aceptación:  
Dado que el usuario cambia opciones  
Cuando agrega o elimina toppings o cambia tamaño  
Entonces el sistema recalcula el precio automáticamente.

---

RF-05: Agregar producto al carrito  
Descripción: El sistema debe permitir añadir un helado personalizado al carrito.  
Prioridad: Must  
Criterio de aceptación:  
Dado un helado personalizado  
Cuando el usuario presiona agregar al carrito  
Entonces el producto se almacena en el carrito.

---

RF-06: Ver carrito de compras  
Descripción: El sistema debe mostrar los productos agregados antes de confirmar el pedido.  
Prioridad: Must  
Criterio de aceptación:  
Dado que el usuario abre el carrito  
Cuando entra a la sección  
Entonces visualiza productos, cantidades y total.

---

RF-07: Modificar cantidad en carrito  
Descripción: El sistema debe permitir cambiar cantidades de productos en el carrito.  
Prioridad: Must  
Criterio de aceptación:  
Dado un producto en el carrito  
Cuando el usuario cambia la cantidad  
Entonces el total se actualiza.

---

RF-08: Confirmar pedido  
Descripción: El sistema debe permitir confirmar el pedido del carrito.  
Prioridad: Should  
Criterio de aceptación:  
Dado que el carrito está listo  
Cuando el usuario confirma el pedido  
Entonces el sistema registra el pedido.

---

RF-09: Guardar pedido en base de datos  
Descripción: El backend debe almacenar el pedido con su información y detalles.  
Prioridad: Should  
Criterio de aceptación:  
Dado un pedido confirmado  
Cuando el sistema procesa la solicitud  
Entonces el pedido se guarda en la base de datos.

---

RF-10: Administrar productos  
Descripción: El administrador puede crear, editar y listar productos del menú.  
Prioridad: Must  
Criterio de aceptación:  
Dado que el administrador accede al panel  
Cuando gestiona productos  
Entonces puede crear, editar y visualizar el catálogo.

---

# 3. Requerimientos No Funcionales (RNF)

RNF-01 Rendimiento  
La app debe cargar el menú de helados en menos de 3 segundos.

RNF-02 Compatibilidad  
La aplicación debe ser compatible con Android 10 o superior.

RNF-03 Usabilidad  
La interfaz debe ser simple, visual y con colores llamativos apropiados para una heladería.

RNF-04 Disponibilidad  
El sistema backend debe estar disponible durante el horario de funcionamiento del negocio.

RNF-05 Seguridad  
Las operaciones de administrador deben requerir autenticación.

RNF-06 Escalabilidad  
La base de datos PostgreSQL debe ejecutarse en contenedores Docker para facilitar despliegue y mantenimiento.

---

# 4. Reglas de negocio (RB)

RB-01  
El precio final del helado se calcula como precio base + toppings + tamaño.

RB-02  
Los tamaños disponibles son únicamente 12 oz, 14 oz y 16 oz.

RB-03  
Un pedido debe contener al menos un producto.

RB-04  
El administrador es el único que puede crear o editar productos.

RB-05  
Un helado debe tener mínimo un sabor seleccionado.

---

# 5. Casos de uso

---

CU-01: Consultar menú de helados

Actor principal: Cliente

Propósito: Permitir al cliente ver los productos disponibles.

Disparador: El usuario entra a la sección menú.

Precondiciones  
El sistema debe estar conectado a la base de datos.

Postcondiciones  
El usuario visualiza los productos disponibles.

Flujo principal

1 El usuario abre la app  
2 El sistema consulta los productos en la base de datos  
3 El sistema muestra la lista de helados  
4 El usuario visualiza imagen, nombre y precio

Excepciones

E1 Error de conexión  
El sistema muestra mensaje de error.

---

CU-02: Personalizar helado

Actor principal: Cliente

Propósito: Configurar el helado según preferencias.

Disparador: El usuario selecciona un helado.

Precondiciones

Producto disponible en el menú.

Postcondiciones

Helado personalizado listo para agregar al carrito.

Flujo principal

1 El usuario selecciona un helado  
2 El sistema muestra opciones de personalización  
3 El usuario selecciona sabor  
4 El usuario selecciona toppings  
5 El usuario selecciona tamaño  
6 El sistema calcula el precio final

Excepciones

A1 No selecciona sabor  
El sistema solicita seleccionar uno.

---

CU-03: Confirmar pedido

Actor principal: Cliente

Propósito: Registrar un pedido en el sistema.

Disparador: El usuario presiona confirmar pedido.

Precondiciones

El carrito contiene productos.

Postcondiciones

Pedido registrado en la base de datos.

Flujo principal

1 El usuario abre el carrito  
2 El sistema muestra productos y total  
3 El usuario confirma el pedido  
4 El sistema guarda el pedido  
5 El sistema confirma la operación

Excepciones

E1 Error en base de datos  
El sistema informa error y permite reintentar.

---

# 6. Trazabilidad de requerimientos

| Requerimiento | Caso de uso asociado | Estado   |
| ------------- | -------------------- | -------- |
| RF-01         | CU-01                | Definido |
| RF-02         | CU-02                | Definido |
| RF-03         | CU-02                | Definido |
| RF-04         | CU-02                | Definido |
| RF-05         | CU-03                | Definido |
| RF-06         | CU-03                | Definido |
| RF-07         | CU-03                | Definido |
| RF-08         | CU-03                | Definido |
| RF-09         | CU-03                | Definido |
| RF-10         | CU-01                | Definido |
