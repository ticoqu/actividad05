# Actividad 5: Despliegue de 3 máquinas con recursos diferenciados

## Descripción
Usarás Terraform para desplegar tres máquinas: una master y dos workers, cada una con configuraciones de CPU, memoria y discos diferentes.

## Requisitos
- Terraform instalado.
- Plantilla `debian-12-qcow2-template` en Proxmox.

### 🎯 Objetivo
Desplegar tres máquinas virtuales con distintos tipos (master y workers) y recursos asignados dinámicamente.

### Entrega
- Archivos tf
- Mostrar capturas de las máquinas creadas en Proxmox.
- Verificar los recursos asignados (memoria, CPU, discos).

## Pasos a seguir

1. **Reutiliza los archivos anteriores**: `main.tf`, `variables.tf`, `terraform.tfvars`.

2. **Verifica el contenido de `terraform.tfvars`**
   Asegúrate de que tenga:
   ```hcl
   cluster_psql = [
     { name = "master-psql", ip = "192.168.1.20", target = "pve", type = "master" },
     { name = "worker-psql1", ip = "192.168.1.21", target = "pve", type = "worker" },
     { name = "worker-psql2", ip = "192.168.1.22", target = "pve", type = "worker" }
   ]

3. **Verificar tareas**
   ```bash
   terraform plan
   ```
   
4. **Ejecutar el despliegue**
   ```bash
   terraform apply
   ```
