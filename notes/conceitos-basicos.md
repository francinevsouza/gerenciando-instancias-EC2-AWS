# ☁️ Conceitos Básicos sobre EC2, AMIs e Snapshots EBS

Este documento reúne os principais conceitos teóricos abordados durante o laboratório da DIO, **Gerenciando Instâncias EC2 na AWS**.  
Ele serve como material de apoio para revisão e entendimento dos componentes essenciais da computação em nuvem na AWS.

---

## 🖥️ 1. O que é o Amazon EC2?

O **Amazon EC2 (Elastic Compute Cloud)** é um serviço de computação em nuvem que permite criar e gerenciar **instâncias de servidores virtuais**.  

Essas instâncias podem ser configuradas conforme a necessidade do usuário, com diferentes sistemas operacionais, processadores, memória e armazenamento.

### ⚙️ Características principais:
- Escalabilidade: aumente ou reduza recursos conforme a demanda.  
- Elasticidade: pague apenas pelo que usar.  
- Flexibilidade: escolha o sistema operacional e as configurações ideais.  
- Integração com outros serviços AWS (S3, EBS, RDS, etc).  

### 🧩 Componentes principais de uma instância EC2:
| Componente | Função |
|-------------|--------|
| **AMI (Amazon Machine Image)** | Imagem que contém o sistema operacional e as configurações base da instância. |
| **Tipo de instância** | Define a quantidade de CPU, memória e rede (ex.: t2.micro). |
| **EBS (Elastic Block Store)** | Volume de armazenamento persistente. |
| **Security Group** | Conjunto de regras que controla o tráfego de entrada e saída. |
| **Key Pair (.pem)** | Par de chaves usado para acessar a instância via SSH. |

---

## 💾 2. O que é o Amazon EBS?

O **Amazon Elastic Block Store (EBS)** fornece volumes de armazenamento persistente que podem ser conectados às instâncias EC2.  

Mesmo que a instância seja encerrada, os dados armazenados no volume EBS podem ser preservados (se o volume não for excluído junto com a instância).

### 🔍 Tipos comuns de volumes EBS:
| Tipo | Características | Uso recomendado |
|------|------------------|-----------------|
| **gp3 / gp2 (SSD Geral)** | Balanceia preço e desempenho | Aplicações de uso geral |
| **io1 / io2 (SSD de alto desempenho)** | Alta IOPS e baixa latência | Bancos de dados críticos |
| **st1 (HDD de throughput)** | Alto desempenho de leitura/gravação sequencial | Grandes volumes de dados |
| **sc1 (HDD frio)** | Baixo custo | Arquivos de acesso raro |

### ✔ Benefícios:
- Armazenamento persistente independente da instância.  
- Pode ser redimensionado ou replicado sem interromper o serviço.  
- Permite criação de **snapshots** para backup e recuperação.

---

## 🧱 3. O que é uma AMI (Amazon Machine Image)?

A **AMI** é uma imagem que contém:
- O **sistema operacional** (Linux, Windows, etc.);
- As **configurações básicas** (usuários, pacotes, scripts);
- E o **estado inicial do volume raiz** da instância.

Ela serve como um **modelo para criar novas instâncias EC2** com a mesma configuração.

### 📦 Tipos de AMIs:
| Tipo de AMI | Descrição |
|--------------|------------|
| **Public AMI** | Fornecidas pela AWS ou pela comunidade. |
| **Private AMI** | Criadas pelo próprio usuário e visíveis apenas na sua conta. |
| **Marketplace AMI** | Oferecidas por terceiros, com softwares pré-instalados. |

### 💡 Quando criar uma AMI personalizada:
- Após configurar e atualizar completamente uma instância.  
- Para padronizar ambientes de desenvolvimento, teste e produção.  
- Antes de realizar grandes alterações, como atualizações de sistema.

---

## 📸 4. O que são Snapshots?

Um **Snapshot EBS** é uma cópia pontual (backup incremental) do volume EBS.  
Ele é armazenado no **Amazon S3**, garantindo alta durabilidade e segurança dos dados.

### 🧩 Como funciona:
- O primeiro snapshot copia todo o volume.  
- Os snapshots seguintes salvam **apenas as alterações** realizadas desde o último backup (incremental).  

### 🔄 Usos comuns:
- Recuperar dados em caso de falhas.  
- Criar novos volumes idênticos ao original.  
- Gerar novas AMIs a partir de volumes existentes.

---

## 🗃 5. O que é o Amazon S3?

O **Amazon S3 (Simple Storage Service)** é o serviço de armazenamento de objetos da AWS.  
Ele permite armazenar e recuperar qualquer tipo de dado (imagens, vídeos, backups, logs, etc.) com alta durabilidade e disponibilidade.

### ⚙️ Características principais:
- Armazenamento ilimitado de objetos em **buckets** (contêineres de dados).  
- **Alta durabilidade (99.999999999%)** e replicação automática entre zonas de disponibilidade.  
- **Controle de acesso** granular por políticas e permissões (IAM, ACLs e Bucket Policy).  
- Integração com **CloudFront**, **Lambda**, **Athena** e outros serviços AWS.

### 💡 Casos de uso:
- Hospedagem de sites estáticos.  
- Armazenamento de backups e logs.  
- Base de dados para análise com Big Data.  
- Integração com funções Lambda (automação).  

---

## ⚡ 6. O que é o AWS Lambda?

O **AWS Lambda** é um serviço de **computação serverless** (sem servidor), que executa código sob demanda em resposta a eventos.  
Você paga apenas pelo tempo de execução do código, sem precisar gerenciar servidores.

### 💡 Principais vantagens:
- **Sem necessidade de EC2:** a AWS gerencia toda a infraestrutura.  
- **Escalabilidade automática:** adapta a execução ao volume de eventos.  
- **Cobrança por uso:** paga apenas pelo tempo de execução.  

### 🔄 Funcionamento básico:
1. Você escreve uma função em **Python**, **Node.js**, **Java**, etc.  
2. Define um **gatilho (trigger)** — por exemplo, um upload em um bucket S3.  
3. O Lambda executa automaticamente o código em resposta a esse evento.  

### 📘 Exemplo prático:
**Evento:** Upload de uma imagem no S3  
**Ação automática (Lambda):** Redimensionar a imagem e salvar em outra pasta.  

---

## 🛡️ 7. Security Groups

Os **Security Groups** funcionam como **firewalls virtuais**, controlando o tráfego de entrada e saída das instâncias EC2.

### 🔐 Boas práticas:
- Permitir apenas portas essenciais (ex.: 22 para SSH, 80/443 para HTTP/HTTPS).  
- Restringir acessos a IPs específicos.  
- Evitar regras amplas como `0.0.0.0/0` para SSH (a não ser em ambientes de teste).

---

## 🧭 8. Fluxo Básico de Criação de Instância EC2

1. Acessar o **console AWS EC2**.  
2. Escolher uma **AMI base** (ex.: Amazon Linux 2).  
3. Selecionar o **tipo de instância** (`t2.micro` para Free Tier).  
4. Configurar **Security Group** e **par de chaves (Key Pair)**.  
5. Lançar a instância e conectar-se via **SSH**.  
6. Instalar pacotes e configurar o ambiente.  
7. Criar **Snapshot** ou **AMI personalizada** para backup ou replicação.  

---

## 📌 10. Qual é a diferença entre AMI e Snapshot?

Uma imagem de máquina da Amazon (AMI) faz o backup de um servidor inteiro, incluindo todos os volumes EBS anexados.
Um snapshot é uma cópia pontual de um determinado volume, sendo possível tirar snapshot de volumes EBS e salvá-los no armazenamento S3.

### 🔍 Comparativo: AMI vs Snapshot

| Característica | **AMI (Amazon Machine Image)** | **Snapshot EBS** |
|----------------|--------------------------------|------------------|
| **Função principal** | Modelo de instância EC2 | Backup de volume EBS |
| **Conteúdo** | Sistema operacional, configurações e metadados | Dados do volume EBS |
| **Criação** | Pode usar um snapshot como base | Criado a partir de um volume EBS existente |
| **Uso** | Lançar novas instâncias EC2 idênticas | Restaurar volumes ou criar AMIs |
| **Armazenamento** | Metadados e snapshots associados (no S3) | Armazenado no S3 de forma incremental |
| **Escopo** | Define o ambiente completo de uma instância | Copia apenas o disco (armazenamento) |
| **Visibilidade** | Pode ser pública, privada ou compartilhada | Sempre privada (por padrão) |
| **Exemplo de uso** | Criar rapidamente novos servidores prontos | Fazer backup de dados antes de atualizações |

### 🔄 Relação entre AMI e Snapshot

Uma **AMI depende de um snapshot** — ao criar uma AMI de uma instância EC2, a AWS cria automaticamente um **snapshot do volume raiz EBS** para registrar o estado atual do sistema.
