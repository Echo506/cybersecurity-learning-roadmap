# Proyecto 1: Fundamentos de IAM (RBAC, MFA, SSO, PKI)

**Fase del roadmap:** 1 de 3 | **Tiempo estimado:** 1-2 horas

## Experiencia practica

Esta fase se enfoca en construir intuicion sobre como funcionan los controles de acceso antes de tocar herramientas especificas. La experiencia practica recomendada es:

1. **Explorar una consola de IAM real** (AWS IAM, Azure AD, o Google Cloud IAM en una cuenta gratuita/de prueba):
   - Crear un usuario y un grupo, y asignar una politica al grupo (no al usuario) para experimentar RBAC de primera mano.
   - Activar MFA en tu propia cuenta de prueba y observar el flujo de login antes/despues.
2. **Inspeccionar un certificado TLS real**: usa el navegador para ver el certificado de cualquier sitio HTTPS (candado > detalles del certificado) e identificar el emisor (CA), el periodo de validez y el algoritmo de firma.
3. **Configurar SSO en una app de prueba**: muchas apps SaaS (ej. una cuenta gratuita de Okta Developer o Auth0) permiten configurar un flujo SSO de ejemplo con SAML u OIDC en minutos.
4. **(Opcional, avanzado)** Replicar el laboratorio [aws-iam-security-lab](https://github.com/Echo506/aws-iam-security-lab) de este perfil, que aplica RBAC y MFA con Terraform de forma reproducible.

El objetivo de esta experiencia practica no es dominar una herramienta especifica, sino poder reconocer estos cuatro conceptos en cualquier plataforma que uses en el futuro.

## Temas a cubrir

- [ ] **RBAC (Role-Based Access Control)**
  - Diferencia entre asignar permisos a un usuario vs. a un rol/grupo.
  - Principio de minimo privilegio.
  - Ejemplos de roles tipicos: administrador, auditor de solo lectura, operador.
- [ ] **MFA (Multi-Factor Authentication)**
  - Los tres factores: algo que sabes (password), algo que tienes (token/telefono), algo que eres (biometria).
  - Metodos comunes: TOTP (Google Authenticator), push notification, llaves de hardware (FIDO2/YubiKey), SMS (y por que se considera menos seguro).
  - Por que MFA es uno de los controles con mejor relacion costo/beneficio en seguridad.
- [ ] **SSO (Single Sign-On)**
  - Concepto de identity provider (IdP) vs. service provider (SP).
  - Protocolos: SAML 2.0, OAuth 2.0, OpenID Connect (OIDC).
  - Beneficios (menos passwords, revocacion centralizada) y riesgos (un solo punto de fallo si el IdP es comprometido).
- [ ] **PKI (Public Key Infrastructure)**
  - Par de llaves publica/privada y su uso en cifrado y firma digital.
  - Certificados digitales y el rol de una Autoridad Certificadora (CA).
  - Cadena de confianza (root CA, intermediate CA, certificado final).
  - Casos de uso: HTTPS/TLS, firma de codigo, autenticacion de dispositivos/maquinas.

## Recursos sugeridos

- **NIST SP 800-162** - Guide to Attribute Based Access Control (ABAC), util tambien para contrastar con RBAC.
- **Documentacion oficial de AWS IAM**, Azure Active Directory / Entra ID, o Google Cloud IAM - para ver RBAC y SSO implementados en un proveedor real.
- **FIDO Alliance** (fidoalliance.org) - para entender los estandares modernos de MFA sin password.
- **DigiCert / Let's Encrypt - "How SSL/TLS works"** - guias introductorias sobre el ciclo de vida de un certificado.
- **Auth0 / Okta Developer docs** - explicaciones practicas de SAML vs. OAuth2 vs. OIDC con diagramas de flujo.

## Resultado esperado

Al finalizar esta fase deberias poder:

- Explicar la diferencia entre autenticacion y autorizacion con un ejemplo propio.
- Dibujar (aunque sea en papel) el flujo basico de un login con SSO usando OIDC.
- Explicar por que un certificado TLS es valido o no, mirando su cadena de confianza.
- Justificar, en una frase, por que MFA deberia ser obligatorio para cuentas con privilegios elevados.

## Enlaces relacionados

- [Roadmap principal](../../README.md)
- [Laboratorio practico: aws-iam-security-lab](https://github.com/Echo506/aws-iam-security-lab)
- Siguiente: [Proyecto 2 - IA para Ciberseguridad](../02-ai-for-cybersecurity/README.md)
