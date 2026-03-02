🚀 Folan 3D - Sistema de Gestión de Impresión

Folan 3D es una plataforma integral diseñada para automatizar el flujo de trabajo de un emprendimiento de impresión 3D. Este sistema permite gestionar el catálogo de productos, controlar pedidos y supervisar procesos de impresión en tiempo real mediante una arquitectura de servicios web.

🛠️ Tecnologías Utilizadas
Lenguaje: Go (Golang) - Backend robusto y concurrente.
Frontend: HTML5, CSS3 (Glassmorphism UI) y JavaScript (Fetch API).
Comunicación: Servicios Web REST con serialización de datos en JSON.
Concurrencia: Uso de Goroutines y WaitGroups/Mutex para simular procesos de impresión asíncronos.

📡 Servicios Web (Endpoints)
El sistema implementa 8 servicios web fundamentales para cumplir con los requisitos de la Unidad 4:

Servicio      Método  Descripción
/productos    GET     Obtiene el catálogo completo de piezas 3D.
/productos    POST    Registra una nueva pieza en el sistema.
/productos    PUT     Actualiza el precio de una pieza existente.
/productos    DELETE  Elimina una pieza del catálogo mediante ID.
/inventario   GET     Consulta el stock disponible de materiales (PLA/Resina).
/inventario   PUT     Recarga el material del inventario.
/pedidos      GET     Lista todos los pedidos y su estado de impresión.
/imprimir     POST    Inicia el proceso de impresión concurrente de una pieza.

🧵 Manejo de Concurrencia (Unidad 3)
Uno de los pilares de este proyecto es la capacidad de gestionar múltiples impresiones simultáneamente sin detener el servidor.
Al activar el servicio /imprimir, el sistema lanza una Goroutine que simula el tiempo de fabricación.
El estado del pedido cambia de Pendiente a Imprimiendo y finalmente a Finalizado.
Gracias al modelo de concurrencia de Go, el usuario puede seguir navegando y agregando productos mientras las "impresoras virtuales" trabajan en segundo plano.


💻 Instalación y Ejecución
Clonar el repositorio:

Bash
git clone https://github.com/LuchoAnd/Programacion_Orientada_a_Objetos_UIDE/blob/main/Final.git

Ejecutar el servidor de Go:
Bash
go run final.go

Abrir el Frontend:
Haz doble clic en el archivo index.html o usa la extensión Live Server de VS Code.

📝 Conclusiones y Reflexión

El desarrollo para Folan 3D permitió aplicar conceptos de programación:

Desacoplamiento: La separación de Frontend y Backend mediante una API permite que el sistema sea escalable.
CORS: Se gestionaron políticas de seguridad para permitir la comunicación entre el navegador y el servidor local.
Seguridad: Como estudiante de Ciberseguridad, se implementó el control de concurrencia mediante sync.Mutex para evitar la corrupción de datos.
