# 🧭 Próximos Passos — Jornada de Aprendizado AWS

Após concluir o desafio **“Gerenciando Instâncias EC2 na AWS”**, percebi que dominar os fundamentos é apenas o primeiro passo dentro do vasto universo da **computação em nuvem**.  
A partir daqui, meu foco será aprofundar o conhecimento e aplicar os conceitos de forma mais automatizada, segura e escalável.

---

## ☁️ 1. Aprofundar Conhecimento em EC2

O EC2 é a base da maioria das soluções AWS, então pretendo explorar recursos mais avançados:

📘 **Objetivos de Estudo:**
- Entender **tipos de instâncias otimizadas** (compute, memory e storage).  
- Criar e gerenciar **Elastic IPs** e **Network Interfaces**.  
- Explorar **EC2 Auto Scaling** para ajustar automaticamente a capacidade.  
- Utilizar **Elastic Load Balancer (ELB)** para distribuir tráfego entre instâncias.  

🧩 **Meta prática:**  
Criar um ambiente escalável com duas instâncias EC2, Auto Scaling e ELB simulando alta disponibilidade.

---

## 💾 2. Automação de Backups e AMIs

A automação é fundamental para evitar tarefas manuais repetitivas e melhorar a segurança dos dados.

📘 **Próximos Estudos:**
- Automatizar **Snapshots EBS** com **AWS Lambda + CloudWatch Events**.  
- Criar **AMIs automaticamente** com base em instâncias configuradas.  
- Estudar **AWS Backup** e políticas de retenção automatizadas.  

🧩 **Meta prática:**  
Desenvolver uma função Lambda que crie snapshots diários e envie logs para o CloudWatch.

---

## 🎯 3. Dominar o Armazenamento S3

O Amazon S3 é essencial para praticamente todos os fluxos de dados e automação na nuvem.

📘 **Pontos de estudo:**
- Configuração de **políticas de acesso (Bucket Policies e ACLs)**.  
- Implementar **versionamento** e **lifecycle policies** para gerenciamento de custos.  
- Explorar **S3 Static Website Hosting** para hospedar sites estáticos.  
- Aprender sobre **S3 Glacier** para arquivamento e backups de longo prazo.  

🧩 **Meta prática:**  
Hospedar um portfólio estático pessoal no S3, com domínio personalizado e HTTPS via CloudFront.

---

## ⚙️ 4. Funções Serverless com AWS Lambda

O **AWS Lambda** é uma das ferramentas mais poderosas para automação e arquitetura *serverless*.

📘 **Objetivos:**
- Aprender a escrever e implantar funções Lambda em **Python** ou **Node.js**.  
- Conectar Lambda a **gatilhos do S3**, **eventos CloudWatch** e **API Gateway**.  
- Monitorar logs e métricas com **CloudWatch Logs**.  

🧩 **Meta prática:**  
Criar uma função Lambda que processe automaticamente imagens enviadas a um bucket S3 (redimensionamento, por exemplo).

---

## 🧱 5. Infraestrutura como Código (IaC)

Gerenciar infraestrutura manualmente é bom para aprendizado, mas a automação é essencial no mundo real.  
A **Infraestrutura como Código (IaC)** é o próximo passo natural.

📘 **Ferramentas para aprender:**
- **AWS CloudFormation** – modelo nativo da AWS para descrever e implantar recursos.  
- **Terraform** – alternativa open source para gerenciar múltiplas nuvens.  

🧩 **Meta prática:**  
Criar um template CloudFormation para provisionar automaticamente:
- Uma instância EC2  
- Um bucket S3  
- Um grupo de segurança configurado  

---

## 🛡️ 6. Segurança e Custos na AWS

Conforme os projetos crescem, segurança e otimização de custos se tornam prioridade.

📘 **Tópicos de foco:**
- Uso de **IAM Roles e Policies** para controle de permissões.  
- Configuração de **CloudTrail** para auditoria e rastreabilidade.  
- Monitoramento de custos com **AWS Cost Explorer e Budgets**.  

🧩 **Meta prática:**  
Criar uma política IAM personalizada para o uso de EC2 e Lambda, aplicando o princípio do “menor privilégio”.

---

## 📈 7. Próximos Desafios e Certificações

Para consolidar o aprendizado e evoluir na carreira, pretendo seguir estudando com foco em certificações e projetos aplicados.

📘 **Roteiro sugerido:**
1. **AWS Certified Cloud Practitioner** (conceitos gerais da AWS).  
2. **AWS Certified Solutions Architect – Associate** (arquitetura e boas práticas).  
3. Participar de novos **labs práticos da DIO** e simulações no **AWS Skill Builder**.  

🧩 **Meta prática:**  
Iniciar um projeto autoral: construir e documentar um sistema completo na AWS com EC2, S3, Lambda e CloudFormation.

---

## 🧠 Conclusão

Finalizar o desafio foi um passo importante para consolidar a base em AWS.  
A partir daqui, meu objetivo é:
> **Unir teoria, prática e automação para construir soluções escaláveis e seguras na nuvem.**

---

📅 *Documento atualizado em: Outubro/2025*  
✍️ *Autora: Francine Souza*  
