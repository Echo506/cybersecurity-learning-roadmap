# Proyecto 2: IA para Ciberseguridad

**Fase del roadmap:** 2 de 3 | **Tiempo estimado:** 3-4 horas

## Experiencia practica

Esta fase busca pasar de la teoria a observar (y en lo posible, construir) ejemplos simples de deteccion asistida por IA/ML. Actividades recomendadas:

1. **Explorar un dataset publico de seguridad**: usa un dataset conocido como NSL-KDD o CICIDS2017 (disponibles en Kaggle o UCI Machine Learning Repository) para ver como se estructuran los datos de trafico de red usados para entrenar modelos de deteccion de intrusiones.
2. **Construir un detector de anomalias simple**: con Python (pandas + scikit-learn), entrena un modelo basico de deteccion de anomalias (ej. Isolation Forest o un simple z-score sobre metricas de trafico) usando un dataset publico. No necesitas precision perfecta; el objetivo es entender el pipeline: datos -> features -> modelo -> alerta.
3. **Probar un asistente de seguridad basado en IA**: si tienes acceso, explora una demo de Microsoft Security Copilot, o revisa como CrowdStrike/Darktrace documentan publicamente el funcionamiento de sus motores de deteccion basados en ML.
4. **Analizar un caso de adversarial ML**: busca un caso documentado (ej. investigaciones academicas o de la industria) donde un atacante logro evadir un clasificador de malware, y identifica que tecnica de evasion se uso.

Esta experiencia no requiere ser data scientist: el objetivo es entender que problema resuelve el ML en seguridad y donde son sus limites, para poder evaluar criticamente herramientas comerciales que dicen usar "IA".

## Temas a cubrir

- [ ] **Herramientas de seguridad potenciadas por IA**
  - EDR/XDR con deteccion basada en comportamiento (vs. firmas tradicionales).
  - SOAR (Security Orchestration, Automation and Response) con triage/priorizacion automatizada de alertas.
  - Asistentes de seguridad basados en LLM (ej. resumenes de incidentes, generacion de queries de busqueda de amenazas).
- [ ] **Deteccion de amenazas con machine learning**
  - Diferencia entre modelos supervisados (clasificacion de malware con muestras etiquetadas) y no supervisados (deteccion de anomalias sin etiquetas previas).
  - Deteccion de anomalias en trafico de red (baseline de comportamiento normal vs. desviaciones).
  - Clasificacion de malware usando features estaticas (hashes, strings, metadata) o dinamicas (comportamiento en sandbox).
- [ ] **UEBA (User and Entity Behavior Analytics)**
  - Como se construye un perfil de comportamiento "normal" por usuario/entidad.
  - Ejemplos de senales: acceso fuera de horario habitual, volumen inusual de descargas, movimiento lateral entre sistemas.
- [ ] **Limitaciones y riesgos**
  - Falsos positivos (alert fatigue) y falsos negativos (amenazas no detectadas).
  - Sesgo en los datos de entrenamiento y su impacto en la deteccion.
  - Adversarial machine learning: como un atacante puede disenar entradas especificamente para evadir un modelo.
  - Importancia de mantener "human-in-the-loop" (un analista humano validando decisiones criticas).

## Recursos sugeridos

- **MITRE ATT&CK** (attack.mitre.org) - framework de tacticas y tecnicas de atacantes; contexto necesario para entender que intentan detectar estas herramientas.
- **Datasets publicos**: NSL-KDD, CICIDS2017, o el dataset de deteccion de phishing de Kaggle, para practicar con datos reales.
- **scikit-learn documentation** - modulo de deteccion de anomalias (Isolation Forest, One-Class SVM) con ejemplos de codigo.
- **Publicaciones tecnicas de proveedores**: blogs de ingenieria de CrowdStrike, Microsoft Defender, y Darktrace sobre como aplican ML en produccion.
- **OWASP Machine Learning Security Top 10** - riesgos de seguridad especificos de sistemas que usan ML, incluyendo adversarial attacks.

## Resultado esperado

Al finalizar esta fase deberias poder:

- Explicar la diferencia entre deteccion basada en firmas y deteccion basada en comportamiento/ML.
- Describir, con un ejemplo propio, como un modelo no supervisado podria detectar una amenaza desconocida (zero-day) que un sistema basado en firmas no detectaria.
- Nombrar al menos una limitacion importante de depender solo de IA/ML para deteccion (ej. adversarial ML o alert fatigue por falsos positivos).
- Describir el pipeline basico de un sistema de deteccion de anomalias: recoleccion de datos, extraccion de features, entrenamiento/inferencia, generacion de alerta.

## Enlaces relacionados

- [Roadmap principal](../../README.md)
- Anterior: [Proyecto 1 - Fundamentos de IAM](../01-iam-fundamentals/README.md)
- Siguiente: [Proyecto 3 - Seguridad y Cumplimiento en la Nube](../03-cloud-security-compliance/README.md)
