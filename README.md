# 🧠 Conceptos Clave para el Uso de Azure Active Directory (Azure AD)

Azure Active Directory (Azure AD), ahora renombrado como **Microsoft Entra ID**, es el servicio de administración de identidades y acceso basado en la nube de Microsoft. Permite controlar el acceso a recursos internos y externos de forma segura.

---

## 📌 1. ¿Qué es Azure AD?

Azure AD es un servicio de identidad basado en la nube que proporciona:

- Autenticación (Inicio de sesión único, multifactor)
- Autorización (Control de acceso a recursos)
- Administración de usuarios y grupos
- Integración con aplicaciones (SaaS, on-premises, personalizadas)

---

## 🧩 2. Componentes Clave

### 👤 Usuarios

Identidades individuales que pueden representar personas, dispositivos o servicios.

- Tipos: Cuentas organizativas, cuentas de invitados (externos), cuentas de servicio.

### 👥 Grupos

Permiten gestionar el acceso de múltiples usuarios a recursos y aplicaciones.

- Tipos: Grupos de seguridad, grupos de Microsoft 365.
- Admisión: Manual o dinámica.

### 🛡️ Roles

Determinan los permisos que tiene un usuario dentro de Azure AD y otras plataformas (Azure, Microsoft 365).

- Roles integrados (Ej. **Global Administrator**, **User Administrator**)
- Roles personalizados (en planes Premium)

### 🌐 Inquilino (Tenant)

Representa la organización dentro de Azure AD. Es una instancia dedicada del servicio.

---

## 🔐 3. Autenticación y Seguridad

### 🔑 Inicio de Sesión Único (SSO)

Permite a los usuarios iniciar sesión una sola vez para acceder a múltiples aplicaciones.

### 📲 Autenticación Multifactor (MFA)

Solicita un segundo factor además de la contraseña (ej. App Authenticator, SMS, FIDO2).

### 🧠 Políticas de Acceso Condicional

Permiten controlar el acceso según condiciones específicas:

- Ubicación geográfica
- Estado del dispositivo
- Rol del usuario
- Aplicación solicitada

---

## 🧬 4. Integraciones

### ☁️ Aplicaciones SaaS

Azure AD se puede integrar con miles de aplicaciones SaaS (Ej. Salesforce, ServiceNow, Google Workspace).

### 🏢 Aplicaciones On-premises

Se puede extender Azure AD a aplicaciones locales mediante **Azure AD Application Proxy** o **AD Federation Services (AD FS)**.

### ⚙️ Proveedores de Identidad Externos

Azure AD puede federarse con otros IDPs como Google, Facebook, o ADFS.

---

## 🔄 5. Sincronización de Identidades

### 🔁 Azure AD Connect

Herramienta para sincronizar usuarios, contraseñas y atributos desde un Active Directory local hacia Azure AD.

- **Password Hash Sync**
- **Pass-through Authentication**
- **Federación con ADFS**

---

## 📊 6. Licenciamiento

Azure AD tiene distintos niveles de servicio:

- **Free**: Básico, ideal para pruebas o pequeñas organizaciones.
- **Office 365 Apps**: Incluido con licencias de Microsoft 365.
- **Premium P1**: Acceso condicional, SSO a apps, grupos dinámicos.
- **Premium P2**: Identity Protection, acceso basado en riesgos, privilegios mínimos (PIM).

---

## 🛠️ 7. Herramientas de Administración

- **Portal de Azure**: Interfaz web principal.
- **Microsoft Entra Admin Center**: Portal específico para administración de identidades.
- **PowerShell y CLI**: Para automatización y gestión avanzada.
- **Graph API**: Para desarrolladores y automatización personalizada.

---

## 📚 8. Buenas Prácticas

- Usar MFA para todos los usuarios.
- Aplicar políticas de acceso condicional.
- Minimizar privilegios (principio de menor privilegio).
- Usar grupos dinámicos para automatización.
- Monitorear accesos con Azure AD Sign-In Logs y Audit Logs.
