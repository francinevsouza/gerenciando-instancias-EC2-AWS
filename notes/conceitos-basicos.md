# 📌 Conceitos Básicos - EC2 na AWS

## O que é EC2?
Amazon EC2 (Elastic Compute Cloud) é um serviço da AWS que permite criar e gerenciar máquinas virtuais na nuvem.  
Cada máquina é chamada de **instância**, podendo ser configurada de acordo com a necessidade.
No modelo Cloud, uma EC2 é do tipo IAAS, ou seja, quando criamos uma EC2 estamos utilizando o tipo Infraestrutura como Serviço.

---

## Tipos de Instâncias
- **t2.micro:** Uso geral, baixo custo, elegível ao Free Tier.  
- **m5.large:** Mais memória, indicado para bancos de dados.  
- **c5.large:** Otimizado para CPU, indicado para processamento intenso.  

---

## AMI (Amazon Machine Image)
- É a "imagem" usada para inicializar uma instância.  
- Contém sistema operacional e pacotes básicos.  
- Exemplos: Amazon Linux, Ubuntu, Windows Server.

---

## EBS (Amazon Elastic Block Store)
- É um serviço para fornecer armazenamento em bloco fiável (também conhecido como volumes ou discos rígidos).
- Foi concebido para ser utilizado com instâncias do Amazon Elastic Compute Cloud (EC2).

---

## Snapshot EBS
- É um serviço de backup nativo do AWS.
- Faz backup dos volumes do EBS em um determinado momento.
- É possível configurar a frequência com que os snapshots são tirados.

---

## Quanto custam os Snapshots do AWS?
Os snapshots do EBS são oferecidos a diferentes custos em diferentes regiões.

---

## Qual é a diferença entre AMI e Snapshot?
Uma imagem de máquina da Amazon (AMI) faz o backup de um servidor inteiro, incluindo todos os volumes EBS anexados.
Um snapshot é uma cópia pontual de um determinado volume, sendo possível tirar snapshot de volumes EBS e salvá-los no armazenamento S3.

---

## Amazon S3
- O Amazon S3 (Amazon Simple Storage Service) é um serviço de armazenamento de objetos em nuvem oferecidos pela AWS.
- É ideal para armazenar, organizar e recuperar grandes volumes de dados de forma segura e escalável.
- Possui algumas classes de storages onde conseguimos economizar nos custos.

---

## Lambda Function
- É uma função que permite executar código sem a necessidade de gerenciar servidores.
- É amplamente usada para criar aplicações escaláveis e baseadas em eventos.
- Pode ser configurado para redimensionar imagens automaticamente quando um arquivo é enviado para um bucket no Amazon S3.
