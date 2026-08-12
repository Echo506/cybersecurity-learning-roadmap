# Cybersecurity Learning Roadmap

Roadmap practico y por etapas para construir una base solida en ciberseguridad, con enfoque en Identity and Access Management (IAM), IA aplicada a seguridad, seguridad/cumplimiento en la nube (incluyendo estandares del Departamento de Defensa de EE. UU.: DoD RMF, IL4/IL5, y FedRAMP), y operaciones de un SOC (deteccion, respuesta a incidentes y auditoria).

Esta guia esta pensada para avanzar de lo fundamental a lo mas especializado, con tiempos estimados por etapa para poder planificar el estudio en sesiones cortas.

## Como usar este roadmap

1. Sigue las cinco fases en orden: cada una construye sobre los conceptos de la anterior.
2. Usa el checklist de cada fase para marcar tu progreso.
3. Los recursos sugeridos son un punto de partida; complementa con documentacion oficial (NIST, AWS, Microsoft, DoD) cuando sea posible.
4. Considera documentar lo aprendido (notas, laboratorios propios, capturas) como evidencia para portafolio o entrevistas.

## Resumen de fases

| Fase | Tema | Tiempo estimado |
|---|---|---|
| 1 | Fundamentos de Ciberseguridad (IAM) | 1-2 horas |
| 2 | IA para Ciberseguridad | 3-4 horas |
| 3 | Seguridad y Cumplimiento en la Nube | 4-6 horas |
| 4 | SOC Operations (SIEM, IR, Monitoreo de Red) | 5-7 horas |
| 5 | Auditoria con CloudTrail y Analisis de Logs | 3-5 horas |

**Tiempo total estimado: 16-24 horas**

## Proyectos (guias detalladas)

Cada fase tiene una guia detallada dentro de la carpeta `projects/`, con experiencia practica sugerida, checklist de temas y recursos:

- [Proyecto 1 - Fundamentos de IAM (RBAC, MFA, SSO, PKI)](projects/01-iam-fundamentals/README.md)
- [Proyecto 2 - IA para Ciberseguridad](projects/02-ai-for-cybersecurity/README.md)
- [Proyecto 3 - Seguridad y Cumplimiento en la Nube](projects/03-cloud-security-compliance/README.md)
- [Proyecto 4 - SOC Operations (SIEM, IR, Monitoreo de Red)](projects/04-soc-operations/README.md)
- [Proyecto 5 - Auditoria con CloudTrail y Analisis de Logs](projects/05-audit-cloudtrail/README.md)

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

## Fase 4: SOC Operations (SIEM, IR, Monitoreo de Red)

**Tiempo estimado: 5-7 horas**

### Objetivo

Comprender como opera un Security Operations Center (SOC): deteccion de amenazas, monitoreo continuo y respuesta a incidentes.

### Temas a cubrir

- [ ] **SIEM (Security Information and Event Management)**: recoleccion y correlacion de logs, alertas y casos de uso comunes.
- [ ] **Monitoreo de red**: analisis de trafico, deteccion de anomalias y herramientas IDS/IPS.
- [ ] **Respuesta a incidentes (IR)**: ciclo de vida de un incidente (preparacion, deteccion, contencion, erradicacion, recuperacion, lecciones aprendidas).
- [ ] **Threat hunting basico**: busqueda proactiva de indicadores de compromiso (IOCs).

### Recursos sugeridos

- NIST SP 800-61 (Computer Security Incident Handling Guide).
- Documentacion de herramientas SIEM (Splunk, Elastic Security, Microsoft Sentinel).
- MITRE ATT&CK como marco de referencia para tacticas y tecnicas de atacantes.

### Resultado esperado

Poder describir el flujo de trabajo de un analista SOC y aplicar un proceso basico de respuesta a incidentes.

> Guia detallada: [Proyecto 4 - SOC Operations](projects/04-soc-operations/README.md)

---

## Fase 5: Auditoria con CloudTrail y Analisis de Logs

**Tiempo estimado: 3-5 horas**

### Objetivo

Aprender a auditar actividad en la nube utilizando AWS CloudTrail y herramientas de analisis de logs, cerrando el ciclo de visibilidad y cumplimiento iniciado en las fases anteriores.

### Temas a cubrir

- [ ] **AWS CloudTrail**: registro de llamadas a la API, tipos de trails (organizacion, multi-region) y almacenamiento de logs en S3.
- [ ] **Analisis de logs**: uso de Amazon Athena o CloudWatch Logs Insights para consultar eventos de CloudTrail.
- [ ] **Deteccion de actividad sospechosa**: identificar cambios no autorizados en IAM, accesos anomalos y uso indebido de credenciales.
- [ ] **Integridad de logs**: validacion de archivos de log de CloudTrail y proteccion contra manipulacion (log file validation, buckets con versionado y MFA delete).

### Recursos sugeridos

- Documentacion oficial de AWS CloudTrail y AWS Config.
- Guias de AWS sobre analisis de logs con Athena.
- NIST SP 800-92 (Guide to Computer Security Log Management).

### Resultado esperado

Poder configurar un trail basico, consultar eventos relevantes y explicar como la auditoria de logs soporta la deteccion de incidentes y el cumplimiento normativo.

> Guia detallada: [Proyecto 5 - Auditoria con CloudTrail](projects/05-audit-cloudtrail/README.md)
