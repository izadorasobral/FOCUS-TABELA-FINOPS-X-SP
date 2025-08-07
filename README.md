# FOCUS-TABELA-FINOPS-X-SP
Descrição das colunas do FOCUS V1.2 , seu uso e explicação.

| Campo | Uso | Exemplo / Explicação |
| --- | --- | --- |
| Availability Zone | Zona técnica do recurso | `us-east-1a` |
| Billed Cost | Valor total faturado | `67.95 EUR` |
| Billing Account ID | ID da conta de cobrança | `123456789012` |
| Billing Account Name | Nome legível da conta | `Empresa X - Conta Principal` |
| Billing Account Type | Tipo de conta de cobrança | `Payer Account (AWS)` |
| Billing Currency | Moeda da fatura | `USD`, `BRL`, `EUR` |
| Billing Period End | Fim do período de faturamento | `2025-06-30T23:59:59Z` |
| Billing Period Start | Início do período de faturamento | `2025-06-01T00:00:00Z` |
| Capacity Reservation | Flag de reserva de capacidade | `true`, `false` |
| Capacity Reservation ID | ID da reserva | `cr-123456` |
| Capacity Reservation Status | Status da reserva | `active`, `cancelled` |
| Charge Category | Tipo de linha | `Usage`, `Purchase`, `Refund` |
| Charge Class | Classe técnica do encargo | `Correction`, `Transfer` |
| Charge Description | Descrição da linha | `Compute Hours for t3.large` |
| Charge Frequency | Frequência da cobrança | `OneTime`, `Recurring` |
| Charge Origination | Origem do encargo | `ProviderGenerated` |
| Charge Period End | Fim da janela de cobrança | `2025-06-15T23:59:59Z` |
| Charge Period Start | Início da janela de cobrança | `2025-06-15T00:00:00Z` |
| Commitment Discount | Indica uso de desconto | `true`, `false` |
| Commitment Discount Category | Tipo de desconto | `Reservation`, `SavingsPlan` |
| Commitment Discount ID | Identificador do desconto | `i-54321` |
| Commitment Discount Name | Nome do plano | `Reserved Instance Discount` |
| Commitment Discount Quantity | Quantidade incluída | `10` (vCPUs) |
| Commitment Discount Status | Status | `Active`, `Expired` |
| Commitment Discount Type | Tipo de preço | `PercentageOff`, `FixedPrice` |
| Commitment Discount Unit | Unidade de medida | `vCPU`, `GB` |
| Consumed Quantity | Quantidade consumida | `120.00` |
| Consumed Unit | Unidade do consumo | `Hours`, `GB`, `Requests` |
| Contracted Cost | Custo com desconto aplicado | `67.50` |
| Contracted Unit Price | Preço unitário negociado | `2.70` |
| Effective Cost | Custo real após créditos | `64.20` |
| Invoice ID | ID da fatura | `INV-2025-06-7890` |
| Invoice Issuer | Empresa que emitiu a fatura | `Amazon Web Services` |
| List Cost | Custo total com preço cheio | `75.00` |
| List Unit Price | Preço unitário público | `3.00` |
| Pricing Category | Tipo de precificação | `PayAsYouGo`, `Reserved` |
| Pricing Currency | Moeda usada para preço | `USD`, `DBU`, `Credits` |
| Pricing Currency Contracted Unit Price | Preço contratado na moeda | `2.70` |
| Pricing Currency Effective Cost | Custo efetivo na moeda | `67.50` |
| Pricing Currency List Unit Price | Preço público na moeda | `3.00` |
| Pricing Quantity | Quantidade de preço | `25` |
| Pricing Unit | Unidade de precificação | `Hours`, `Credits` |
| Provider | Nome técnico do provedor | `AWS`, `Azure`, `Snowflake` |
| Publisher | Empresa que oferece o serviço | `Amazon Web Services`, `Microsoft` |
| Region ID | Código da região | `us-east-1` |
| Region Name | Nome da região | `Norte da Virgínia` |
| Resource ID | Identificador do recurso | `i-1234567890abcdef0` |
| Resource Name | Nome legível do recurso | `prod-database-server-01` |
| Resource Type | Tipo técnico | `VirtualMachine`, `SQLDatabase` |
| Service Category | Categoria funcional | `Compute`, `Storage`, `Database` |
| Service Name | Nome do serviço | `AmazonEC2`, `Snowflake-Compute` |
| Service Subcategory | Subcategoria do serviço | `GPU-Optimized`, `Serverless` |
| SKU | Indica se possui SKU | `true`, `false` |
| SKU ID | Identificador do SKU | `DZH218-0043` |
| SKU Meter | Métrica do SKU | `Storage GB`, `Compute Hours` |
| SKU Price Details | Detalhes em JSON | `{"tier":"Premium"}` |
| SKU Price ID | ID do preço | `PRICE-12345` |
| Sub Account ID | ID da subconta ou assinatura | `sub-987654321` |
| Sub Account Name | Nome da subconta | `Projeto Marketing Digital` |
| Sub Account Type | Tipo da subconta | `Project`, `Subscription` |
| Tags | Metadados personalizados | `{"CostCenter":"TI"}` |
| x_* | Campos customizados por provedor | `x_aws_account_id`, `x_azure_reservation_order_id` |

**Legenda & Regras de Formatação (FOCUS v1.2)**

**Formato de Dados:**

- **Datas:**
    
    Devem seguir o padrão ISO 8601.
    
    Exemplo: `2025-06-30T23:59:59Z`
    
- **Tags:**
    
    Devem ser representadas como JSON válido.
    
    Exemplo: `{"Project":"Marketing","CostCenter":"IT"}`
    
- **Moedas:**
    
    Devem utilizar códigos ISO 4217.
    
    Exemplos: `USD`, `EUR`, `BRL`
    
    Para unidades virtuais: `DBU`, `Credits`, `Tokens`
    
- **Identificadores Técnicos:**
    
    Devem ser alfanuméricos, únicos e conter prefixos identificáveis.
    
    Exemplos: `INV-2025-06-7890`, `i-1234567890abcdef0`
    
- **Nomes de Regiões e Provedores:**
    - `RegionId`: sempre em minúsculas, sem espaços (ex: `us-east-1`)
    - `RegionName`: com capitalização legível (ex: `Norte da Virgínia`)
    - `ProviderName`: nomes oficiais (ex: `AWS`, `Azure`, `Snowflake`)
- **Valores Numéricos:**
    - Custos e preços: até 2 casas decimais (ex: `67.95`)
    - Quantidades fracionadas: até 3 casas decimais (ex: `10.125`)
- **Campos JSON:**
    
    Chaves e valores devem estar entre aspas, separados por vírgulas.
    
    O formato deve ser consistente e validável.
    
    Exemplo: `{"Environment":"Prod","Owner":"Equipe Financeira"}`

  Tabela Geral — Regras Técnicas da FOCUS Specification

| 🔧 Atributo | ✅ Regras e Padrões | ❌ Proibido / Exceções |
| --- | --- | --- |
| **Column Naming & Ordering** | • PascalCase (ex: `ResourceId`) 
• Sem acrônimos (exceto `Id`, `Sku`) 
• Alfanumérico 
• Máx. 50 caracteres 
• Custom columns com prefixo `x_` | • Siglas não padrão 
• Abreviações (exceto `Id`, `Sku`) 
• Caracteres especiais |
| **Currency Code Format** | • Códigos de 3 letras (ex: `BRL`, `USD`) 
• Conforme **ISO 4217:2015** | • Símbolos (`$`) 
• Moeda escrita por extenso (`real`, `dólar`) |
| **Date/Time Format** | • Formato ISO 8601 com UTC: `YYYY-MM-DDTHH:mm:ssZ` 
• Aceita offset ex: `−03:00` | • Formatos locais não padronizados 
• Ambiguidade de fuso horário |
| **Discount Handling** | • Desconto aplicado na **mesma linha da cobrança** 
• Aplica-se à linha toda 
• Créditos após são `ChargeCategory: Credit` | • Separar descontos em linhas distintas 
• Aplicar parcialmente |
| **Key-Value Format** | • String JSON simples conforme **ECMA 404** 
• Valores: `string`, `number`, `true`, `false`, `null` | • Arrays (`[]`) 
• Objetos aninhados 
• Chaves duplicadas |
| **Null Handling** | • Usar `NULL` quando não houver valor 
• Consistência para colunas nullable | • `""`, `0`, `"Not Set"` ou `"Not Applicable"` como substitutos de null |
| **String Handling** | • Preservar casing, espaços e pontuação originais 
• Identificadores imutáveis permanecem iguais | • Strings vazias ou só com espaço em colunas não-nullable |
| **Numeric Format** | • Valor único (inteiro, decimal ou notação científica) 
• Sinal negativo permitido (`-`) | • Sinal positivo (`+`) 
• Símbolos (`$`, `%`) 
• Frações (`½`) 
• Vírgulas |
| **Unit Format** | • Formatos válidos: `GB`, `Seconds`, `GB-Hours`, `MB/Day` 
• Abreviações padronizadas em maiúsculas | • Termos por extenso (`terabyte`) 
• Sufixos incorretos (`GBs`) 
• Formato `per` ou hífen (`GB-hour`) |
| **Count-Based Units** | • Nomes discretos: `Requests`, `Instances`, `Tokens` 
• Novo valor? Deve ser **capitalizado** | • Minúsculo sem padronização (`requests`) 
• Unidades não capitalizadas |
| **Time-Based Units** | • Válidos: `Second`, `Minute`, `Hour`, `Day`, `Month`, `Year` | • Variações não padronizadas (`min`, `hrs`, `mo`) |
| **Composite Units** | • Separar com `/` ou espaço (ex: `Requests/Day`, `GB Hour`) 
• Componentes devem estar entre unidades recomendadas | • Uso de `"per"` ou hífen para unir unidades (ex: `requests-per-day`, `GB-hour`) |
