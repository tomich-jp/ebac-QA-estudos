# Bug Report — Módulo 4

## [CRÍTICO] Sistema trava ao inserir senha com mais de 20 caracteres

**Ambiente:**
- URL: https://ebaconline.com.br/qualidade-de-software
- Navegador: Chrome 124
- Sistema Operacional: Windows 11
- Ambiente: Produção

**Severidade:** Crítica
**Prioridade:** Alta
**Status:** Aberto
**Criado por:** João Pedro Tomich
**Atribuído para:** Dev responsável pelo módulo de autenticação

**Etapas para reproduzir:**
1. Acessar a tela de login
2. Digitar um usuário válido
3. Digitar uma senha com mais de 20 caracteres
4. Clicar no botão "Avançar"

**Resultado obtido:**
O sistema trava completamente e não executa nenhuma ação

**Resultado esperado:**
O sistema valida a senha e redireciona o usuário para a página inicial

**Evidências:**
[Anexar print ou vídeo da tela]



## Complementos importantes — Revisão pós-quiz

### Ambientes de teste
- **DEV (Desenvolvimento):** onde o desenvolvedor codifica e testa localmente
- **HML (Homologação):** onde o QA testa e o cliente valida antes do lançamento
- **PROD (Produção):** onde o usuário final usa — NUNCA deve ser testado diretamente

### Por que não testar em produção?
Risco de impactar usuários reais — um teste mal executado pode derrubar o sistema,
corromper dados reais de clientes ou expor vulnerabilidades.
O custo financeiro é consequência desse impacto.

### Caixa Cinza
Combinação de caixa preta e caixa branca — o testador tem acesso parcial
ao código. Muito usado em testes de API.

### Os 7 Princípios completos
1. O teste mostra a presença de defeitos, não a ausência
2. Testes exaustivos são impossíveis
3. O teste inicial economiza tempo e dinheiro
4. Defeitos se agrupam
5. Cuidado com o paradoxo do pesticida
6. O teste depende do contexto
7. Ausência de erros é uma ilusão

### Cobertura de teste — tipos
- **Cobertura de código:** % de linhas de código executadas pelos testes
- **Cobertura de requisitos:** % de requisitos cobertos pelos testes
- **Cobertura de cenários:** % de cenários de negócio testados
- 100% de cobertura de código não significa ausência de bugs de regra de negócio
