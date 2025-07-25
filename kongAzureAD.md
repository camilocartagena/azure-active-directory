# 💡 PoC: Integración de Kong Konnect con Azure Active Directory (AAD)

Este documento describe los pasos necesarios para configurar Azure AD como proveedor de identidad (IdP) en Kong Konnect mediante OpenID Connect (OIDC).

---

## 📋 Requisitos previos

- Cuenta de **Azure AD** con permisos administrativos.
- Acceso a **Kong Konnect** (Control Plane habilitado).
- Plugin **OIDC** habilitado en Konnect.
- Tener configurado tu dominio o hostname para redirección: `https://<tu-kong-host>/oauth2/callback`.

---

## 🧭 Paso 1: Registrar una aplicación en Azure AD

1. Accede al [Azure Portal](https://portal.azure.com/).
2. Ve a: **Azure Active Directory** → **App registrations** → **+ New registration**.
3. Completa el formulario:
   - **Nombre**: `Kong Konnect Integration`
   - **Supported account types**: Single tenant o multitenant (según necesidad).
   - **Redirect URI**:
     - Tipo: `Web`
     - URI: `https://<tu-kong-host>/oauth2/callback`
4. Haz clic en **Register**.

---

## 🔐 Paso 2: Crear un secreto de cliente

1. Dentro de la app registrada, ve a **Certificates & secrets** → **+ New client secret**.
2. Proporciona una descripción y selecciona una expiración (6–12 meses recomendado).
3. Guarda el **valor del secreto**, lo usarás en Kong.

---

## 📥 Paso 3: Obtener datos de configuración de OIDC

1. En la sección **Overview** copia:
   - `Application (client) ID`
   - `Directory (tenant) ID`
2. Construye el **Discovery Endpoint URL**:
   ```text
   https://login.microsoftonline.com/<TENANT_ID>/v2.0/.well-known/openid-configuration
   ```
