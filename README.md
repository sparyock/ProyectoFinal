# Gestión de Gimnasio
##Necesidad 
Implementar un sistema para gestionar de forma eficiente las membresías de los clientes, incluyendo la creación de diferentes planes de pago, la renovación automática de membresías, el control de morosidad y la generación de informes sobre la base de datos de clientes.

## Requerimientos Funcionales

1.RF 1 Registro de clientes: 
Ingresar datos personales, contacto, planes de pago e historial médico.

2.RF 2 Gestión de Pagos y Facturación: 
debe tener como tal la generación de facturas y recibos y así como tal la gestión de membresías (mensuales, trimestrales y anuales) añadiendo cualquier descuento, así mismo debe permitir el pago por distintas modalidades como tarjetas de crédito, débito y pagos en línea.

3.RF 3 Renovación Automática de Membresías:
El sistema debe ser capaz de renovar automáticamente las membresías de los clientes según el plan seleccionado.

4. RF 4 Control de morosidad: 
Generar y notificar a los clientes con pagos atrasados.


## Requerimientos No Funcionales

1. RNF: Seguridad
Proteger la información personal y financiera de los clientes.
2. RNF: Rendimiento
El sistema debe ser rápido y eficiente para atender a un gran número de clientes
3. RNF: Mantenimiento
El sistema debe ser fácil de mantener y actualizar.
4. RNF: Disponibilidad:
El sistema debe estar disponible las 24 horas del día, los 7 días de la semana, para que los clientes puedan acceder a sus membresías y realizar pagos en cualquier momento.


 #### Diseñar Base de Datos

### Tabla: Clientes
| id | nombre   | apellido   | teléfono       | dirección      | documento  |
|----|-------------|--------------|------------------|-----------------|------------------|
| 1  | Yeison    | Scarpeta | 3205788679 | cr 5#6-30     | 1007255220|
| 2  |Sebastian| Andres    | 3585885588 | cr 7#6-40     | 1008558221|
| 3  | sergio     | Calderon | 8585858585 | cr 8#6-25     | 104495564  |

---------------------------------------------------------------------------------------------
### Tabla: Planes
| Id        |  Costo       |    Descripción     |          Tipo                 |
|----------|---------------|-----------------------|-----------------------------|
|   1       |    50.000   |      mensual        |    GOLD                    |
|   2       |    30.000   |       trimestral      |     PLATINUM           |
|   3       |    25000    |    semestral        |        BASICO             |
|  2        |    35000    |      anual             |  GOLD                      |

### Tabla: Membresías
| membresia_id | cliente_id| plan_id  |fecha_inicio| fecha_fin   |estado       |
|---------------------|-------------|------------|-----------------|---------------|---------------|
|  1025350         |       1       | 365       | 2023-04-15  |2023-05-15 |  activo       |
|  1052555         |        2      |  524      | 2023-04-18  |2023-05-18 |  pendiente |
|   854221          |       3       |   754     | 2023-04-24  |2023-05-15|   activo        |
|   815052          |        4      |   747     | 2023-06-12  |2023-07-15|   cancelado |
|  442222           |       5       | 751       |2023-07-29   |2023-08-15|   activo        |
|   452632          |        6      | 652       |  2023-08-25 |2023-09-15|   pendiente |
### Tabla: Facturas
  | factura_id | cliente_id   | fecha_emision | monto_total | descuento|metodo_pago | estado  | 
  |---------------|----------------|---------------------|-----------------|---------------|-----------------------|------------| 
  |           1     |        1         |    2023-01-10     |    100.00       |    10.00     |tarjeta crédito | pagado   | 
  |           2     |        2         |    2023-02-05     |    150.00      |   15.00    |    débito          |pagado     | 
  |           3     |        3         |    2023-03-20     |    200.00        |   20.00     |    online          |pendiente| 
  |           4     |        4         |    2023-04-15      |    250.00       |   25.00    |tarjeta crédito |atrasado    | 
  |           5     |        5         |    2023-05-10      |   300.00        |  30.00     |     débito         |atrasado    | 



### Tabla: Pagos
Aquí tienes una tabla de pagos con datos aleatorios:

### Tabla: Pagos
| pago_id | factura_id | fecha_pago | monto_pagado  |metodo_pago                     |
|------------|---------------|------------------|----------------------|------------------------------------|
|   1          | 1001         | 2024-05-10 |       250.00         |Tarjeta de Crédito              |
| 2            | 1002         | 2024-05-11 |         150.75       |       PayPal                         |
| 3            | 1003         | 2024-05-12 |         300.50       | Transferencia Bancaria     |
| 4            | 1004         | 2024-05-13 |         450.00       | Efectivo                             |
| 5            | 1005         | 2024-05-14 |         220.25       | Tarjeta de Débito               |
| 6            | 1006         | 2024-05-15 |         330.10       | Cheque                              |
| 7            | 1007         | 2024-05-16 |         125.00       | PayPal                               |
| 8            | 1008         | 2024-05-17 |           600.00     | Tarjeta de Crédito              |
| 9            | 1009         | 2024-05-18 |           199.99     | Transferencia Bancaria     |
| 10          | 1010         | 2024-05-19 |           480.50     | Efectivo                             |



### Tabla: Notificaciones

| notificacion_id | cliente_id | tipo       | mensaje                                                         | fecha_envio |
|-----------------|------------|------------|-----------------------------------------------------------------|-------------|
| 1               | 1          | renovación | Su membresía está próxima a renovarse. Por favor, revise su plan.| 2023-01-15  |
| 2               | 2          | mora       | Su pago está atrasado. Por favor, póngase al día con su factura. | 2023-02-10  |
| 3               | 3          | renovación | Su membresía está próxima a renovarse. Por favor, revise su plan.| 2023-03-25  |
| 4               | 4          | mora       | Su pago está atrasado. Por favor, póngase al día con su factura. | 2023-04-20  |
| 5               | 5          | renovación | Su membresía está próxima a renovarse. Por favor, revise su plan.| 2023-05-15  |
| 6               | 6          | mora       | Su pago está atrasado. Por favor, póngase al día con su factura. | 2023-06-10  |
| 7               | 7          | renovación | Su membresía está próxima a renovarse. Por favor, revise su plan.| 2023-07-25  |
| 8               | 8          | mora       | Su pago está atrasado. Por favor, póngase al día con su factura. | 2023-08-20  |
| 9               | 9          | renovación | Su membresía está próxima a renovarse. Por favor, revise su plan.| 2023-09-15  |
| 10              | 10         | mora       | Su pago está atrasado. Por favor, póngase al día con su factura. | 2023-10-10  |





## Índices y Claves Foráneas
- `FK_Clientes_Planes`: `Membresias.plan_id` referencia a `Planes.plan_id`
- `FK_Membresias_Clientes`: `Membresias.cliente_id` referencia a `Clientes.cliente_id`
- `FK_Facturas_Clientes`: `Facturas.cliente_id` referencia a `Clientes.cliente_id`
- `FK_Pagos_Facturas`: `Pagos.factura_id` referencia a `Facturas.factura_id`
- `FK_Notificaciones_Clientes`: `Notificaciones.cliente_id` referencia a `Clientes.cliente_id`



### Base de datos script

```sql

-- Crear la base de datos
CREATE DATABASE IF NOT EXISTS GestionClientes;

-- Usar la base de datos
USE GestionClientes;

-- Crear la tabla Clientes
CREATE TABLE Clientes (
    cliente_id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    apellido VARCHAR(100) NOT NULL,
    fecha_nacimiento DATE NOT NULL,
    correo_electronico VARCHAR(100) NOT NULL,
    telefono VARCHAR(15) NOT NULL,
    direccion VARCHAR(255) NOT NULL,
    historial_medico TEXT
);

-- Crear la tabla Planes
CREATE TABLE Planes (
    plan_id INT AUTO_INCREMENT PRIMARY KEY,
    nombre_plan VARCHAR(50) NOT NULL,
    precio DECIMAL(10, 2) NOT NULL,
    descripcion TEXT
);

-- Crear la tabla Membresias
CREATE TABLE Membresias (
    membresia_id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT NOT NULL,
    plan_id INT NOT NULL,
    fecha_inicio DATE NOT NULL,
    fecha_fin DATE NOT NULL,
    estado VARCHAR(20) NOT NULL,
    FOREIGN KEY (cliente_id) REFERENCES Clientes(cliente_id),
    FOREIGN KEY (plan_id) REFERENCES Planes(plan_id)
);

-- Crear la tabla Facturas
CREATE TABLE Facturas (
    factura_id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT NOT NULL,
    fecha_emision DATE NOT NULL,
    monto_total DECIMAL(10, 2) NOT NULL,
    descuento DECIMAL(10, 2),
    metodo_pago VARCHAR(50) NOT NULL,
    estado VARCHAR(20) NOT NULL,
    FOREIGN KEY (cliente_id) REFERENCES Clientes(cliente_id)
);

-- Crear la tabla Pagos
CREATE TABLE Pagos (
    pago_id INT AUTO_INCREMENT PRIMARY KEY,
    factura_id INT NOT NULL,
    fecha_pago DATE NOT NULL,
    monto_pagado DECIMAL(10, 2) NOT NULL,
    metodo_pago VARCHAR(50) NOT NULL,
    FOREIGN KEY (factura_id) REFERENCES Facturas(factura_id)
);

-- Crear la tabla Notificaciones
CREATE TABLE Notificaciones (
    notificacion_id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT NOT NULL,
    tipo VARCHAR(50) NOT NULL,
    mensaje TEXT NOT NULL,
    fecha_envio DATE NOT NULL,
    FOREIGN KEY (cliente_id) REFERENCES Clientes(cliente_id)
);
[ver](https://trello.com/b/7eZDcz8A/proyecto-analisis)
