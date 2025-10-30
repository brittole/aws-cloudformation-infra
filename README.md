# aws-cloudformation-infra
# Implementando Infraestrutura Automatizada com AWS CloudFormation

## Descrição do Desafio
Este repositório foi criado para documentar o desafio “Implementando Infraestrutura Automatizada com AWS CloudFormation”, proposto pela Digital Innovation One (DIO).  
O objetivo é aplicar os conceitos de **infraestrutura como código (IaC)**, utilizando o CloudFormation para provisionar automaticamente diversos recursos na AWS de forma segura, escalável e reproduzível.

---

## Objetivos de Aprendizagem
Ao concluir este desafio, eu fui capaz de:
- Entender o funcionamento e a estrutura do AWS CloudFormation;
- Criar e gerenciar stacks automatizadas a partir de templates YAML/JSON;
- Compreender como o CloudFormation reduz erros e aumenta a eficiência em implantações na nuvem;
- Documentar de forma técnica o processo de automação de infraestrutura.

---

## O que é o AWS CloudFormation
O **AWS CloudFormation** é um serviço que permite descrever toda a infraestrutura de um ambiente AWS usando arquivos de texto (YAML ou JSON).  
Esses arquivos são chamados de **templates** e definem os recursos necessários para o funcionamento de um sistema — como servidores, bancos de dados, redes e permissões.  

O CloudFormation interpreta o template e **cria automaticamente todos os recursos**, obedecendo dependências, configurações e políticas definidas pelo usuário.  
Dessa forma, você pode **replicar ambientes inteiros** de forma rápida, padronizada e controlada.

---

## Conceitos-Chave

| Conceito | Descrição |
|-----------|------------|
| **Template** | Arquivo YAML ou JSON que descreve a infraestrutura desejada. |
| **Stack** | Conjunto de recursos criados a partir de um template. |
| **Resources** | Componentes reais da AWS, como EC2, S3, IAM, Lambda, entre outros. |
| **Parameters** | Valores dinâmicos que permitem personalizar a implantação. |
| **Outputs** | Informações retornadas após a criação da stack (ex: URL, ID, IP). |
| **Change Set** | Mostra as alterações que serão feitas antes de atualizar uma stack. |

---

## Exemplo de Template (YAML)

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Exemplo de infraestrutura automatizada com CloudFormation

Resources:
  MinhaVPC:
    Type: AWS::EC2::VPC
    Properties:
      CidrBlock: 10.0.0.0/16
      EnableDnsSupport: true
      EnableDnsHostnames: true
      Tags:
        - Key: Name
          Value: VPC-Automation

  MeuBucketS3:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: infraestrutura-automatica-dio
      VersioningConfiguration:
        Status: Enabled
