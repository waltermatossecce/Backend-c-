
# 🖥️ API REST – Gestión de Pedidos (.NET 7)

Backend RESTful desarrollado en **.NET 7 Web API** con enfoque en **Clean Architecture**, para dar soporte a la app Android de gestión de pedidos. Utiliza patrones modernos como **CQRS con MediatR**, acceso a datos con **Dapper**, y validaciones con **FluentValidation**.

---

## 🌐 API REST – .NET 7

### 🛠️ Tecnologías y Principios

- ✅ **.NET 7 Web API**
- ✅ **Clean Architecture**
- ✅ **Dapper** para acceso rápido a datos
- ✅ **CQRS** con MediatR
- ✅ **AutoMapper** y **FluentValidation**
- ✅ **SQL Server** con Stored Procedures
- ✅ **Swagger** para documentación
- ✅ **Inyección de dependencias**

---

### 📂 Estructura del Backend

```
Gestion/
├── Gestion.Api/             → API Web (Controllers, Middlewares)
├── Gestion.Application/     → UseCases, Commands, Queries
├── Gestion.Domain/          → Entidades e interfaces
├── Gestion.Persistence/     → Repositorios e infraestructura
└── Gestion.Utilities/       → Constantes y utilidades
```

---

### ⚙️ Configuración

1. Asegúrate de tener SQL Server corriendo.

2. Crea la base de datos `PruebaTecnicaMobile` y agrega los siguientes stored procedures:

   - `uspPedidosList`
   - `uspPedidosById`
   - `uspRegistrarPedido`
   - `uspActualizarPedido`
   - `uspEliminarPedido`

3. Configura tu cadena de conexión en `appsettings.json`:

```json
"ConnectionStrings": {
  "GestionConnection": "Data Source=localhost\SQLEXPRESS;Database=PruebaTecnicaMobile;User=sa;Password=sql;TrustServerCertificate=True"
}
```

4. Ejecuta el backend:

```bash
dotnet build
dotnet run --project Gestion.Api
```

---

## 📡 Endpoints Expuestos

| Método | Ruta                        | Descripción                |
|--------|-----------------------------|----------------------------|
| GET    | /api/Pedidos                | Obtener todos los pedidos |
| GET    | /api/Pedidos/{id}           | Obtener pedido por ID     |
| POST   | /api/Pedidos/Register       | Crear nuevo pedido        |
| PUT    | /api/Pedidos/EditarPedido   | Editar un pedido existente|
| DELETE | /api/Pedidos/Remove/{id}    | Eliminar un pedido        |

---

## 🔐 Seguridad y Configuración CORS

- CORS habilitado para permitir llamadas desde la app móvil.
- `NetworkSecurityConfig` en Android habilita tráfico HTTP si estás en red local.

---

## ✨ Valor Agregado

- Filtros dinámicos en listado.
- Exportación a PDF y Excel.
- Notificaciones visuales tras operaciones clave.
- Sincronización en background.
- Arquitectura limpia y desacoplada en backend.
- Adaptación para entornos sin conexión.

---

## ✍️ Autor

**Walter Matos**

---
