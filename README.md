# FOCUS-TABELA-FINOPS-X-SP 

> **Referência Técnica:** FinOps Open Cost & Usage Specification (FOCUS) **v1.2**

---

##  Dicionário de Dados (FOCUS v1.2)

A tabela abaixo lista todas as 57 colunas obrigatórias e opcionais da especificação.

| Campo (Column ID) | Uso / Tipo | Exemplo / Explicação |
| :--- | :--- | :--- |
| **`AvailabilityZone`** | Zona técnica | `us-east-1a` |
| **`BilledCost`** | Valor faturado | `67.95` |
| **`BillingAccountId`** | ID da conta | `123456789012` |
| **`BillingAccountName`** | Nome da conta | `Empresa X - Conta Principal` |
| **`BillingAccountType`** | Tipo de conta | `Payer Account`, `MCA` (**Novo 1.2**) |
| **`BillingCurrency`** | Moeda da fatura | `USD`, `BRL` |
| **`BillingPeriodEnd`** | Fim faturamento | `2025-06-30T23:59:59Z` |
| **`BillingPeriodStart`** | Início faturamento | `2025-06-01T00:00:00Z` |
| **`CapacityReservationId`** | ID da reserva | `cr-123456` (Se preenchido, é reserva) |
| **`CapacityReservationStatus`** | Status da reserva | `Unused`, `Used` |
| **`ChargeCategory`** | Tipo de linha | `Usage`, `Purchase`, `Tax` |
| **`ChargeClass`** | Classe técnica | `Correction`, `Total`, `Rounding` |
| **`ChargeDescription`** | Descrição | `Compute Hours for t3.large` |
| **`ChargeFrequency`** | Frequência | `OneTime`, `Recurring`, `UsageBased` |
| **`ChargePeriodEnd`** | Fim cobrança | `2025-06-15T23:59:59Z` |
| **`ChargePeriodStart`** | Início cobrança | `2025-06-15T00:00:00Z` |
| **`CommitmentDiscountCategory`** | Categoria desc. | `Spend`, `Usage` (ex: SP vs RI) |
| **`CommitmentDiscountId`** | ID do desconto | `ri-54321` |
| **`CommitmentDiscountName`** | Nome do plano | `Compute Savings Plan` |
| **`CommitmentDiscountQuantity`** | Qtd do desconto | `10` |
| **`CommitmentDiscountStatus`** | Status | `Active` |
| **`CommitmentDiscountType`** | Tipo de desc. | `Spend`, `Usage` |
| **`CommitmentDiscountUnit`** | Unidade desc. | `USD`, `Hours` |
| **`ConsumedQuantity`** | Qtd consumida | `120.00` |
| **`ConsumedUnit`** | Unidade consumo | `Hours`, `GB` |
| **`ContractedCost`** | Custo negociado | `67.50` |
| **`ContractedUnitPrice`** | Preço negociado | `2.70` |
| **`EffectiveCost`** | Custo amortizado | `64.20` (Essencial para FinOps) |
| **`InvoiceId`** | ID da fatura | `INV-2025-06-7890` (**Novo 1.2**) |
| **`InvoiceIssuer`** | Emissor | `Google Ireland`, `AWS Inc.` |
| **`ListCost`** | Custo de lista | `75.00` |
| **`ListUnitPrice`** | Preço de lista | `3.00` |
| **`PricingCategory`** | Categoria preço | `OnDemand`, `Commitment` |
| **`PricingCurrency`** | Moeda original | `USD` (Se contrato for em dólar) |
| **`PricingCurrencyContractedUnitPrice`**| Preço neg. (Moeda Orig) | `2.70` (**Novo 1.2**) |
| **`PricingCurrencyEffectiveCost`** | Custo efetivo (Moeda Orig)| `67.50` (**Novo 1.2**) |
| **`PricingCurrencyListUnitPrice`** | Preço lista (Moeda Orig) | `3.00` (**Novo 1.2**) |
| **`PricingQuantity`** | Qtd precificada | `25` |
| **`PricingUnit`** | Unidade preço | `Hours`, `GiB` |
| **`Provider`** | Provedor | `AWS`, `Azure`, `Google` |
| **`Publisher`** | Editor do serviço | `Microsoft`, `MarketplaceVendorX` |
| **`RegionId`** | ID Região | `us-east-1` |
| **`RegionName`** | Nome Região | `Norte da Virgínia` |
| **`ResourceId`** | ID Recurso | `i-12345abcdef` |
| **`ResourceName`** | Nome Recurso | `prod-db-01` |
| **`ResourceType`** | Tipo Recurso | `Compute Instance`, `Storage Bucket` |
| **`ServiceCategory`** | Categoria Macro | `Compute`, `Database` |
| **`ServiceName`** | Serviço | `AmazonEC2`, `Virtual Machines` |
| **`ServiceSubcategory`** | Subcategoria | `On-Demand`, `Standard Storage` |
| **`SkuId`** | ID do SKU | `DZH218-0043` |
| **`SkuMeter`** | Métrica SKU | `Standard IO` (Substitui `x_SkuMeterName`) |
| **`SkuPriceDetails`** | Detalhes Preço (JSON) | `{"tier":"Free", "spot":true}` (**Novo 1.2**) |
| **`SkuPriceId`** | ID Preço SKU | `PRICE-12345` |
| **`SubAccountId`** | ID Subconta | `123456` |
| **`SubAccountName`** | Nome Subconta | `Projeto Alpha` |
| **`SubAccountType`** | Tipo Subconta | `Project`, `Subscription` (**Novo 1.2**) |
| **`Tags`** | Tags (JSON) | `{"Env":"Prod"}` |
| **`x_CustomField`** | Campos extras | `x_cost_center_code` |

---

##  Legenda & Regras de Formatação

Para garantir a conformidade com a especificação FOCUS, os dados devem seguir estritamente os padrões abaixo.

### 🔹 Formato de Dados

* **Datas e Horários:**
    * Devem seguir o padrão **ISO 8601** (UTC).
    * Exemplo: `2025-06-30T23:59:59Z`
* **Tags e Metadados:**
    * Devem ser representados como **JSON válido**.
    * Exemplo: `{"Project":"Marketing","CostCenter":"IT"}`
* **Moedas:**
    * Devem utilizar códigos de 3 letras conforme **ISO 4217**.
    * Exemplos: `USD`, `EUR`, `BRL`
    * *Virtuais:* `DBU`, `Credits`, `Tokens`
* **Identificadores Técnicos (IDs):**
    * Devem ser alfanuméricos, únicos e conter prefixos identificáveis.
    * Exemplos: `INV-2025-06-7890`, `i-12345abcdef`
* **Nomes de Regiões e Provedores:**
    * `RegionId`: sempre em minúsculas, sem espaços (ex: `us-east-1`)
    * `RegionName`: com capitalização legível (ex: `Norte da Virgínia`)
    * `Provider`: nomes oficiais (ex: `AWS`, `Azure`, `Snowflake`)
* **Valores Numéricos:**
    * Custos: recomendado até 2 casas decimais (ex: `67.95`)
    * Quantidades: até 3 casas decimais (ex: `10.125`)
* **Campos JSON:**
    * Chaves e valores entre aspas duplas `""`.
    * Exemplo: `{"Environment":"Prod","Owner":"FinOps Team"}`

---

## 🔧 Regras Técnicas da Especificação

Guia rápido do que é permitido (✅) e proibido (❌) ao implementar o FOCUS.

| Atributo | ✅ Regras e Padrões (Permitido) | ❌ Proibido / Exceções |
| :--- | :--- | :--- |
| **Column Naming** | • PascalCase (ex: `ResourceId`)<br>• Sem acrônimos (exceto `Id`, `Sku`)<br>• Alfanumérico<br>• Custom columns com prefixo `x_` | • Espaços em nomes<br>• Snake_case (exceto `x_`)<br>• Caracteres especiais (`@`, `#`) |
| **Currency Code** | • Códigos de 3 letras (ex: `BRL`)<br>• Conforme ISO 4217 | • Símbolos (`$`)<br>• Por extenso (`Dólar`) |
| **Date/Time** | • ISO 8601 UTC: `YYYY-MM-DDTHH:mm:ssZ`<br>• Aceita offset: `−03:00` | • Formatos locais (`DD/MM`)<br>• Sem fuso horário definido |
| **Discount Handling** | • Descontos reduzem o `ContractedCost`<br>• Créditos são linhas `ChargeCategory: Credit` | • Misturar preço com crédito na mesma coluna |
| **Key-Value (JSON)** | • JSON simples (ECMA 404)<br>• Valores: `string`, `number`, `bool`, `null` | • Arrays complexos `[]`<br>• Objetos muito aninhados<br>• Chaves duplicadas |
| **Null Handling** | • Usar `NULL` quando não houver valor<br>• Consistência em opcionais | • Strings vazias `""`<br>• Usar `0` p/ valor desconhecido<br>• Termos `"Not Set"` |
| **String Handling** | • Preservar casing original<br>• IDs imutáveis | • Normalizar IDs sensíveis a case |
| **Numeric Format** | • Ponto como separador (`.` )<br>• Sinal negativo (`-`) permitido | • Vírgula (`,`)<br>• Sinal positivo (`+`)<br>• Símbolos de moeda |


# English version:

> **Technical Reference:** FinOps Open Cost & Usage Specification (FOCUS) **v1.2**


---

## Data Dictionary (FOCUS v1.2)

The table below lists all 57 mandatory and optional columns of the specification.

| Column ID | Usage / Type | Example / Explanation |
| :--- | :--- | :--- |
| **`AvailabilityZone`** | Technical Zone | `us-east-1a` |
| **`BilledCost`** | Invoiced Amount | `67.95` |
| **`BillingAccountId`** | Account ID | `123456789012` |
| **`BillingAccountName`** | Account Name | `Company X - Main Account` |
| **`BillingAccountType`** | Account Type | `Payer Account`, `MCA` (**New in 1.2**) |
| **`BillingCurrency`** | Invoice Currency | `USD`, `BRL` |
| **`BillingPeriodEnd`** | Billing End | `2025-06-30T23:59:59Z` |
| **`BillingPeriodStart`** | Billing Start | `2025-06-01T00:00:00Z` |
| **`CapacityReservationId`** | Reservation ID | `cr-123456` (If populated, it's a reservation) |
| **`CapacityReservationStatus`** | Reservation Status | `Unused`, `Used` |
| **`ChargeCategory`** | Line Item Type | `Usage`, `Purchase`, `Tax` |
| **`ChargeClass`** | Technical Class | `Correction`, `Total`, `Rounding` |
| **`ChargeDescription`** | Description | `Compute Hours for t3.large` |
| **`ChargeFrequency`** | Frequency | `OneTime`, `Recurring`, `UsageBased` |
| **`ChargePeriodEnd`** | Charge End | `2025-06-15T23:59:59Z` |
| **`ChargePeriodStart`** | Charge Start | `2025-06-15T00:00:00Z` |
| **`CommitmentDiscountCategory`** | Discount Category | `Spend`, `Usage` (e.g., SP vs RI) |
| **`CommitmentDiscountId`** | Discount ID | `ri-54321` |
| **`CommitmentDiscountName`** | Plan Name | `Compute Savings Plan` |
| **`CommitmentDiscountQuantity`** | Discount Qty | `10` |
| **`CommitmentDiscountStatus`** | Status | `Active` |
| **`CommitmentDiscountType`** | Discount Type | `Spend`, `Usage` |
| **`CommitmentDiscountUnit`** | Discount Unit | `USD`, `Hours` |
| **`ConsumedQuantity`** | Consumed Qty | `120.00` |
| **`ConsumedUnit`** | Consumption Unit | `Hours`, `GB` |
| **`ContractedCost`** | Negotiated Cost | `67.50` |
| **`ContractedUnitPrice`** | Negotiated Price | `2.70` |
| **`EffectiveCost`** | Amortized Cost | `64.20` (Essential for FinOps) |
| **`InvoiceId`** | Invoice ID | `INV-2025-06-7890` (**New in 1.2**) |
| **`InvoiceIssuer`** | Issuer | `Google Ireland`, `AWS Inc.` |
| **`ListCost`** | List Cost | `75.00` |
| **`ListUnitPrice`** | List Price | `3.00` |
| **`PricingCategory`** | Pricing Category | `OnDemand`, `Commitment` |
| **`PricingCurrency`** | Original Currency | `USD` (If contract is in dollars) |
| **`PricingCurrencyContractedUnitPrice`**| Negotiated Price (Orig) | `2.70` (**New in 1.2**) |
| **`PricingCurrencyEffectiveCost`** | Effective Cost (Orig)| `67.50` (**New in 1.2**) |
| **`PricingCurrencyListUnitPrice`** | List Price (Orig) | `3.00` (**New in 1.2**) |
| **`PricingQuantity`** | Pricing Qty | `25` |
| **`PricingUnit`** | Pricing Unit | `Hours`, `GiB` |
| **`Provider`** | Provider | `AWS`, `Azure`, `Google` |
| **`Publisher`** | Service Publisher | `Microsoft`, `MarketplaceVendorX` |
| **`RegionId`** | Region ID | `us-east-1` |
| **`RegionName`** | Region Name | `North Virginia` |
| **`ResourceId`** | Resource ID | `i-12345abcdef` |
| **`ResourceName`** | Resource Name | `prod-db-01` |
| **`ResourceType`** | Resource Type | `Compute Instance`, `Storage Bucket` |
| **`ServiceCategory`** | Macro Category | `Compute`, `Database` |
| **`ServiceName`** | Service | `AmazonEC2`, `Virtual Machines` |
| **`ServiceSubcategory`** | Subcategory | `On-Demand`, `Standard Storage` |
| **`SkuId`** | SKU ID | `DZH218-0043` |
| **`SkuMeter`** | SKU Meter | `Standard IO` (Replaces `x_SkuMeterName`) |
| **`SkuPriceDetails`** | Price Details (JSON) | `{"tier":"Free", "spot":true}` (**New 1.2**) |
| **`SkuPriceId`** | SKU Price ID | `PRICE-12345` |
| **`SubAccountId`** | Sub-Account ID | `123456` |
| **`SubAccountName`** | Sub-Account Name | `Project Alpha` |
| **`SubAccountType`** | Sub-Account Type | `Project`, `Subscription` (**New 1.2**) |
| **`Tags`** | Tags (JSON) | `{"Env":"Prod"}` |
| **`x_CustomField`** | Custom Fields | `x_cost_center_code` |

---

##  Legend & Formatting Rules

To ensure compliance with the FOCUS specification, data must strictly follow the standards below.

### 🔹 Data Format

* **Dates and Times:**
    * Must follow the **ISO 8601** standard (UTC).
    * Example: `2025-06-30T23:59:59Z`
* **Tags and Metadata:**
    * Must be represented as **Valid JSON**.
    * Example: `{"Project":"Marketing","CostCenter":"IT"}`
* **Currencies:**
    * Must use 3-letter codes per **ISO 4217**.
    * Examples: `USD`, `EUR`, `BRL`
    * *Virtual:* `DBU`, `Credits`, `Tokens`
* **Technical Identifiers (IDs):**
    * Must be alphanumeric, unique, and contain identifiable prefixes.
    * Examples: `INV-2025-06-7890`, `i-12345abcdef`
* **Region and Provider Names:**
    * `RegionId`: always lowercase, no spaces (e.g., `us-east-1`)
    * `RegionName`: readable "Title Case" (e.g., `North Virginia`)
    * `Provider`: official short names (e.g., `AWS`, `Azure`, `Snowflake`)
* **Numeric Values:**
    * Costs: recommended up to 2 decimal places (e.g., `67.95`)
    * Quantities: up to 3 decimal places (e.g., `10.125`)
* **JSON Fields:**
    * Keys and values must be enclosed in double quotes `""`.
    * Example: `{"Environment":"Prod","Owner":"FinOps Team"}`

---

## 🔧 Technical Specification Rules

Quick guide on what is allowed (✅) and forbidden (❌) when implementing FOCUS.

| Attribute | ✅ Rules and Standards (Allowed) | ❌ Forbidden / Exceptions |
| :--- | :--- | :--- |
| **Column Naming** | • PascalCase (e.g., `ResourceId`)<br>• No acronyms (except `Id`, `Sku`)<br>• Alphanumeric<br>• Custom columns with `x_` prefix | • Spaces in names<br>• Snake_case (except in `x_`)<br>• Special characters (`@`, `#`) |
| **Currency Code** | • 3-letter codes (e.g., `BRL`)<br>• Compliant with ISO 4217 | • Symbols (`$`)<br>• Full text (`Dollar`) |
| **Date/Time** | • ISO 8601 UTC: `YYYY-MM-DDTHH:mm:ssZ`<br>• Accepts offset: `−03:00` | • Local formats (`DD/MM`)<br>• No timezone defined |
| **Discount Handling** | • Discounts reduce `ContractedCost`<br>• Credits are lines with `ChargeCategory: Credit` | • Mixing price and credit in the same column |
| **Key-Value (JSON)** | • Simple JSON (ECMA 404)<br>• Values: `string`, `number`, `bool`, `null` | • Complex arrays `[]`<br>• Highly nested objects<br>• Duplicate keys |
| **Null Handling** | • Use `NULL` when no value exists<br>• Consistency in optional columns | • Empty strings `""`<br>• Using `0` for unknown value<br>• Terms like `"Not Set"` |
| **String Handling** | • Preserve original casing<br>• IDs are immutable | • Normalizing case-sensitive IDs |
| **Numeric Format** | • Dot as separator (`.` )<br>• Negative sign (`-`) allowed | • Comma (`,`)<br>• Positive sign (`+`)<br>• Currency symbols |
| **Unit Format** | • Standard uppercase abbreviations (`GB`)<br>• Discrete names (`Requests`) | • Plurals (`GBs`)<br>• Lowercase (`gb`)<br>• Full text (`Gigabytes`) |
| **Composite Units** | • Separate with slash `/` or space<br>• E.g., `GB-Mo`, `Requests/Hour` | • Using `"per"`<br>• Hyphen as grammatical connector |
| **Unit Format** | • Abreviações padrão (`GB`)<br>• Nomes discretos (`Requests`) | • Plurais (`GBs`)<br>• Minúsculas (`gb`)<br>• Extenso (`Gigabytes`) |
| **Composite Units** | • Separar com barra `/` ou espaço<br>• Ex: `GB-Mo`, `Requests/Hour` | • Usar `"per"`<br>• Hífen como conector gramatical |
