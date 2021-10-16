# Laboratorio de Cómputo con Nested Stacks

Templates:
* master.yml
* efs.yml
* alb.yml
* rds.yml
* asg.yml

Pre-Requisitos:

* Necesita una VPC en su cuenta con al menos 2 subredes públicas y 2 subredes privadas.
* Debe tener un SecureString en Parameter Group creado con el nombre `RDS_PASSWORD` el cual almacenará el password que quiere para su RDS.
* Todos los templates deben estar cargados en un bucket de S3.

  EfsStack:
    Type: AWS::CloudFormation::Stack
    Properties:
      TemplateURL: "https://<your_bucket_name>.s3.<your_region>.amazonaws.com/<template_name>"
      TimeoutInMinutes: 30
      Parameters: 
        PrivateSubnetId1: !Select [ 0, !Ref PrivateSubnets ]
        PrivateSubnetId2: !Select [ 1, !Ref PrivateSubnets ]
        VPCId: !Ref VPCId
        VPCCidr: !Ref VPCCidr

Actualice el master.yml haciendo el llamado a todos sus stacks con el ejemplo anterior. 


