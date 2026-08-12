# Proyecto 5: Auditoria con CloudTrail y Analisis de Logs

**Tiempo estimado: 3-5 horas**

## Objetivo

Aprender a auditar actividad en una cuenta de AWS utilizando CloudTrail, almacenar los logs de forma segura y analizarlos para detectar actividad sospechosa relacionada con IAM y otros servicios.

## Prerequisitos

- Cuenta de AWS (idealmente una cuenta de pruebas/sandbox, no de produccion).
- Terraform instalado (>= 1.5).
- AWS CLI configurado con credenciales temporales o un perfil dedicado (nunca usar credenciales root).
- Familiaridad basica con S3, IAM y CloudTrail (ver Fase 1 y el laboratorio [aws-iam-security-lab](https://github.com/Echo506/aws-iam-security-lab)).

## Arquitectura del laboratorio

- **CloudTrail Trail**: multi-region, con logging de eventos de management y opcionalmente de datos.
- **Bucket S3**: destino de los logs, con versionado habilitado, bloqueo de acceso publico y cifrado (SSE-S3 o SSE-KMS).
- **Log file validation**: habilitado para detectar manipulacion de logs.
- **(Opcional) CloudWatch Logs**: integracion para busquedas y alertas en tiempo real.
- **(Opcional) Athena**: tabla externa sobre los logs en S3 para consultas SQL ad-hoc.

## Temas a cubrir (checklist)

- [ ] Crear un trail de CloudTrail multi-region con Terraform.
- [ ] Configurar un bucket S3 seguro como destino de logs (versionado, bloqueo de acceso publico, cifrado).
- [ ] Habilitar log file validation para garantizar integridad.
- [ ] Generar actividad de prueba (crear/eliminar un usuario IAM, asumir un rol) y localizar los eventos correspondientes en CloudTrail.
- [ ] Consultar los logs con Athena o CloudWatch Logs Insights.
- [ ] Documentar un caso de uso de deteccion (por ejemplo, alertar sobre `CreateAccessKey` o cambios en politicas de IAM).

## Uso (setup, test, destroy)

```bash
# 1. Clonar el repositorio y entrar al modulo
cd projects/05-audit-cloudtrail

# 2. Configurar credenciales de AWS (perfil dedicado, sin usar root)
export AWS_PROFILE=lab-sandbox

# 3. Inicializar Terraform
terraform init

# 4. Revisar el plan antes de aplicar
terraform plan

# 5. Aplicar la configuracion (crea el trail y el bucket S3)
terraform apply

# 6. Generar actividad de prueba (ejemplo)
aws iam create-user --user-name lab-test-user
aws iam delete-user --user-name lab-test-user

# 7. Revisar los eventos en la consola de CloudTrail o vía Athena/CLI
aws cloudtrail lookup-events --max-results 10

# 8. Destruir los recursos al finalizar para evitar costos
terraform destroy
```

> Importante: nunca subas archivos `.tfstate`, credenciales ni archivos `.tfvars` con datos sensibles al repositorio. Usa variables de entorno o un backend remoto seguro para el estado de Terraform.

## Recursos sugeridos

- Documentacion oficial de AWS CloudTrail y AWS Config.
- Guias de AWS sobre analisis de logs con Amazon Athena.
- NIST SP 800-92 (Guide to Computer Security Log Management).

## Resultado esperado

Poder desplegar un trail de CloudTrail reproducible con Terraform, consultar eventos relevantes de la cuenta y explicar como la auditoria de logs soporta la deteccion de incidentes y el cumplimiento normativo (por ejemplo, en el contexto de DoD RMF o FedRAMP).

> Relacionado: este proyecto complementa el laboratorio [aws-iam-security-lab](https://github.com/Echo506/aws-iam-security-lab), que incluye un modulo dedicado de auditoria (`05-audit-cloudtrail`) con la implementacion completa en Terraform.
