# 🚀 Implementando minha Primeira Stack com AWS CloudFormation

Projeto prático desenvolvido para o desafio de código da plataforma **Digital Innovation One (DIO)**. O objetivo principal deste repositório é documentar a implementação de uma infraestrutura como código (IaC) utilizando o **AWS CloudFormation**, servindo como guia de estudos e portfólio técnico.

============================================================================================

## 📌 Sumário
- [Sobre o projeto](#-sobre-o-projeto)
- [O que é AWS CloudFormation?](#-o-que-é-aws-cloudformation)
- [Conceitos Chave](#-conceitos-chave)
- [Estrutura do Modelo (Template)](#-estrutura-do-modelo-template)
- [Passo a Passo da Implementação](#-passo-a-passo-da-implementação)
- [Insights e Aprendizados](#-insights-e-aprendizados)
- [Estrutura do Repositório](#-estrutura-do-repositório)

============================================================================================

## 📖 Sobre o Projeto
Este laboratório demonstra como provisionar recursos AWS de forma automatizada, reproduzível e segura através de código, eliminando a necessidade de configurações manuais via AWS Management Console.

============================================================================================

## ☁️ O que é AWS CloudFormation?
O **AWS CloudFormation** é um serviço de Infraestrutura como Código (IaC) que permite modelar, provisionar e gerenciar recursos da AWS por meio de arquivos de modelo (templates) em formato **JSON** ou **YAML**.
========================================================================================================================================================================
### Vantagens do uso:
* **Automação:** Provisionamento rápido e sem intervenção manual.
* **Consistência:** Garante que ambientes de dev, test e prod sejam idênticos.
* **Controle de Versão:** Possibilidade de versionar a infraestrutura no GitHub.
* **Gerenciamento de Estado:** A AWS gerencia a criação, atualização e exclusão dos recursos de forma coordenada.

============================================================================================

## 🧠 Conceitos Chave

| Conceito | Descrição |
| :--- | :--- |
| **Template** | Arquivo em formato JSON ou YAML que declara os recursos AWS e suas configurações. |
| **Stack (Pilha)** | Conjunto de recursos AWS gerenciados como uma única unidade criada a partir do Template. |
| **Change Sets** | Prévia das alterações que serão feitas em uma Stack antes de executá-las de fato. |
| **Drift Detection** | Recurso que identifica se recursos da Stack foram alterados manualmente fora do CloudFormation. |

============================================================================================

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

```
============================================================================================
⚙️ Passo a Passo da Implementação

  1. Criação do Template:Escrita do código.
     Criei o arquivo template.yaml especificando os recursos que precisava provisionar (exemplo: uma instância EC2 ou um Bucket S3).

  2. Acesso ao Console AWS:
     Navegação.Acessei o Console da AWS e naveguei até o serviço CloudFormation.

  3. Criação da Stack:
     Deploy.Selecionei a opção Create Stack > With new resources (standard) e fiz o upload do arquivo template.yaml.
  
  4. Configuração de Parâmetros:
     Definições.Preenchi os parâmetros necessários (nome da Stack e variáveis de ambiente) e avancei pelas telas de configuração.
  
  5. Verificação de Eventos:
     Monitoramento.Acompanhei a aba Events até a alteração do status para CREATE_COMPLETE.
  
  6. Exclusão de Recursos:
     Limpeza de ambiente.Após testar, executei o Delete Stack para remover todos os recursos e evitar custos indesejados.
============================================================================================
💡 Insights e Aprendizados
  1. Gestão de Dependências Automática: O CloudFormation descobre a ordem correta de criação dos recursos com base nas referências cruzadas (Ref e Fn::GetAtt).

  2. Rollback Automático: Caso ocorra algum erro durante o provisionamento de qualquer recurso, o CloudFormation desfaz todas as alterações automaticamente (ROLLBACK_COMPLETE), mantendo o ambiente limpo.

  3. Boas Práticas de Custos: Sempre exclua a Stack após a conclusão de testes para não gerar cobranças adicionais na conta AWS.
============================================================================================
📁 Estrutura do Repositório
├── template.yaml      # Arquivo do CloudFormation com a declaração da infraestrutura
├── README.md          # Documentação do projeto
└── images/            # Printscreens do processo de criação da Stack
    ├── stack-creation.png
    └── stack-complete.png
