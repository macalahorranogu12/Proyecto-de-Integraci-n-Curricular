Arquitectura y funcionalidades iniciales.
A continuación, la arquitectura se explicara mediante un diagrama UML,
como se puede evidenciar en la figura 1.

Diagram UML

Nota: como se puede evidenciar, El Usuario interactúa primero con el Módulo
de Usuarios para registrarse o iniciar sesión. Una vez autenticado, puede
7
acceder al Módulo de Ingresos y Gastos, donde guarda y clasifica todos sus
movimientos financieros. El Módulo de Presupuesto permite fijar un límite
mensual y comparar automáticamente los gastos contra ese presupuesto. Con
base en la información de ingresos, gastos y presupuestos, el Módulo de
Reportes y Estadísticas genera gráficos y reportes exportables. Todo esto se
almacena en la Base de Datos (PostgreSQL). La API Backend (Go + Gin)
coordina la comunicación entre el usuario, los módulos y la base de datos.
Creación propia.
<img width="817" height="462" alt="image" src="https://github.com/user-attachments/assets/3aed09db-1a30-4a8e-bce8-06c7297b3455" />


 <img width="282" height="559" alt="image" src="https://github.com/user-attachments/assets/6cc8f1bb-f4ed-4d17-bfbb-cbb0369c29bc" />
internal/usuarios/

Contiene todo lo relacionado con registro, login y perfil.

Los archivos definen estructuras (structs) y funciones (methods) del módulo.

Ejemplo:

usuario.go: estructura Usuario con nombre, correo, contraseña.

autenticacion.go: funciones RegistrarUsuario(), Login().

perfil.go: editar datos del perfil, cambiar contraseña, etc.

 internal/ingresosgastos/

Registra ingresos y gastos, los clasifica y guarda.

ingreso.go y gasto.go definen estructuras con campos: monto, fecha, descripción.

categoria.go maneja categorías (alimentación, transporte, etc.).

service.go contiene la lógica de negocio (por ejemplo, “registrar nuevo gasto”).

 internal/presupuesto/

Crea presupuestos mensuales y los compara con los gastos reales.

presupuesto.go: estructura del presupuesto (límite mensual, categoría, fecha).

comparador.go: analiza si los gastos superan el presupuesto.

service.go: funciones para calcular balances y mostrar advertencias.

internal/reportes/

Genera reportes de ingresos, gastos y presupuestos.

reportes.go: define la estructura de reporte (periodo, totales).

graficas.go: genera los gráficos (barras, pastel, líneas) usando alguna librería compatible con Go.

exportador.go: exporta los reportes a PDF o Excel.

service.go: controla el flujo de generación y exportación.
