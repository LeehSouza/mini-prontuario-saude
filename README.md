# 🏥 Mini Prontuário de Saúde (Sistema de Gestão em Camadas)

## 🎯 Sobre o Projeto
Sistema modular de gestão de prontuários eletrónicos desenvolvido com foco em **arquitetura limpa, segurança de dados e proteção de informações clínicas sensíveis**. 

Este projeto simula o fluxo real de atendimento hospitalar e triagem, estruturando os dados em camadas de criticidade crescente para garantir total conformidade com a privacidade do paciente.

---

## 🏗️ Arquitetura do Sistema (Modelo em Camadas)

O sistema foi desenhado em **três camadas lógicas de segurança e acesso**:

###1️⃣ **Primeira Camada (A Porta de Entrada / Contexto)**
* **Objetivo:** Identificação rápida e rastreabilidade básica do atendimento.
* **Dados Armazenados:**
  * `nome_paciente` (Identificação civil)
  * `cpf_paciente` (Documento oficial único)
  * `enderço_paciente` (Localização)
  * `medico_responsavel` (Profissional encarregado)
  * `Hospital de Destino` (Unidade de atendimento)

### 2️⃣ **Segunda Camada (O Prontuário Operacional)** 🔒 *(Exige Chave de Acesso)*
* **Objetivo:** Gerir o internamento, estado clínico intermediário e planeamento de intervenções.
* **Dados Armazenados:**
  * `Pedido de Exames`
  * `Necessidade de Cirurgia`
  * `Diagnóstico` preliminar/geral
  * `Número do Leito`
  * `Estado do Paciente`

### 3️⃣ **Terceira Camada (O Núcleo / Cofre Ultra-Sigiloso)** 🔒🔒 *(Exige Chave de Acesso de Nível Máximo)*
* **Objetivo:** Proteger dados internos profundos, laudos cirúrgicos e rotinas críticas do hospital.
* **Dados Armazenados:**
  * `Data da Cirurgia`
  * `Andar do Exame` e `Sala do Exame`
  * `Complicações` registadas
  * `Rotina de Custódia e Cuidados do Hospital`

---

## 👥 Classes de Usuários e Permissões (Controle de Acesso)

O sistema define três atores principais com diferentes níveis de autorização:

* **👩‍💼 Recepcionista:** 
  * Permissão: **Nível 1 (Básico)**
  * Acesso exclusivo à **Primeira Camada** (Identificação e Recepção).
  
* **🩺 Enfermagem:** 
  * Permissão: **Nível 2 (Operacional / Triagem)**
  * Acesso à **Primeira** e **Segunda Camadas** (Triagem, Leito, Estado do Paciente e Exames).

* **👨‍⚕️ Médico:** 
  * Permissão: **Nível 3 (Total / Núcleo Sigiloso)** 🔒
  * Acesso a **todas as camadas**, incluindo a **Terceira Camada** (Diagnósticos profundos, Cirurgias e Complicações).

---

## 🛠️ Tecnologias Previstas
* **Linguagem:** A definir (Python / C++)
* **Controle de Versão:** Git & GitHub
