# Proyecto 4: SOC Operations (SIEM, Respuesta a Incidentes, Monitoreo de Red)

**Fase del roadmap:** 4 de 4 | **Tiempo estimado:** 5-7 horas

## Objetivo

Las fases 1 a 3 cubren como configurar identidad de forma segura, como la IA ayuda a detectar amenazas, y como se cumplen requisitos de seguridad en la nube. Esta fase agrega la habilidad operativa central de un SOC Analyst: **detectar, investigar y responder** a eventos de seguridad en tiempo real usando un SIEM, un proceso formal de respuesta a incidentes, y analisis de trafico de red.

Esta fase conecta directamente con experiencia previa en soporte de red y telecomunicaciones (troubleshooting de capas 1-3, analisis de trafico, manejo de tickets), aplicando esas mismas habilidades a un contexto de seguridad.

## Experiencia practica

1. **Explorar un SIEM gratuito**: instala o usa una instancia de prueba de Splunk Free, Microsoft Sentinel (trial), o monta un stack ELK/OpenSearch local. Ingiere logs de muestra (ej. logs de autenticacion, logs de firewall) y practica escribir consultas basicas de busqueda.
2. **Practicar con un dataset de logs publico**: usa datasets como los de Security Onion o muestras de logs de Sysmon/Windows Event Logs disponibles publicamente, y busca eventos especificos (ej. multiples intentos fallidos de login, un proceso sospechoso).
3. **Simular un playbook de respuesta a incidentes**: toma un escenario simple (ej. "se detecto una alerta de malware en un endpoint") y documenta paso a paso como aplicarias las fases de NIST SP 800-61: Preparation, Detection & Analysis, Containment, Eradication, Recovery, Lessons Learned.
4. **Capturar y analizar trafico de red**: usa Wireshark en tu propia maquina/red domestica para capturar trafico, identificar protocolos comunes (DNS, HTTP/HTTPS, ARP) y reconocer un patron anomalo simple (ej. un escaneo de puertos con Nmap contra tu propia maquina de prueba, en un entorno controlado y autorizado).
5. **Explorar reglas de un IDS/IPS**: revisa reglas de ejemplo de Suricata o Snort (disponibles publicamente) y entiende como una regla detecta una firma de trafico malicioso especifica.

> Nota etica: todo ejercicio de captura de trafico o escaneo debe hacerse unicamente en redes o sistemas propios o con autorizacion explicita. Nunca se debe escanear o capturar trafico de redes de terceros sin permiso.

## Temas a cubrir

- [ ] **Fundamentos de SIEM**
  - Que es un SIEM y por que centraliza logs de multiples fuentes (endpoints, firewalls, servidores, aplicaciones).
  - Diferencia entre SIEM (correlacion y alertas) y SOAR (automatizacion de respuesta).
  - Escritura basica de consultas de busqueda (ej. SPL en Splunk, KQL en Sentinel).
  - Creacion de una alerta/regla de correlacion simple (ej. 5 logins fallidos en 1 minuto desde la misma IP).
- [ ] **Respuesta a Incidentes (Incident Response)**
  - Las seis fases de NIST SP 800-61: Preparation, Detection & Analysis, Containment, Eradication, Recovery, Lessons Learned (Post-Incident Activity).
  - Diferencia entre contencion (aislar el problema) y erradicacion (eliminar la causa raiz).
  - Importancia de la cadena de custodia y documentacion durante un incidente.
  - Clasificacion de severidad de incidentes (ej. P1-P4) y tiempos de respuesta esperados (SLA).
- [ ] **Monitoreo y analisis de trafico de red**
  - Uso basico de Wireshark: filtros de captura y de visualizacion, seguimiento de una conversacion TCP.
  - Diferencia entre IDS (deteccion) e IPS (prevencion activa).
  - Reconocimiento de patrones de trafico anomalos: escaneo de puertos, exfiltracion de datos, beaconing de C2 (Command and Control).
  - Netflow / logs de firewall como fuente complementaria a la captura de paquetes completa.
- [ ] **Gestion de vulnerabilidades**
  - Ciclo de vida: descubrimiento, escaneo, priorizacion, remediacion, verificacion.
  - Uso de CVSS (Common Vulnerability Scoring System) para priorizar que vulnerabilidades atender primero.
  - Herramientas comunes: Nessus, OpenVAS, Qualys.

## Recursos sugeridos

- **NIST SP 800-61** - Computer Security Incident Handling Guide (la referencia oficial para el proceso de IR).
- **Splunk Fundamentals (gratuito)** o **Microsoft Sentinel Ninja Training** - cursos introductorios oficiales sobre SIEM.
- **Wireshark University / Wireshark.org docs** - guias oficiales de uso de filtros y analisis de capturas.
- **Snort / Suricata rule documentation** - para entender la sintaxis de reglas de deteccion.
- **MITRE ATT&CK** - para mapear que tacticas/tecnicas buscarias detectar en un SIEM o con un IDS.
- **Security Onion** - distribucion gratuita que integra SIEM, IDS y captura de red en un solo entorno de laboratorio.
- **Documentacion de Nessus Essentials (gratuito)** - para practicar un escaneo de vulnerabilidades basico en tu propia red.

## Resultado esperado

Al finalizar esta fase deberias poder:

- Escribir una consulta de busqueda simple en un SIEM para encontrar un patron especifico de eventos.
- Describir las seis fases de respuesta a incidentes de NIST SP 800-61 en orden, con un ejemplo de que se hace en cada una.
- Explicar la diferencia entre un IDS y un IPS, y dar un ejemplo de cuando usarias cada uno.
- Identificar, en una captura de trafico, al menos un patron que consideraras sospechoso y justificar por que.
- Explicar como se prioriza una vulnerabilidad usando CVSS.

## Enlaces relacionados

- [Roadmap principal](../../README.md)
- Anterior: [Proyecto 3 - Seguridad y Cumplimiento en la Nube](../03-cloud-security-compliance/README.md)
