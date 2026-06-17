# ⚡ EV ChargeOps — Gestão Inteligente de Recarga Coletiva

> **Monitoramento • Rateio Automatizado • Previsão de Demanda • Inteligência Operacional**

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![API](https://img.shields.io/badge/GoodWe-SEMS%20API-green?style=for-the-badge)
![IA](https://img.shields.io/badge/Intelig%C3%AAncia-Artificial-orange?style=for-the-badge)
![FIAP](https://img.shields.io/badge/Enterprise-Challenge-red?style=for-the-badge)

---

## 🌌 Visão geral

O **EV ChargeOps** é um sistema de gestão operacional desenvolvido para o **Enterprise Challenge 2026 (GoodWe + FIAP)**. Nosso objetivo é transformar sessões de recarga de veículos elétricos (VEs) em dados estruturados e inteligência acionável para condomínios e edifícios corporativos.

Em infraestruturas compartilhadas, a gestão da recarga é um desafio logístico e elétrico. O EV ChargeOps atua como a camada de inteligência entre o carregador **GoodWe HCA G2** e a administração do edifício, resolvendo problemas de rateio, sobrecarga de rede e experiência do usuário.

### O que o sistema entrega:
* 🔌 Monitoramento em tempo real via API GoodWe e Modbus TCP;
* 🧾 Rateio automático de custos por unidade consumidora;
* ⚡ Gestão dinâmica de carga para evitar sobrecarga (Load Balancing);
* 🧠 Previsão de demanda energética com IA;
* 💬 Chatbot (NLP) para consulta de faturamento e status;
* 🚨 Alertas inteligentes de falha ou comportamento atípico.

---

## 📊 Arquitetura de dados

O sistema coleta dados de telemetria diretamente do carregador GoodWe HCA G2.

### Principais pontos de dados monitorados
| Dado | Fonte | Função |
| :--- | :--- | :--- |
| `power` | API/Modbus | Potência instantânea da recarga |
| `energy` | API/Modbus | Volume total de energia entregue (kWh) |
| `status` | API | Estado da sessão (idle, charging, fault) |
| `soc` | BMS/Inversor | Nível de carga (quando aplicável) |

---

# 🚀 Proposta de valor

O EV ChargeOps foi projetado para eliminar o atrito entre moradores e síndicos. 

**O síndico ganha:**
* Transparência total no rateio;
* Segurança operacional da rede elétrica do condomínio;
* Relatórios automáticos de gestão.

**O morador ganha:**
* Autonomia via App para recargas;
* Histórico detalhado de consumo;
* Tarifação justa (Pay-per-use).

---

# ⚙️ Como o EV ChargeOps funciona

Fluxo lógico do sistema:

```text```
Carregador HCA G2 
        ↓
Gateway Modbus/API
        ↓
Servidor Backend (Python)
        ↓
Motor de Rateio e IA
        ↓
Dashboard & Chatbot

EVChargeOps/
│
├── data/
│   └── rateio_mensal.json
│
├── docs/
│   ├── arquitetura.png
│   └── especificacoes_goodwe.pdf
│
├── src/
│   ├── integraçao_api.py
│   ├── motor_rateio.py
│   ├── predicao_ia.py
│   └── chatbot_sindico.py
│
├── README.md
└── requirements.txt


🤖 Inteligência Artificial
A IA não é decorativa. Ela é o motor de otimização:

Previsão de Demanda: Utilizamos modelos de regressão para antecipar os picos de uso do condomínio, ajustando a potência disponível para cada estação de recarga.

Síndico Virtual (NLP): Um agente conversacional que processa comandos em linguagem natural (ex: "Qual o gasto da unidade 202?") traduzindo dados brutos da API em informações gerenciais.

🚨 Gestão de Falhas e SRE

Como um projeto focado em SRE (Site Reliability Engineering), o EV ChargeOps prioriza:

Consistência: Logs de sessão persistidos localmente em caso de queda de internet.

Disponibilidade: Monitoramento proativo do status do hardware via código de erro da GoodWe (verificar AC Fault Bytes).

Escalabilidade: Arquitetura desacoplada pronta para suportar a adição de múltiplos carregadores.

Integrante	RM	Email

Vinicius Pelogia	RM 572675	vinipelogia@gmail.com
David Tomaz	RM 570348	daviddesatomaz@gmail.com
Eric Yuiti	RM 573495	Eric.nissi@gmail.com
Antuny Menezes	RM 572107	antunyyt@gmail.com

🔗 Referências
Resolução Normativa ANEEL nº 1.000/2021.

Manual do Usuário - Carregador CA Série HCA G2 (GoodWe).

Protocolo Modbus HCA G2 - GoodWe.

EV ChargeOps — Recarregando com Inteligência, Gestão e Segurança.
