# Proyecto 3: Seguridad y Cumplimiento en la Nube

**Fase del roadmap:** 3 de 3 | **Tiempo estimado:** 4-6 horas

## Experiencia practica

Esta es la fase mas orientada a cumplimiento normativo. La experiencia practica aqui es mas de analisis documental y comparacion de arquitecturas que de laboratorio tecnico, aunque incluye algunos ejercicios tecnicos:

1. **Diagrama de responsabilidad compartida**: elige un proveedor (AWS, Azure o GCP) y dibuja (o documenta en una tabla) que controles son responsabilidad del proveedor vs. del cliente para un servicio especifico (ej. una base de datos administrada vs. una VM sin administrar).
2. **Explorar el marketplace de FedRAMP**: visita el sitio oficial de FedRAMP y busca 2-3 servicios en la nube que tengan una autorizacion "FedRAMP Moderate" o "FedRAMP High", y revisa que tipo de agencias los usan.
3. **Leer un SSP (System Security Plan) resumido o un caso de estudio publico**: algunos proveedores publican resumenes de sus paquetes de autorizacion; identificar que controles de NIST SP 800-53 se mencionan con mas frecuencia.
4. **Ejercicio de clasificacion de datos**: toma 3-4 tipos de datos ficticios (ej. datos de salud de personal militar, informacion publica de una pagina web, planos de infraestructura critica) y clasifica cual Impact Level (IL2, IL4, IL5) le correspondería y por que.
5. **(Tecnico, opcional)** Revisa la configuracion de seguridad de un servicio IoT/edge real (ej. AWS IoT Core o Azure IoT Hub) y identifica que mecanismos de autenticacion de dispositivos usa (certificados X.509, tokens).

## Temas a cubrir

- [ ] **Modelo de responsabilidad compartida**
  - Que asegura el proveedor de nube (infraestructura fisica, hipervisor, algunos servicios administrados).
  - Que asegura el cliente (configuracion, datos, gestion de identidades, parches en IaaS).
  - Como cambia la linea de responsabilidad entre IaaS, PaaS y SaaS.
- [ ] **Seguridad de edge/IoT**
  - Superficie de ataque ampliada por dispositivos distribuidos y con recursos limitados.
  - Gestion de identidad de dispositivos (certificados por dispositivo, aprovisionamiento seguro).
  - Retos de parchar/actualizar dispositivos remotos o con conectividad intermitente.
- [ ] **Integracion segura**
  - Autenticacion de servicio a servicio (API keys, OAuth2 client credentials, mTLS).
  - Cifrado en transito (TLS) y en reposo (KMS/HSM) en pipelines de datos entre servicios.
  - Patrones seguros para colas de mensajes y APIs expuestas entre componentes en la nube.
- [ ] **DoD RMF (Risk Management Framework)**
  - Las siete etapas: Prepare, Categorize, Select, Implement, Assess, Authorize, Monitor.
  - Rol del Authorizing Official (AO) en otorgar la Autorizacion para Operar (ATO).
  - Diferencia entre RMF y el proceso tradicional de C&A (Certification and Accreditation) que reemplazo.
- [ ] **DoD Impact Levels (IL4 / IL5)**
  - Tipo de datos correspondientes: IL4 para informacion controlada no clasificada (CUI) sensible; IL5 para informacion nacional de seguridad y CUI de mayor sensibilidad.
  - Controles adicionales de IL5: aislamiento fisico/logico mas estricto, requisitos de personal (ciudadania de EE. UU.), restricciones de ubicacion de datos.
- [ ] **FedRAMP**
  - Proposito: estandarizar la evaluacion, autorizacion y monitoreo continuo de seguridad de servicios en la nube usados por el gobierno de EE. UU.
  - Niveles de autorizacion: Low, Moderate, High (segun la sensibilidad de los datos).
  - Proceso de autorizacion: evaluacion por un 3PAO (Third-Party Assessment Organization), paquete de autorizacion, emision de la ATO por una agencia o el JAB.

## Recursos sugeridos

- **Sitio oficial de FedRAMP** (fedramp.gov) - marketplace de proveedores autorizados y documentacion del proceso.
- **DoD Cloud Computing Security Requirements Guide (SRG)** - documento publico que detalla los requisitos especificos de IL2, IL4, IL5 y IL6.
- **NIST SP 800-37** - Risk Management Framework, la base conceptual que adopta el DoD RMF.
- **NIST SP 800-53** - catalogo de controles de seguridad que se seleccionan durante la etapa "Select" del RMF.
- **Documentacion de AWS GovCloud (US)** y **Azure Government** - como estas regiones especificas cumplen con IL4/IL5 y FedRAMP.
- **ENISA / NIST guidance on IoT security** - buenas practicas para seguridad de dispositivos edge/IoT.

## Resultado esperado

Al finalizar esta fase deberias poder:

- Explicar el modelo de responsabilidad compartida usando un ejemplo especifico de servicio (ej. RDS de AWS vs. una EC2 sin administrar).
- Enumerar las siete etapas del DoD RMF en el orden correcto.
- Explicar la diferencia principal entre IL4 e IL5 y dar un ejemplo de dato que corresponderia a cada uno.
- Explicar por que un proveedor de nube necesita una autorizacion FedRAMP para vender a agencias federales de EE. UU., y que hace un 3PAO en ese proceso.
- Identificar al menos un riesgo especifico de seguridad en dispositivos edge/IoT que no aplica de la misma forma en servidores tradicionales.

## Enlaces relacionados

- [Roadmap principal](../../README.md)
- Anterior: [Proyecto 2 - IA para Ciberseguridad](../02-ai-for-cybersecurity/README.md)
