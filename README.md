# Laboratorio de Cómputo con Nested Stacks

Templates:
* master.yml
* efs.yml
* alb.yml
* rds.yml
* asg.yml

Pre-Requisitos:

* Necesita una VPC en su cuenta con al menos 2 subredes públicas y 2 subredes privadas.
* Debe tener un SecureString en Parameter Store creado con el nombre `RDS_PASSWORD` el cual almacenará el password que quiere para su RDS.
* Todos los templates deben estar cargados en un bucket de S3.

      TemplateURL: "https://<your_bucket_name>.s3.<your_region>.amazonaws.com/<template_name>"

* Actualice el master.yml haciendo el llamado a todos sus stacks con el ejemplo anterior. 
* Tenga en cuenta en el stack de asg.yml actualizar las líneas 165 y 167 con la región donde vaya a lanzar los recursos.

# Diagrama de Arquitectura 

![Diagrama Arquitectura](https://github.com/cloudingla/lab-compute/blob/master/images/lab-compute.png)