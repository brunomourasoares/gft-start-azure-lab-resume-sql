# Objetivo do Desafio

Este laboratório tem como objetivo praticar o processo de configuração de uma instância de Banco de Dados na plataforma Microsoft Azure. Como entregável, o desafio proposto é a criação de um repositório contendo resumos, anotações e dicas sobre o uso da Azure, servindo como material de apoio para estudos e futuras implementações.

---

## 1. Visão Geral dos Serviços de Banco de Dados no Azure

- Azure SQL Database  
  Instância PaaS com alta disponibilidade integrada e escalabilidade automática.

- Azure SQL Managed Instance  
  Compatibilidade próxima do SQL Server on-premises, ideal para migrações lift-and-shift.

- Azure Database for PostgreSQL / MySQL / MariaDB  
  Serviços gerenciados open-source, opções Single Server e Flexible Server.

- Cosmos DB  
  Banco multimodelo, latência ultrabaixa e escalabilidade global.

---

## 2. Planejamento Pré-Implementação

1. Definir requisitos de capacidade  
   - Volume de dados estimado  
   - Número de transações por segundo  

2. Escolher tipo de serviço  
   - PaaS vs Managed Instance vs Open-Source gerenciado  

3. Arquitetura de rede  
   - VNet Integration  
   - Private Endpoints para isolamento  

4. Requisitos de segurança e compliance  
   - Firewall e regras de IP  
   - Autenticação (Azure AD vs SQL Auth)  

---

## 3. Passo a Passo: Criando uma Instância de Azure SQL Database

1. Acesse o portal do Azure.  
2. Selecione “Criar recurso” > “Banco de dados” > “Azure SQL Database”.  
3. Defina assinatura, grupo de recursos e nome da instância.  
4. Escolha modelo de compra:  
   - DTU (Database Transaction Unit)  
   - vCore (compute e storage separados)  
5. Selecione camada de serviço: Basic, Standard ou Premium.  
6. Configure rede:  
   - Ative “Allow Azure services…” ou configure Virtual Network.  
7. Defina autenticação:  
   - Servidor principal e credenciais de acesso  
   - Habilite Azure Active Directory se necessário  
8. Revise e crie.

---

## 4. Anotações Essenciais

- Escalabilidade  
  Ajuste de DTUs/vCores sem downtime perceptível em muitas camadas.

- Alta Disponibilidade  
  Zone-redundant deployment para resiliência contra falhas de zona.

- Backups  
  Automáticos por padrão, retenção configurável de 7 a 35 dias.

- Monitoramento  
  Use Azure Monitor e Query Performance Insight para identificar gargalos.

- Custo  
  Utilize o Azure Pricing Calculator antes de provisionar para evitar surpresas.

---

## 5. Dicas Práticas

- Configure alertas de uso de CPU, DTU/vCore e storage para ação proativa.  
- Separe ambientes (desenvolvimento, homologação e produção) em grupos de recursos distintos.  
- Utilize Azure CLI ou PowerShell para automatizar provisionamento e escalonamento.  
- Empregue templates ARM ou Bicep para versionar e replicar configurações de forma confiável.  
- Habilite Always Encrypted e Transparent Data Encryption (TDE) para reforçar a proteção de 
