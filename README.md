# FOCUS-TABELA-FINOPS-X-SP
Referência das 57 colunas da FOCUS Specification v1.2  
Padronização de dados multi-cloud para FinOps.

---

## 🔗 Links importantes
- **Column Library Oficial:** [https://focus.finops.org/focus-columns/](https://focus.finops.org/focus-columns/)
- **FOCUS Driver — meu guia completo com explicações, contexto e casos reais:** [https://github.com/izadorasobral/focus-drive](https://github.com/izadorasobral/focus-drive)

---

## 📘 Sobre este repositório
Este repositório é uma referência rápida e prática das **57 colunas obrigatórias, condicionais e opcionais** da FOCUS Specification v1.2.  
Serve como apoio para estudos, consultas, auditorias e construção de pipelines FinOps.

Se você trabalha com AWS, Azure, GCP ou Oracle Cloud, este padrão elimina a dor de cabeça de “traduzir” cada provedor e permite construir processos consistentes, dashboards confiáveis e governança real.

---

##  Legenda de Nível (Feature Level)
🔴 **Mandatory** — obrigatório  
🟡 **Conditional** — obrigatório se aplicável  
🟢 **Optional** — recomendado, mas não bloqueante  

---

#  1. Charge & Invoicing (Cobrança e Fatura)

| Campo | Nível | Explicação |
|---|---|---|
| InvoiceId | 🔴 | ID da fatura real. (Novo v1.2) |
| InvoiceIssuer | 🔴 | Quem emite a fatura. |
| ChargeCategory | 🔴 | Usage, Purchase, Tax, Credit. |
| ChargeClass | 🔴 | Tipo da linha de cobrança. |
| ChargeDescription | 🔴 | Descrição da cobrança. |
| ChargeFrequency | 🔴 | OneTime, Recurring, UsageBased. |
| ChargePeriodStart | 🔴 | Início da cobrança. |
| ChargePeriodEnd | 🔴 | Fim da cobrança. |
| BillingPeriodStart | 🔴 | Início do ciclo de faturamento. |
| BillingPeriodEnd | 🔴 | Fim do ciclo de faturamento. |

---

#  2. Account & Provider (Conta e Provedor)

| Campo | Nível | Explicação |
|---|---|---|
| Provider | 🔴 | Provedor: AWS, Azure, GCP, OCI. |
| Publisher | 🟢 | Editor do serviço. |
| BillingAccountId | 🔴 | Conta pagadora. |
| BillingAccountName | 🟢 | Nome da conta. |
| BillingAccountType | 🟢 | Tipo da conta. (Novo v1.2) |
| SubAccountId | 🔴 | Subconta/projeto/assinatura. |
| SubAccountName | 🟢 | Nome da subconta. |
| SubAccountType | 🟢 | Tipo da subconta. |

---

#  3. Cost & Pricing (Custos e Preços)

| Campo | Nível | Explicação |
|---|---|---|
| BilledCost | 🔴 | Valor faturado. |
| EffectiveCost | 🔴 | Custo amortizado/efetivo. |
| ListCost | 🟢 | Custo de tabela. |
| ContractedCost | 🟢 | Custo após contrato/desconto. |
| BillingCurrency | 🔴 | Moeda da fatura. |
| PricingCurrency | 🟡 | Moeda do contrato. |
| PricingCategory | 🔴 | OnDemand, Commitment, Free. |
| ListUnitPrice | 🟢 | Preço de tabela por unidade. |
| ContractedUnitPrice | 🟢 | Preço negociado por unidade. |
| PricingCurrencyEffectiveCost | 🟢 | Custo efetivo na moeda original. |
| PricingCurrencyListUnitPrice | 🟢 | Preço lista na moeda original. |
| PricingCurrencyContractedUnitPrice | 🟢 | Preço negociado na moeda original. |

---

#  4. Resource & Service (Recurso e Serviço)

| Campo | Nível | Explicação |
|---|---|---|
| RegionId | 🔴 | Identificador da região. |
| RegionName | 🟢 | Nome da região. |
| AvailabilityZone | 🟢 | Zona de disponibilidade. |
| ResourceId | 🟢 | ID do recurso. |
| ResourceName | 🟢 | Nome do recurso. |
| ResourceType | 🟢 | Tipo do recurso. |
| ServiceCategory | 🔴 | Compute, Database, Network… |
| ServiceName | 🔴 | Nome do serviço. |
| ServiceSubcategory | 🟢 | Subcategoria. |

---

#  5. SKU & Usage (Consumo)

| Campo | Nível | Explicação |
|---|---|---|
| SkuId | 🔴 | ID único da SKU. |
| SkuMeter | 🟢 | Métrica técnica da SKU. |
| SkuPriceId | 🟢 | ID do preço. |
| SkuPriceDetails | 🟢 | JSON com detalhes (tier, spot). (Novo v1.2) |
| ConsumedQuantity | 🔴 | Quantidade consumida. |
| ConsumedUnit | 🔴 | Unidade consumida. |
| PricingQuantity | 🟢 | Quantidade tarifada. |
| PricingUnit | 🟢 | Unidade tarifada. |

---

#  6. Commitment Discount (Descontos)

| Campo | Nível | Explicação |
|---|---|---|
| CommitmentDiscountId | 🟡 | ID do plano/compromisso. |
| CommitmentDiscountStatus | 🟡 | Used / Unused. |
| CommitmentDiscountType | 🟡 | Spend / Usage. |
| CommitmentDiscountCategory | 🟡 | Categoria do desconto. |
| CommitmentDiscountName | 🟢 | Nome do plano. |
| CommitmentDiscountQuantity | 🟢 | Quantidade aplicada. |
| CommitmentDiscountUnit | 🟢 | Unidade. |
| CapacityReservationId | 🟢 | ID da reserva. |
| CapacityReservationStatus | 🟢 | Status. |

---

#  7. Metadata (Metadados)

| Campo | Nível | Explicação |
|---|---|---|
| Tags | 🟢 | Tags em JSON. |
| x_CustomField | 🟢 | Campos customizados. |

---

#  Regras Técnicas da FOCUS Specification

| Atributo | ✔️ Aceito | ❌ Não permitido |
|---|---|---|
| Formato dos nomes | PascalCase | snake_case, espaços, acentos |
| Datas | ISO 8601 UTC | DD/MM/AAAA |
| Valores nulos | NULL | "", "Not set", 0 |
| Moedas | USD, BRL | $, R$ |
| Unidades | GB, MB, vCPU | Gigabytes, GBs |
| JSON | simples e válido | estruturas aninhadas gigantes |

---

# 📘 Meu guia completo — FOCUS Driver  
Explico a FOCUS Specification com contexto, casos reais, exercícios, diagramas e comparações entre versões.  
[https://github.com/izadorasobral/focus-drive](https://github.com/izadorasobral/focus-drive)

<br>

---
---

<br>

#  FOCUS-TABELA-FINOPS-X-SP
Reference for all 57 columns of the FOCUS Specification v1.2  
A multi-cloud cost and usage normalization standard for FinOps.

---

## 🔗 Important Links
- **Official Column Library:** [https://focus.finops.org/focus-columns/](https://focus.finops.org/focus-columns/)
- **FOCUS Driver — my complete companion guide:** [https://github.com/izadorasobral/focus-drive](https://github.com/izadorasobral/focus-drive)

---

##  About this repository
This repository is a fast and practical reference for all **57 mandatory, conditional, and optional fields** of FOCUS Specification v1.2.

It's built for engineers, analysts, and FinOps practitioners who need consistent and comparable multi-cloud cost data.

Perfect for pipelines, dashboards, audits, and cloud cost governance.

---

##  Feature Level Legend
🔴 **Mandatory** — required  
🟡 **Conditional** — required if applicable  
🟢 **Optional** — recommended but not blocking  

---

#  1. Charge & Invoicing

| Field | Level | Description |
|---|---|---|
| InvoiceId | 🔴 | Actual invoice ID. (New in v1.2) |
| InvoiceIssuer | 🔴 | Entity issuing the invoice. |
| ChargeCategory | 🔴 | Usage, Purchase, Tax, Credit. |
| ChargeClass | 🔴 | Type of charge line. |
| ChargeDescription | 🔴 | Description of the charge. |
| ChargeFrequency | 🔴 | OneTime, Recurring, UsageBased. |
| ChargePeriodStart | 🔴 | Charge start. |
| ChargePeriodEnd | 🔴 | Charge end. |
| BillingPeriodStart | 🔴 | Billing cycle start. |
| BillingPeriodEnd | 🔴 | Billing cycle end. |

---

#  2. Account & Provider

| Field | Level | Description |
|---|---|---|
| Provider | 🔴 | Cloud provider (AWS, Azure, GCP, OCI). |
| Publisher | 🟢 | Service publisher. |
| BillingAccountId | 🔴 | Payer/billing account. |
| BillingAccountName | 🟢 | Billing account name. |
| BillingAccountType | 🟢 | Account type. (New v1.2) |
| SubAccountId | 🔴 | Subscription/project/account ID. |
| SubAccountName | 🟢 | Subaccount name. |
| SubAccountType | 🟢 | Subaccount type. |

---

#  3. Cost & Pricing

| Field | Level | Description |
|---|---|---|
| BilledCost | 🔴 | Invoiced cost. |
| EffectiveCost | 🔴 | Amortized/effective cost. |
| ListCost | 🟢 | List cost. |
| ContractedCost | 🟢 | Contracted/discounted cost. |
| BillingCurrency | 🔴 | Invoice currency. |
| PricingCurrency | 🟡 | Contract currency. |
| PricingCategory | 🔴 | OnDemand, Commitment, Free. |
| ListUnitPrice | 🟢 | List unit price. |
| ContractedUnitPrice | 🟢 | Contracted unit price. |
| PricingCurrencyEffectiveCost | 🟢 | Effective cost in original currency. |
| PricingCurrencyListUnitPrice | 🟢 | List price in original currency. |
| PricingCurrencyContractedUnitPrice | 🟢 | Contracted price in original currency. |

---

#  4. Resource & Service

| Field | Level | Description |
|---|---|---|
| RegionId | 🔴 | Region identifier. |
| RegionName | 🟢 | Region name. |
| AvailabilityZone | 🟢 | Availability zone. |
| ResourceId | 🟢 | Resource ID. |
| ResourceName | 🟢 | Resource name. |
| ResourceType | 🟢 | Resource type. |
| ServiceCategory | 🔴 | Compute, Database, Network… |
| ServiceName | 🔴 | Service name. |
| ServiceSubcategory | 🟢 | Service subcategory. |

---

#  5. SKU & Usage

| Field | Level | Description |
|---|---|---|
| SkuId | 🔴 | Unique SKU ID. |
| SkuMeter | 🟢 | Technical meter name. |
| SkuPriceId | 🟢 | Price ID. |
| SkuPriceDetails | 🟢 | JSON pricing details (tier, spot). |
| ConsumedQuantity | 🔴 | Amount consumed. |
| ConsumedUnit | 🔴 | Consumption unit. |
| PricingQuantity | 🟢 | Billed quantity. |
| PricingUnit | 🟢 | Billed unit. |

---

#  6. Commitment Discount

| Field | Level | Description |
|---|---|---|
| CommitmentDiscountId | 🟡 | Commitment/plan ID. |
| CommitmentDiscountStatus | 🟡 | Used / Unused. |
| CommitmentDiscountType | 🟡 | Spend / Usage. |
| CommitmentDiscountCategory | 🟡 | Discount category. |
| CommitmentDiscountName | 🟢 | Plan name. |
| CommitmentDiscountQuantity | 🟢 | Quantity applied. |
| CommitmentDiscountUnit | 🟢 | Unit. |
| CapacityReservationId | 🟢 | Capacity reservation ID. |
| CapacityReservationStatus | 🟢 | Status. |

---

#  7. Metadata

| Field | Level | Description |
|---|---|---|
| Tags | 🟢 | Tags in JSON. |
| x_CustomField | 🟢 | Custom fields. |

---

#  Technical Rules

| Attribute | ✔️ Accepted | ❌ Not allowed |
|---|---|---|
| Naming | PascalCase | snake_case, spaces, accents |
| Dates | ISO 8601 UTC | DD/MM/YYYY |
| Nulls | NULL | "", "Not set", 0 |
| Currency | USD, BRL | $, R$ |
| Units | GB, MB, vCPU | GBs, Gigabytes |
| JSON | Valid simple structure | Giant nested objects |

---

#  My companion guide — FOCUS Driver  
A practical guide explaining the FOCUS Specification with context, diagrams, use cases and version comparisons.  
[https://github.com/izadorasobral/focus-drive](https://github.com/izadorasobral/focus-drive)
