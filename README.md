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
