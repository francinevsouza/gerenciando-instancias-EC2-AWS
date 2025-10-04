# 🧠 Boas Práticas no Gerenciamento de Instâncias EC2, AMIs e Snapshots EBS

Este documento reúne as principais boas práticas necessárias para o **gerenciamento de instâncias EC2**, **criação de AMIs** e **utilização de Snapshots EBS** na AWS.

---

## ⚙️ 1. Criação e Configuração de Instâncias EC2

### ✅ Escolha correta do tipo de instância
- Selecione o tipo de instância **de acordo com a necessidade do ambiente** (ex.: `t2.micro` para testes e estudos gratuitos).
- Sempre verifique se o tipo de instância está **elegível para o Free Tier** para evitar cobranças desnecessárias.

### 🔒 Segurança
- Nunca exponha portas desnecessárias (mantenha apenas o SSH, HTTP ou HTTPS abertos quando realmente necessário).
- Use **Security Groups** bem configurados: restrinja o acesso SSH ao seu **endereço IP** específico.
- Evite armazenar **chaves privadas (.pem)** no repositório — mantenha-as seguras localmente.

### 🌍 Localização e custo
- Escolha a **região AWS mais próxima** do seu público ou de onde você está executando os testes.
- Compare custos entre regiões antes de lançar instâncias.

---

## 💾 2. Volumes EBS e Snapshots

### 🧩 Boas práticas com volumes EBS
- **Separe o volume do sistema operacional dos volumes de dados.**
- Nomeie os volumes de forma clara (`EC2-WebServer-Volume1`).
- Monitore o uso do volume e evite volumes superdimensionados que geram custo desnecessário.

### 🪣 Snapshots
- Crie **Snapshots regulares** para garantir a recuperação em caso de falha.
- **Automatize backups** com políticas de ciclo de vida (Lifecycle Manager).
- Exclua Snapshots antigos que não são mais necessários para evitar custos acumulados.
- Sempre **teste a restauração de um snapshot** criando um volume ou instância a partir dele.

---

## 🧩 3. AMIs (Amazon Machine Images)

### 💡 Criação de AMIs
- Gere AMIs **somente após configurar e validar completamente** a instância base.
- Mantenha **descrições e tags claras**, como `AMI - Servidor Web v1.0 - 2025-10-01`.
- Antes de criar a AMI, **pare a instância** para garantir consistência no snapshot do volume raiz.

### ♻️ Manutenção
- Periodicamente **remova AMIs antigas** que não estão sendo utilizadas.
- Monitore o **armazenamento de snapshots associados às AMIs**, pois eles geram custos mesmo após exclusão da instância.

---

## 🧰 4. Gerenciamento e Automação

- Utilize o **AWS Systems Manager** para gerenciar instâncias de forma centralizada.
- Automatize tarefas repetitivas (backup, criação de AMIs) com **AWS Lambda** ou **EventBridge**.
- Armazene scripts de inicialização (User Data) versionados em repositórios Git.

---

## 🧾 5. Custos e Monitoramento

- Configure **AWS Budgets** e **CloudWatch Alarms** para alertas de uso e custo.
- Desligue ou encerre instâncias que não estão em uso.
- Habilite **Monitoramento Detalhado (Detailed Monitoring)** apenas quando necessário.
