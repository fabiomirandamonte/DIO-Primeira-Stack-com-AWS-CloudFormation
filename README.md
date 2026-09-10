# 🚀 Implementando minha Primeira Stack com AWS CloudFormation

Projeto prático desenvolvido para o desafio de código da plataforma **Digital Innovation One (DIO)**. O objetivo principal deste repositório é documentar a implementação de uma infraestrutura como código (IaC) utilizando o **AWS CloudFormation**, servindo como guia de estudos e portfólio técnico.

---

## 📌 Sumário
- [Sobre o projeto](#-sobre-o-projeto)
- [O que é AWS CloudFormation?](#-o-que-é-aws-cloudformation)
- [Conceitos Chave](#-conceitos-chave)
- [Estrutura do Modelo (Template)](#-estrutura-do-modelo-template)
- [Passo a Passo da Implementação](#-passo-a-passo-da-implementação)
- [Insights e Aprendizados](#-insights-e-aprendizados)
- [Estrutura do Repositório](#-estrutura-do-repositório)

---

## 📖 Sobre o Projeto
Este laboratório demonstra como provisionar recursos AWS de forma automatizada, reproduzível e segura através de código, eliminando a necessidade de configurações manuais via AWS Management Console.

---

## ☁️ O que é AWS CloudFormation?
O **AWS CloudFormation** é um serviço de Infraestrutura como Código (IaC) que permite modelar, provisionar e gerenciar recursos da AWS por meio de arquivos de modelo (templates) em formato **JSON** ou **YAML**.

### Vantagens do uso:
* **Automação:** Provisionamento rápido e sem intervenção manual.
* **Consistência:** Garante que ambientes de dev, test e prod sejam idênticos.
* **Controle de Versão:** Possibilidade de versionar a infraestrutura no GitHub.
* **Gerenciamento de Estado:** A AWS gerencia a criação, atualização e exclusão dos recursos de forma coordenada.

---

## 🧠 Conceitos Chave

| Conceito | Descrição |
| :--- | :--- |
| **Template** | Arquivo em formato JSON ou YAML que declara os recursos AWS e suas configurações. |
| **Stack (Pilha)** | Conjunto de recursos AWS gerenciados como uma única unidade criada a partir do Template. |
| **Change Sets** | Prévia das alterações que serão feitas em uma Stack antes de executá-las de fato. |
| **Drift Detection** | Recurso que identifica se recursos da Stack foram alterados manualmente fora do CloudFormation. |

---

## 📄 Estrutura do Modelo (Template)

Os arquivos de modelo utilizam as seguintes seções principais:

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: 'Descrição da Stack - Primeira infraestrutura CloudFormation'

Parameters:
  # Entradas personalizáveis pelo usuário antes do deploy (ex: tipo de instância, chave SSH)

Resources:
  # SEÇÃO OBRIGATÓRIA: Define os recursos AWS a serem criados (ex: EC2, S3, VPC)
  MyEC2Instance:
    Type: 'AWS::EC2::Instance'
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c55b159cbfafe1f0 # Exemplo de AMI

Outputs:
  # Exibe valores de saída após o deploy (ex: IP público da instância, URL do bucket)
