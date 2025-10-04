# 🚀 Gerenciando Instâncias EC2 na AWS (Desafio DIO)

## 📌 Descrição  
Este projeto faz parte do desafio da [DIO - Digital Innovation One](https://www.dio.me/), no qual foi proposto praticar conceitos fundamentais de **gerenciamento de instâncias EC2 na AWS**, com foco em criação e utilização de **AMIs (Amazon Machine Images)** e **Snapshots EBS**, através da criação de desenhos de arquiteturas utilizando a ferramenta [draw.io](https://www.drawio.com/). 

---

## 🎯 Objetivos do Desafio
- Compreender como funciona a criação e uso de imagens **AMI**
- Compreender como funcionam os **Snapshots EBS**
- Criar o desenho de uma arquitetura com **instância EC2**
- Criar o desenho de uma arquitetura com **S3** e **Lambda Function**
- Utilizar o site [draw.io](https://www.drawio.com/) para criar o desenho das arquiteturas propostas

---

## 🛠️ Tecnologias e Serviços Utilizados
- **draw.io** → Aplicativo de diagramação online
 
---

## 📂 Estrutura do Repositório
- [`/notes/conceitos-basicos.md`](notes/conceitos-basicos.md) → Definições essenciais sobre EC2, AMI e EBS   
- [`/notes/boas-praticas.md`](notes/boas-praticas.md) → Recomendações de uso seguro e econômico da AWS  
- [`/notes/insights.md`](notes/insights.md) → Reflexões e aprendizados durante o laboratório  
- [`/notes/proximos-passos.md`](notes/proximos-passos.md) → Sugestões para expandir os estudos em AWS  
- [`/notes/arquiteturas.md`](notes/arquiteturas.md) → Diagramas criados no draw.io sobre fluxos de EBS e integração de serviços  

---

## 📸 Demonstração

- Arquitetura Fluxo EBS
<img width="812" height="578" alt="Arquitetura AWS com EC2 drawio" src="https://github.com/user-attachments/assets/11592f12-3d58-4d3a-a1a9-5f4bde2e191f" /> 

>>>

- Arquitetura Fluxo S3 + Lambda
<img width="644" height="282" alt="Arquitetura AWS com S3 e Lambda Function drawio" src="https://github.com/user-attachments/assets/ef78d555-d598-4ecc-b569-5b2c1db574d4" /> 

---

## 🏗️ Arquiteturas AWS (draw.io)  
Durante o estudo, foram criados diagramas para entender melhor o fluxo dos serviços:  
- [Arquitetura EBS](notes/arquiteturas.md#arquitetura-de-fluxo-ebs)  
- [Arquitetura S3 + Lambda](notes/arquiteturas.md#arquitetura-de-integração-s3--lambda)  

---

## 📚 Aprendizados
- Entendi a diferença entre **AMI** e **Snapshot**  
- Aprendi a criar **Snapshots** de volumes EBS para backup e recuperação  
- Vi como a **AMI** facilita a replicação de instâncias com a mesma configuração
- Entendi a importância da criação dos desenhos de arquitetura para o bom planejamento de um projeto AWS 
- Reforcei boas práticas de segurança e gestão de custos na AWS  

---

## 🔗 Referências
- [Documentação AWS EC2](https://docs.aws.amazon.com/ec2/)  
- [Documentação Amazon EBS](https://docs.aws.amazon.com/ebs/)
- [Documentação Amazon S3](https://docs.aws.amazon.com/s3/)  
- [Digital Innovation One (DIO)](https://www.dio.me/)  
