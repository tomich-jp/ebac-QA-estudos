# Módulo 5 — Técnicas de Teste Caixa Preta

## 1. Particionamento de Equivalência

Técnica de teste caixa preta que divide os dados de entrada em partições
(grupos similares), assumindo que todos os valores de uma mesma partição
se comportam da mesma forma. Testa-se apenas um representante de cada
partição, otimizando o número de casos de teste sem perder cobertura.

**Quando usar:** quando temos intervalos de dados com comportamentos
diferentes — válidos e inválidos.

**Exemplo prático — cadastro de usuários (16 a 80 anos):**

| CT | Entrada | Partição | Resultado Esperado |
|---|---|---|---|
| CT01 | 11 anos | Inválida (abaixo) | ❌ Não cadastrar |
| CT02 | 22 anos | Válida | ✅ Cadastrar |
| CT03 | 81 anos | Inválida (acima) | ❌ Não cadastrar |

---

## 2. Análise de Valor Limite

Extensão do particionamento de equivalência. Aplica a mesma lógica de
partições, porém testa os extremos de cada intervalo — onde a maioria
dos bugs costuma se esconder.

**Padrão:** testar 3 pontos por borda (abaixo do limite, no limite e
acima do limite).

**Quando usar:** quando a partição é ordenada e sequencial (numérica
ou temporal).

**Exemplo prático — cadastro por horário (09:00 às 18:00):**

| CT | Entrada | Resultado Esperado |
|---|---|---|
| CT01 | 08:59 | ❌ Inválido |
| CT02 | 09:00 | ✅ Válido |
| CT03 | 09:01 | ✅ Válido |
| CT04 | 17:59 | ✅ Válido |
| CT05 | 18:00 | ✅ Válido |
| CT06 | 18:01 | ❌ Inválido |

---

## 3. Tabela de Decisão

Técnica utilizada para sistemas com regras de negócio complexas que
possuem múltiplas condições e ações em combinação. Organiza todas as
combinações possíveis em formato de tabela com valores booleanos
(SIM/NÃO).

**Fórmula:** número de regras = 2ⁿ (onde n = número de condições)
Exemplo: 2 condições = 4 regras | 3 condições = 8 regras

**Quando usar:** quando combinações diferentes de condições geram
resultados diferentes.

**Desvantagem:** quando o número de condições cresce muito, a tabela
fica complexa demais.

**Exemplo prático — desconto (cliente premium + cupom válido):**

| Condições | RN01 | RN02 | RN03 | RN04 |
|---|---|---|---|---|
| Cliente premium? | SIM | NÃO | SIM | NÃO |
| Cupom válido? | SIM | SIM | NÃO | NÃO |
| **Ações** | | | | |
| Desconto? | ✅ SIM | ❌ NÃO | ❌ NÃO | ❌ NÃO |

---

## 4. Transição de Estado

Técnica aplicada quando o sistema possui múltiplos estados e eventos
que causam transições entre eles. Testa tanto as transições válidas
quanto as inválidas.

**Quando usar:** sistemas com fluxo sequencial obrigatório — pedidos,
pagamentos, status de cadastro, semáforos, fluxo de login com bloqueio.

**Elementos:**
- **Estado:** situação atual do sistema
- **Evento:** o que causa a mudança
- **Transição:** a mudança de um estado para outro
- **Ação:** o que o sistema faz ao transitar

**Exemplo prático — fluxo de pedido online:**


**Regra importante:** após Enviado o pedido não pode ser cancelado.
Cancelado é estado final — não retorna para Criado.

---

## 5. Técnicas Baseadas em Experiência

> ⚠️ Importante: essas técnicas podem ser usadas em qualquer nível
> de teste (unitário, integração, sistema, aceitação) — não são
> exclusivas do nível de aceitação.

### Teste Exploratório
Baseado na experiência e intuição do testador. Sem roteiro fixo,
permite descobrir bugs inesperados que técnicas sistemáticas não
encontrariam.

**Quando usar:** pouca documentação, tempo reduzido, ou quando se
quer encontrar bugs fora do esperado.

### Teste Baseado em Checklist
O testador segue uma lista predefinida de condições a verificar.
Garante cobertura mínima de itens específicos com rastreabilidade.

**Quando usar:** quando precisamos garantir que itens específicos
foram verificados e documentados.

### Suposição de Erro
O testador usa experiência própria e do time para prever onde os
bugs têm maior probabilidade de aparecer. Complementado com análise
de risco para ser mais assertivo.

**Como aplicar sendo júnior:**
- Consultar histórico de bugs anteriores do sistema
- Perguntar ao dev onde o código é mais complexo
- Focar em campos de entrada (formulários, uploads, campos numéricos)
- Usar a matriz de risco para priorizar
