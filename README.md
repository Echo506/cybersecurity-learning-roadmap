# Cybersecurity Learning Roadmap

Roadmap practico y por etapas para construir una base solida en ciberseguridad, con enfoque en Identity and Access Management (IAM), IA aplicada a seguridad, y seguridad/cumplimiento en la nube (incluyendo estandares del Departamento de Defensa de EE. UU.: DoD RMF, IL4/IL5, y FedRAMP).

Esta guia esta pensada para avanzar de lo fundamental a lo mas especializado, con tiempos estimados por etapa para poder planificar el estudio en sesiones cortas.

## Como usar este roadmap

1. Sigue las tres fases en orden: cada una construye sobre los conceptos de la anterior.
2. Usa el checklist de cada fase para marcar tu progreso.
3. Los recursos sugeridos son un punto de partida; complementa con documentacion oficial (NIST, AWS, Microsoft, DoD) cuando sea posible.
4. Considera documentar lo aprendido (notas, laboratorios propios, capturas) como evidencia para portafolio o entrevistas.

## Resumen de fases

| Fase | Tema | Tiempo estimado |
|---|---|---|
| 1 | Fundamentos de Ciberseguridad (IAM) | 1-2 horas |
| 2 | IA para Ciberseguridad | 3-4 horas |
| 3 | Seguridad y Cumplimiento en la Nube | 4-6 horas |

**Tiempo total estimado: 8-12 horas**

---

## Fase 1: Fundamentos de Ciberseguridad (IAM)

**Tiempo estimado: 1-2 horas**

### Objetivo

Entender los conceptos basicos de las soluciones de Identity and Access Management (IAM), que son la base de casi todos los controles de seguridad modernos.

### Temas a cubrir

- [ ] **RBAC (Role-Based Access Control)**: como se asignan permisos por rol en lugar de por usuario individual, y por que esto reduce el riesgo de sobre-permisos.
- [ ] **MFA (Multi-Factor Authentication)**: factores de autenticacion (algo que sabes, tienes, eres), metodos comunes (TOTP, push, hardware keys) y por que MFA reduce drasticamente el riesgo de cuentas comprometidas.
- [ ] **SSO (Single Sign-On)**: como funciona la autenticacion centralizada, protocolos comunes (SAML, OAuth2, OIDC) y sus beneficios/riesgos.
- [ ] **PKI (Public Key Infrastructure)**: conceptos de llave publica/privada, certificados digitales, autoridades certificadoras (CA) y como PKI habilita HTTPS, firma de codigo y autenticacion de dispositivos.

### Recursos sugeridos

- Documentacion de NIST sobre control de acceso (NIST SP 800-162 para ABAC/RBAC).
- Documentacion de AWS IAM / Azure AD / Google Cloud IAM como referencia practica de RBAC y SSO.
- Guias introductorias de PKI (por ejemplo, DigiCert o Let's Encrypt) para entender el ciclo de vida de un certificado.

### Resultado esperado

Poder explicar, con tus propias palabras, la diferencia entre autenticacion y autorizacion, y como RBAC, MFA, SSO y PKI se combinan para proteger el acceso a sistemas.

> Relacionado: el laboratorio [aws-iam-security-lab](https://github.com/Echo506/aws-iam-security-lab) de este mismo perfil aplica estos conceptos de forma practica con Terraform en AWS IAM.

---

## Fase 2: IA para Ciberseguridad

**Tiempo estimado: 3-4 horas**

### Objetivo

Explorar como la inteligencia artificial se usa para mejorar la seguridad, incluyendo herramientas de seguridad potenciadas por IA y deteccion de amenazas basada en machine learning.

### Temas a cubrir

- [ ] **Herramientas de seguridad potenciadas por IA**: EDR/XDR con deteccion basada en comportamiento, SOAR con triage automatizado, y asistentes de seguridad basados en LLM (ej. Microsoft Security Copilot).
- [ ] **Deteccion de amenazas con machine learning**: modelos supervisados vs. no supervisados, deteccion de anomalias en trafico de red, y clasificacion de malware.
- [ ] **UEBA (User and Entity Behavior Analytics)**: como los modelos de ML detectan comportamiento anomalo de usuarios o entidades (ej. acceso fuera de horario, movimientos laterales).
- [ ] **Limitaciones y riesgos**: falsos positivos/negativos, sesgo en modelos, adversarial machine learning (como los atacantes pueden intentar evadir modelos de deteccion), y la importancia de mantener supervision humana ("human-in-the-loop").

### Recursos sugeridos

- Documentacion de MITRE ATT&CK para entender el contexto de amenazas que estas herramientas intentan detectar.
- Publicaciones de proveedores (CrowdStrike, Microsoft, Darktrace) sobre como implementan ML en sus productos de deteccion.
- Cursos introductorios sobre fundamentos de machine learning aplicados a seguridad (ej. en Coursera o plataformas similares).

### Resultado esperado

Poder describir al menos dos casos de uso reales de IA/ML en ciberseguridad y explicar una limitacion importante de depender unicamente de estos sistemas.

---

## Fase 3: Seguridad y Cumplimiento en la Nube

**Tiempo estimado: 4-6 horas**

### Objetivo

Estudiar seguridad en la nube, dispositivos edge/IoT, e integracion segura, incluyendo los requisitos de DoD RMF, IL4/IL5 y FedRAMP.

### Temas a cubrir

- [ ] **Modelo de responsabilidad compartida**: que asegura el proveedor de nube (AWS/Azure/GCP) vs. que asegura el cliente.
- [ ] **Seguridad de edge/IoT**: superficie de ataque de dispositivos distribuidos, gestion de identidad de dispositivos, y retos de actualizar/parchar dispositivos en el borde de la red.
- [ ] **Integracion segura**: patrones seguros para APIs, colas de mensajes y pipelines de datos entre servicios en la nube (autenticacion de servicio a servicio, cifrado en transito y en reposo).
- [ ] **DoD RMF (Risk Management Framework)**: las siete etapas del RMF (Prepare, Categorize, Select, Implement, Assess, Authorize, Monitor) y como se usa para autorizar sistemas dentro del Departamento de Defensa de EE. UU.
- [ ] **DoD Impact Levels (IL4 / IL5)**: que tipo de datos corresponden a cada nivel de impacto, y que controles adicionales exige IL5 frente a IL4 (aislamiento, personal con ciudadania, ubicacion de datos).
- [ ] **FedRAMP**: proposito del programa (estandarizar la evaluacion de seguridad de servicios en la nube para el gobierno de EE. UU.), niveles de autorizacion (Low, Moderate, High), y el proceso general de autorizacion (assessment por un 3PAO, paquete de autorizacion, ATO).

### Recursos sugeridos

- Sitio oficial de [FedRAMP](https://www.fedramp.gov/) para entender el proceso de autorizacion y el marketplace de proveedores autorizados.
- Documentacion publica del DoD Cloud Computing Security Requirements Guide (SRG) para IL4/IL5.
- NIST SP 800-37 (Risk Management Framework) como base conceptual del RMF.
- Documentacion de AWS GovCloud / Azure Government sobre como sus regiones cumplen con estos requisitos.

### Resultado esperado

Poder explicar la diferencia entre IL4 e IL5, describir las etapas del RMF en orden, y explicar por que un proveedor de nube necesita una autorizacion FedRAMP para trabajar con agencias federales.

---

## Proximos pasos sugeridos

Despues de completar las tres fases, algunas rutas naturales de profundizacion son:

- Practicar los conceptos de IAM de forma hands-on (ver [aws-iam-security-lab](https://github.com/Echo506/aws-iam-security-lab)).
- Explorar certificaciones relacionadas: CompTIA Security+, (ISC)2 CCSP (seguridad en la nube), o certificaciones especificas de proveedor (AWS Security Specialty, Azure Security Engineer).
- Profundizar en un area especifica de IA para seguridad, por ejemplo montando un detector simple de anomalias con datos de logs publicos.
- Leer el paquete de autorizacion publico de un proveedor FedRAMP como caso de estudio real.

## Autor

Wilfrido Perez Romero - [LinkedIn](https://linkedin.com/in/wilfridocostarica)
