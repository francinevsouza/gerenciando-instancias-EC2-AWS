# 💭 Insights e Aprendizados — Desafio “Gerenciando Instâncias EC2 na AWS”

Durante este desafio da DIO, tive a oportunidade de praticar os conceitos fundamentais do **Amazon EC2**, **AMIs** e **Snapshots EBS**, explorando na prática o funcionamento dos principais recursos da **nuvem AWS**.

---

## 🚀 1. Primeiros Contatos com o EC2

No início do laboratório, percebi que o **Amazon EC2** é a base de praticamente tudo na AWS.  
Entender como ele funciona foi essencial para compreender o conceito de **infraestrutura como serviço (IaaS)**.  

📘 **Principais aprendizados:**
- Como criar, configurar e acessar uma instância EC2 via **SSH**.  
- A importância das **Security Groups** para o controle de acesso e segurança.  
- Diferenças entre **parar** e **encerrar** uma instância (e o impacto disso no volume EBS).  

💡 *Insight:* a AWS não é apenas sobre “subir um servidor”, mas sobre **gerenciar recursos com eficiência e segurança.**

---

## 💾 2. Compreendendo AMIs e Snapshots

Ao trabalhar com **AMIs (Amazon Machine Images)** e **Snapshots**, percebi que eles são fundamentais para garantir **continuidade e automação** de ambientes.

📘 **O que aprendi:**
- A **AMI** é como um *modelo completo* de servidor pronto para replicação.  
- O **Snapshot** é como um *backup pontual* do armazenamento (EBS).  
- Uma AMI é construída **a partir de um snapshot**, o que mostra a relação entre os dois recursos.  

💡 *Insight:* usar snapshots e AMIs corretamente reduz retrabalho, acelera implantações e melhora a recuperação em casos de falha.

---

## 🧠 3. Boas Práticas Aprendidas

Com o avanço do desafio, percebi que boas práticas fazem toda a diferença, especialmente quando pensamos em **custos e segurança**.

📘 **Pontos que mais me marcaram:**
- Utilizar **instâncias Free Tier** (como `t2.micro`) para estudar sem gerar custos.  
- Nunca deixar portas abertas para todos os IPs (`0.0.0.0/0`) em ambiente de produção.  
- Remover **volumes e snapshots antigos** que não estão em uso.  
- Adicionar **tags** a todos os recursos para organização e rastreabilidade.  

💡 *Insight:* Gerenciar infraestrutura em nuvem não é apenas criar recursos, mas **mantê-los de forma controlada e sustentável**.

---

## 🪣 4. Planejando Arquiteturas com Draw.io

Durante o estudo, aprendi a utilizar o **Draw.io** para planejar e visualizar a arquitetura AWS antes da execução.  
Esse passo me ajudou a **entender o fluxo entre os serviços** e a identificar pontos de automação.

📘 **Arquiteturas desenvolvidas:**
- **Fluxo EBS:** mostrando a relação entre EC2, volume EBS e snapshots.  
- **Fluxo S3 + Lambda:** ilustrando o processamento automático de arquivos via eventos do S3.  

💡 *Insight:* desenhar antes de implementar evita erros e ajuda a visualizar dependências entre os serviços AWS.

---

## ⚡ 5. Integração entre S3 e Lambda

Ao estudar mais sobre os serviços AWS, compreendi o poder das **arquiteturas serverless** com **AWS Lambda**.  
A integração entre **S3** e **Lambda** mostra como é possível criar soluções automatizadas sem depender de servidores tradicionais.

📘 **O que aprendi:**
- O S3 é ideal para **armazenamento de objetos** e **gatilhos de eventos**.  
- O Lambda permite **automatizar tarefas**, como processar arquivos assim que são enviados para o bucket.  

💡 *Insight:* o conceito de *“pagar apenas pelo que executa”* faz o Lambda ser uma das ferramentas mais poderosas para otimizar custos e desempenho na nuvem.

---

## 🔍 6. Desafios Enfrentados

Durante a prática, alguns desafios me ajudaram a consolidar o aprendizado:
- Entender a diferença entre **parar** e **terminar** instâncias EC2.  
- Configurar corretamente o acesso SSH sem expor a chave privada.  
- Compreender o ciclo de vida de uma **AMI** e dos **Snapshots** associados.  

💡 *Insight:* cada etapa do projeto serviu como aprendizado para compreender melhor **como a AWS interliga seus serviços de forma modular e segura.**

---

## 🧭 7. Conclusão e Próximos Passos

Esse desafio foi uma introdução essencial ao ecossistema AWS.  
Aprendi que **entender os fundamentos** (EC2, EBS, S3, AMI, Lambda) é o primeiro passo para avançar em áreas como **DevOps, Arquitetura Cloud e Automação**.

📘 **Próximos passos de estudo:**
- Explorar **EC2 Auto Scaling** e **Elastic Load Balancer (ELB)**.  
- Automatizar backups com **AWS Lambda**.  
- Criar pipelines de infraestrutura com **AWS CloudFormation**.  

💡 *Insight final:*  
> A nuvem é poderosa quando entendemos o equilíbrio entre **simplicidade, automação e boas práticas**.

---

📅 *Documento atualizado em: Outubro/2025*  
✍️ *Autora: Francine Souza*  
