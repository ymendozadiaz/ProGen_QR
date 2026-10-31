================================================================================
                        PROGEN QR - SISTEMA DE GESTIÓN
                                Versión 3.0
================================================================================

                          MANUAL DE INSTALACIÓN Y USO
================================================================================


1. DESCRIPCIÓN GENERAL
================================================================================

Progen QR es un sistema de gestión empresarial integral diseñado para 
optimizar los procesos de inventario, facturación, control de clientes, 
proveedores, costos y generación de códigos QR.

El programa permite:
  ✅ Registrar productos y equipos con código QR único
  ✅ Generar facturas con múltiples productos y cálculo automático de totales
  ✅ Control de pagos y adeudos por cliente
  ✅ Gestión de proveedores con logo personalizado
  ✅ Registro de costos y materiales (compras)
  ✅ Reportes financieros y gráficos estadísticos
  ✅ Cálculo de impuestos (módulo ONAT)
  ✅ Generación de PDF de facturas con QR, logo y firmas
  ✅ Exportación a Excel de todos los módulos
  ✅ Sistema de licencias para uso autorizado


2. REQUISITOS DEL SISTEMA
================================================================================

- Sistema operativo: Windows 7/8/10/11 (recomendado), Linux o macOS (con adaptaciones)
- Python 3.8 o superior (si se ejecuta desde código fuente)
- Espacio en disco: mínimo 200 MB
- Memoria RAM: 2 GB recomendado
- Conexión a internet: solo para activación de licencia (opcional)


3. INSTALACIÓN
================================================================================

3.1. Instalación desde código fuente (para desarrolladores)

   1. Clonar o descargar el proyecto en una carpeta.
   2. Abrir una terminal en la carpeta del proyecto.
   3. Instalar las dependencias:
      
      pip install -r requirements.txt
      
   4. Ejecutar el programa:
      
      python main.py
      

3.2. Instalación desde ejecutable (para usuarios finales)

   1. Descargar el archivo ProgenQR.exe desde el enlace proporcionado.
   2. Colocar el ejecutable en una carpeta de su elección.
   3. Hacer doble clic en el archivo para ejecutarlo.
   4. La primera vez, el programa creará automáticamente la base de datos y solicitará activación.


4. ACTIVACIÓN DE LICENCIA (PRIMER USO)
================================================================================

Al ejecutar el programa por primera vez, aparecerá una ventana de activación.

PASOS PARA ACTIVAR:

   1. La ventana mostrará un ID de máquina (ejemplo: "ABCD-1234-EFGH").
   2. Copie ese ID y envíelo a su proveedor (desarrollador).
   3. El desarrollador le generará una clave de activación.
   4. Ingrese la clave en el campo correspondiente y haga clic en "Activar".
   5. El programa guardará la licencia y no volverá a solicitarla.

IMPORTANTE: La licencia tiene una fecha de expiración. Cuando expire, deberá 
solicitar una nueva clave al desarrollador.


5. ACCESO AL SISTEMA
================================================================================

Al iniciar el programa, aparecerá la pantalla de LOGIN.

Credenciales por defecto (Administrador):
  Usuario: admin
  Contraseña: 12345678

Recomendación: Cambie la contraseña del usuario admin inmediatamente después 
del primer inicio (desde el módulo "Registro").

Para usuarios normales, el administrador debe registrarlos desde el mismo módulo.


6. MÓDULOS DEL PROGRAMA (Menú lateral)
================================================================================

6.1. INICIO - Generador de QR
────────────────────────────────────────────────────────────────────────────────
Este módulo permite gestionar productos (PCs, equipos) y generar sus códigos QR.

Funciones:
  - Agregar: Registra un nuevo producto con sus especificaciones.
  - Actualizar: Modifica los datos de un producto existente.
  - Eliminar: Elimina un producto de la base de datos.
  - Generar QR: Crea un código QR con los datos del producto seleccionado.
  - Exportar: Exporta la lista de productos a Excel.
  - Sincronizar: Importa automáticamente los datos desde el módulo "Propiedades".


6.2. PROPIEDADES - Información de Hardware
────────────────────────────────────────────────────────────────────────────────
Obtiene automáticamente las especificaciones del equipo (CPU, RAM, motherboard, 
disco duro, sistema operativo, etc.) y las guarda en la base de datos.

Funciones:
  - Generar Reporte: Escanea el hardware actual y lo guarda.
  - Exportar BD: Exporta todos los registros de hardware a Excel.
  - Sincronizar QR: Actualiza la tabla de productos con los datos de propiedades.


6.3. FACTURACIÓN - Gestión de facturas
────────────────────────────────────────────────────────────────────────────────
Módulo principal para la creación y gestión de facturas.

Características:
  - Datos de factura: N° Factura, Cliente, Cuenta, Servicio.
  - Productos: Agregue hasta 5 productos (ampliable) con cantidad y precio unitario.
  - Cálculo automático: Subtotal y total general se calculan en tiempo real.
  - Pagado y Adeudo: Permite registrar pagos parciales.
  - Proveedor y Cliente: Se asocian desde las tablas correspondientes.
  - Botones:
    • Agregar Factura: Guarda la factura con todos sus productos.
    • Actualizar: Modifica una factura existente.
    • Eliminar: Elimina la factura y sus detalles (en cascada).
    • Generar QR: Crea un código QR con los datos de la factura.
    • Generar PDF: Crea un PDF profesional con logo, QR, firma y sello.
    • Importar Excel: Carga facturas desde un archivo Excel.
    • Exportar Excel: Exporta todas las facturas a Excel.
    • Reporte Vencidas: Muestra facturas con más de 30 días sin pago.
    • Ver Gráficos: Muestra gráficos de facturas pagadas vs con adeudo.

Resumen de saldos: Muestra en tiempo real los adeudos por cliente y por mes.


6.4. ONAT - Cálculo de Impuestos
────────────────────────────────────────────────────────────────────────────────
Calcula los impuestos mensuales basados en el total facturado.

Reglas de cálculo:
  - Impuesto del 10% sobre el total facturado del mes.
  - Impuesto del 5% sobre el excedente de (Total facturado - 3260) si es positivo.

Funciones:
  - Calcular Mes: Calcula los impuestos para el mes seleccionado.
  - Registrar Pago: Guarda el pago de impuestos en el histórico.
  - Exportar Histórico: Exporta todos los registros de pago a Excel.


6.5. PROVEEDORES - Gestión de proveedores
────────────────────────────────────────────────────────────────────────────────
Permite registrar y gestionar los proveedores de la empresa.

Campos:
  - Nombre (obligatorio)
  - NIT
  - No. Cuenta Fiscal
  - Dirección
  - Sucursal Bancaria
  - Código Postal
  - Email
  - Logo (seleccionar imagen de 95x95 px recomendado)

El logo se mostrará en el módulo de facturación y en los PDFs de factura.


6.6. CLIENTES - Gestión de clientes
────────────────────────────────────────────────────────────────────────────────
Permite registrar y gestionar los clientes.

Campos:
  - Cliente (obligatorio)
  - Dirección
  - Sucursal Bancaria
  - No. Cuenta
  - Código REEUP
  - NIT

Al seleccionar un cliente en facturación, se rellenan automáticamente el nombre 
y el número de cuenta.


6.7. COSTOS - Registro de costos y compras
────────────────────────────────────────────────────────────────────────────────
Registro detallado de costos operativos y compras de materiales.

Campos:
  - Fecha
  - Proveedor
  - Materiales
  - Mercancía/Ventas
  - Combustible
  - Energía
  - Salarios
  - Pago Arrendamiento
  - Total Gastos (se calcula automáticamente)
  - Total Pagado

Funciones:
  - Agregar, Actualizar, Eliminar
  - Filtrar por fecha y proveedor
  - Mostrar Resumen (ventana con totales y gráfico de barras)
  - Exportar a Excel


6.8. REPORTES - Análisis de datos
────────────────────────────────────────────────────────────────────────────────
Módulo de análisis con cuatro pestañas:

  1. Mensual: Muestra facturas de un mes específico con gráfico.
  2. Anual: Resumen mensual con gráfico de barras doble.
  3. Por Cliente: Facturas de un cliente específico con resumen.
  4. Adeudos/Pagados: Resumen de adeudos por cliente con gráfico de torta.


6.9. REGISTRO - Gestión de usuarios
────────────────────────────────────────────────────────────────────────────────
Permite al administrador crear nuevos usuarios y cambiar contraseñas.

Funciones:
  - Registrar usuario: Crea un nuevo usuario con rol "user".
  - Buscar y Cambiar Contraseña: Modifica la contraseña de un usuario existente.


6.10. CONFIGURACIÓN - Personalización del tema
────────────────────────────────────────────────────────────────────────────────
Permite cambiar:
  - Modo de apariencia: Oscuro o Claro.
  - Tema de color: Azul, Verde, Morado, Rojo o Naranja.

Los cambios se guardan en el archivo config.json y se aplican al reiniciar.


6.11. ACERCA DE - Información del programa
────────────────────────────────────────────────────────────────────────────────
Muestra información sobre el desarrollador, versión, contacto y derechos de autor.


7. FLUJO DE TRABAJO BÁSICO (RECOMENDADO)
================================================================================

PASO 1: Configuración inicial
  - Registrar proveedores (módulo Proveedores)
  - Registrar clientes (módulo Clientes)
  - Registrar productos (módulo Inicio)

PASO 2: Generar facturación
  - Crear factura (módulo Facturación)
  - Seleccionar cliente y proveedor
  - Agregar productos con cantidades y precios
  - Registrar pago (parcial o total)
  - Guardar factura

PASO 3: Reportes y cierres
  - Consultar saldos por cliente (módulo Facturación)
  - Generar reportes mensuales/anuales (módulo Reportes)
  - Calcular impuestos ONAT (módulo ONAT)
  - Exportar datos a Excel para auditorías


8. ATAJOS DE TECLADO
================================================================================

  Ctrl+1  →  Ir a Inicio
  Ctrl+2  →  Ir a Propiedades
  Ctrl+3  →  Ir a Facturación
  Ctrl+4  →  Ir a ONAT
  Ctrl+5  →  Ir a Proveedores
  Ctrl+6  →  Ir a Clientes
  Ctrl+7  →  Ir a Costos
  Ctrl+8  →  Ir a Reportes
  Ctrl+9  →  Ir a Registro
  Ctrl+Q  →  Salir de la aplicación


9. SOLUCIÓN DE PROBLEMAS COMUNES
================================================================================

PROBLEMA: El programa no inicia y muestra error de licencia.
SOLUCIÓN: Asegúrese de que el archivo licencia.dat esté en la misma carpeta 
          que el ejecutable. Si no, solicite una nueva licencia.

PROBLEMA: El logo del proveedor no se muestra en el PDF.
SOLUCIÓN: Verifique que la ruta del logo sea correcta y que el archivo exista. 
          El logo debe estar en formato PNG o JPG y no superar los 95x95 px.

PROBLEMA: No se pueden agregar productos en la factura.
SOLUCIÓN: Asegúrese de llenar los campos "Producto", "Cantidad" y "Precio Unitario".
          La cantidad y el precio deben ser números positivos.

PROBLEMA: El total de la factura no coincide con la suma de productos.
SOLUCIÓN: Verifique que todos los productos tengan cantidad y precio válidos.
          El total se recalcula automáticamente al modificar cualquier campo.

PROBLEMA: Error al exportar a Excel.
SOLUCIÓN: Asegúrese de tener instalado pandas y openpyxl. Si usa el ejecutable,
          verifique que no haya archivos de Excel abiertos al exportar.

PROBLEMA: El gráfico de resumen de costos no se muestra.
SOLUCIÓN: Asegúrese de tener matplotlib instalado. Si usa el ejecutable,
          verifique que el archivo no esté dañado.


10. CONTACTO Y SOPORTE
================================================================================

Desarrollador: Yosbel Mendoza Diaz
Contacto: [Tu email]
Dirección: Calle 10 Edif. 7 Apto. 14, Morón, Cuba
Año: 2024

Para soporte técnico, reporte de errores o solicitud de nuevas funcionalidades,
por favor contacte al desarrollador a través del correo electrónico.


11. LICENCIA Y DERECHOS DE AUTOR
================================================================================

Este software es propiedad de su desarrollador. Queda prohibida su reproducción, 
distribución o modificación sin autorización expresa. El programa cuenta con un 
sistema de licencias que garantiza su uso autorizado.

© 2024 Progen QR - Todos los derechos reservados.

================================================================================
                      ¡Gracias por usar Progen QR!
==============================================================================