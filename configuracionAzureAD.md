# 📝 Registro de una Nueva Aplicación en Azure Active Directory ahora renombrado como **Microsoft Entra ID**

Registrar una aplicación en Azure AD ahora renombrado como **Microsoft Entra ID** te permite autenticar usuarios, acceder a APIs protegidas (como Microsoft Graph), y definir permisos personalizados para tu app.

---

## 📍 Requisitos Previos

- Tener una cuenta con permisos para registrar aplicaciones (por ejemplo, **Application Administrator** o **Global Administrator**).
- Acceso al portal de Azure: [https://portal.azure.com](https://portal.azure.com)

---

## ✅ Paso a Paso para Registrar una Aplicación

### 1. Iniciar sesión en Azure

1. Abre [https://portal.azure.com](https://portal.azure.com)
2. Inicia sesión con tu cuenta de Microsoft 365 o Azure AD.

---

### 2. Acceder a Azure Active Directory ahora renombrado como **Microsoft Entra ID**

1. En el menú lateral, haz clic en **Azure Active Directory** ahora renombrado como **Microsoft Entra ID**.
2. Luego selecciona **Registros de aplicaciones (App registrations)**.

---

### 3. Registrar una nueva aplicación

1. Haz clic en **+ Nueva aplicación de registro** (New registration).
2. Completa los campos:

   - **Nombre**: Un nombre descriptivo para tu aplicación.
   - **Tipos de cuenta admitidos**:
     - Solo cuentas en este directorio (single tenant)
     - Cuentas en cualquier directorio (multi-tenant)
     - Cuentas personales de Microsoft (como Outlook.com)
   - **URI de redirección (opcional)**:
     - Solo necesario si estás desarrollando una app web o móvil.
     - Ejemplo: `https://localhost:3000/auth/callback`

3. Haz clic en **Registrar**.

---

### 4. Revisar el resumen de la aplicación

Una vez registrada, se mostrará la página principal con:

- **Application (client) ID**
- **Directory (tenant) ID**
- **Object ID**
- **Nombre de la aplicación**

Guarda estos valores para configurar tu app cliente.

---

### 5. (Opcional) Configurar URI de redirección adicional

1. Ve a **Autenticación (Authentication)** en el menú lateral de la app.
2. Agrega más URIs de redirección si es necesario.
3. Habilita flujos como "Access tokens", "ID tokens" si estás usando OAuth 2.0 o OpenID Connect.

---

### 6. (Opcional) Configurar permisos de API

1. Ve a **Permisos de API (API permissions)**.
2. Haz clic en **+ Agregar un permiso (Add a permission)**.
3. Selecciona la API (por ejemplo, **Microsoft Graph**).
4. Escoge el tipo de permiso:
   - **Delegados**: Requieren un usuario autenticado.
   - **Aplicación**: No requieren usuario (ideal para demonios o servicios backend).
5. Haz clic en **Agregar permisos**.
6. (Si aplica) Haz clic en **Conceder consentimiento del administrador**.

---

### 7. (Opcional) Crear un secreto de cliente (Client Secret)

1. Ve a **Certificados y secretos (Certificates & secrets)**.
2. Haz clic en **+ Nuevo secreto de cliente**.
3. Asigna una descripción y elige una duración.
4. Guarda el **valor secreto** de inmediato (solo se muestra una vez).

---

## 📌 Resultado

Tu aplicación ya está registrada en Azure AD y lista para usar con autenticación, autorización y consumo de APIs seguras.

---

## 🧠 Tips

- Usa el **Microsoft Authentication Library (MSAL)** para autenticar usuarios desde tu app.
- Si vas a usar la app en producción, configura correctamente los **URI de redirección seguros** y habilita **autenticación multifactor**.
- Consulta [https://learn.microsoft.com/es-es/azure/active-directory/develop/](https://learn.microsoft.com/es-es/azure/active-directory/develop/) para ejemplos por lenguaje y plataforma.
