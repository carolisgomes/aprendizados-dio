---

## Desafio AWS Step Functions
💻 Criei este documento para registrar alguns dos ensinamentos da orquestração de processos na nuvem AWS. Poderemos observar os conceitos, anotações e insights ao criar workflows automatizados e resilientes na AWS.


## 📝 O que são Step Funcitions?

Nada mais é do que um construtor visual para criar fluxos de trabalho. Ele é um serviço que facilita a coordenação de aplicativos e microserviços, usando fluxos de trabalho visuais. Ao criar o fluxo de trabalho, não precisamos ter todos os recursos do AWS antecipadamente para começar, podemos criar o workflow e depois adicionar as definições aos recursos.

### ⚙️ Alguns dos benefícios do Step Functions.
- Automação Serveless, sem necessidade de servidores para gerenciar ou escalar;
- Orquestração de Serviços, permitindo coordenar serviços da AWS (como Lambda, DynamoDB, Amazon S3, etc) em fluxos de trabalho complexos;
- Controle de fluxo e lógica condicional, permitindo criar condições, loops, paralelismo e ramificações em fluxos de trabalho, facilitando processos de decisão automáticos dentro do sistema;
- Monitoramento e rastreamento detalhado, onde cada etapa é registrada automaticamente no AWS CloudWatch;
- Tolerância a falhas, reduzindo o risco de falhas em processos longos ou distribuídos;
- Escalabilidade automática conforme o volume de execuções.

### 🤖 Estrutura do Workflow.

A estrutura de um workflow no AWS STep Functions é bem organizada, seguindo um modelo em JSON ou YAML, descrevendo o fluxo de execução de tarefas, decisões e estados.
Os componentes principais da estrutura são:
- **Comment**: Um comentário descritivo sobre o workflow, servindo apenas para documentação interna;
- **StartAt**: Define qual estado será executado primeiro;
- **States**: Contém todos os estados do workflow, cada estado tem um nome e um tipo.

Os tipos de estados mais usados são:
-**Task**: Executa uma tarefa;
-**Choice**: Faz decisões condicionais (if/else);
-**Parallel**: Executa várias etapas ao mesmo tempo;
-**Wait**: Adiciona um atraso/espera antes de continuar;
-**Succed/Fail**: Finaliza o processo.


---


## Desafio AWS CloudFormation.
💻 Neste desafio, tenho o objetivo de implementar a primeira stack com AWS CloudFormation. Observaremos os conceitos, anotações sobre o assunto.


## 📝 O que é o CloudFormation?
Nada mais é do que um conceito que auxilia na automação de criação de recursos na AWS por meio de templates JSON ou YAML. Podemos utilizar os templates quantas vezes quisermos e pagamos apenas pelas Stacks criadas (conjunto de recursos, ex: EC2, RDS, S3, etc).
Além de ser um processo automatizado, conseguimos versionar estes templates. Com ele podemos criar um recurso simples como uma EC2, até uma arquitetura robusta com vários recursos.

### ⚙️ Alguns dos benefícios do CloudFormation.
- Infraestrutura em código (IaC), permitindo descrever toda a infraestrutura em arquivos de template;
- Automação e consistência, criando e configurando recursos automaticamente, reduzindo erros humanos;
- Gerenciamento simplificado de Stacks, sendo possível criar, atualizar e excluir grupos inteiros de recursos de uma só vez, mantendo controle sobre dependência;
- Integração com outros serviços da AWS;
- Reprodutibilidade e escalabilidade, facilitando o provisionamento de múltiplos ambientes iguais.

### 🤖 Estrutura do CloudFormation.
Ele tem uma estrutura bem definida com seções específicas, algumas obrigatórias e outras opcionais.

Podemos das um exemplo bem básico de como seria o template do CloudFormation.

```yaml
AWSTemplateFormatVersion: "2010-09-09"  #(opcional)
Description: "Criação de uma instância EC2 simples"  #(opcional)

Resources:                               #(obrigatório)
  EC2Instance:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: "meu-bucket-exemplo-cloudformation"
```
