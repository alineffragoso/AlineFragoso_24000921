# Avaliação — Engenharia de Software

**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: Aline de Souza Fragoso

RA: 24000921

Data: 26/03/2026

---

# 1. Definição do MVP

O MVP que eu defini é focado na parte de vendas da farmácia, que é o que mais acontece no dia a dia. Ele começa quando o cliente pede um produto e vai até a finalização da compra.

Dentro do MVP eu incluí:

* busca de produtos
* verificação de estoque
* realização da venda
* cadastro de cliente (quando precisar)
* venda a prazo

Fora do MVP eu deixei:

* relatórios mais completos
* controle financeiro detalhado
* integração entre várias unidades
* cadastro e gestão de fornecedores

Escolhi isso porque a venda é o principal processo da farmácia. Se essa parte funcionar bem, já resolve grande parte dos problemas.

---

# 2. Regras de Negócio (mínimo: 5)

**RN01 —** Não dá pra vender produto que não tem no estoque

**RN02 —** Quando a venda for a prazo, o sistema precisa gerar uma conta a receber automaticamente

**RN03 —** O estoque tem que ser atualizado assim que a venda for feita

**RN04 —** Só cliente cadastrado pode comprar a prazo

**RN05 —** Todo produto precisa ter nome, preço e fabricante cadastrados

**RN06 —** O sistema deve avisar quando o estoque estiver baixo

---

# 3. Requisitos Funcionais (mínimo: 8)

**RF01 —** Cadastrar cliente

**RF02 —** Buscar produto

**RF03 —** Mostrar informações do produto

**RF04 —** Realizar venda

**RF05 —** Fazer venda a prazo

**RF06 —** Atualizar o estoque automaticamente

**RF07 —** Gerar conta a receber

**RF08 —** Emitir comprovante

**RF09 —** Cadastrar produto

---

# 🛡 4. Requisitos Não Funcionais (mínimo: 4)

**RNF01 —** O sistema deve funcionar pela internet

**RNF02 —** Precisa ter login com usuário e senha

**RNF03 —** As ações devem acontecer rápido

**RNF04 —** Os dados precisam ser protegidos

---

# 5. Casos de Uso (mínimo: 10)

(Depois você coloca o diagrama aqui)

* UC01 – Cadastrar produto
* UC02 – Consultar produto
* UC03 – Realizar venda
* UC04 – Cadastrar cliente
* UC05 – Venda a prazo
* UC06 – Verificar estoque
* UC07 – Atualizar estoque
* UC08 – Gerar conta a receber
* UC09 – Emitir comprovante
* UC10 – Gerenciar clientes

**Includes:**

* Realizar venda → consultar produto
* Realizar venda → verificar estoque
* Realizar venda → identificar cliente

**Extends:**

* Venda a prazo → realizar venda
* Cadastro de cliente → realizar venda
* Gerar conta a receber → venda a prazo

---

# 6. Documentação dos Casos de Uso

---

## **UC01 — Cadastrar Produto**

**Ator(es):** Gerente
**Descrição:** Cadastro de novos produtos
**Pré-condições:** Estar logado
**Pós-condições:** Produto salvo no sistema

### Fluxo Principal

1. Entra na tela de cadastro
2. Preenche os dados
3. Confirma
4. Sistema salva

### Fluxos Alternativos / Exceções

* FA01 — Algum dado obrigatório não foi preenchido

### Relacionamentos

* **Include:** —
* **Extend:** —

---

## **UC02 — Consultar Produto**

**Ator(es):** Atendente
**Descrição:** Buscar produto no sistema
**Pré-condições:** Sistema funcionando
**Pós-condições:** Produto aparece na tela

### Fluxo Principal

1. Digita o nome ou código
2. Sistema busca
3. Mostra o resultado

### Fluxos Alternativos / Exceções

* FA01 — Produto não encontrado

### Relacionamentos

* **Include:** —
* **Extend:** —

---

## **UC03 — Realizar Venda**

**Ator(es):** Atendente
**Descrição:** Fazer uma venda
**Pré-condições:** Produto cadastrado
**Pós-condições:** Venda concluída

### Fluxo Principal

1. Identifica o cliente
2. Busca o produto
3. Verifica estoque
4. Informa quantidade
5. Finaliza

### Fluxos Alternativos / Exceções

* FA01 — Sem estoque
* FA02 — Cliente não cadastrado

### Relacionamentos

* **Include:** Consultar produto, Verificar estoque
* **Extend:** Venda a prazo, Cadastro de cliente

---

## **UC04 — Cadastrar Cliente**

**Ator(es):** Atendente
**Descrição:** Cadastro de cliente
**Pré-condições:** Nenhuma
**Pós-condições:** Cliente registrado

### Fluxo Principal

1. Abre cadastro
2. Preenche dados
3. Salva

### Fluxos Alternativos / Exceções

* FA01 — Dados incompletos

### Relacionamentos

* **Include:** —
* **Extend:** Realizar venda

---

## **UC05 — Venda a Prazo**

**Ator(es):** Atendente
**Descrição:** Venda com pagamento depois
**Pré-condições:** Cliente cadastrado
**Pós-condições:** Conta a receber criada

### Fluxo Principal

1. Faz a venda
2. Define prazo
3. Sistema registra

### Fluxos Alternativos / Exceções

* FA01 — Cliente não pode comprar a prazo

### Relacionamentos

* **Include:** Gerar conta a receber
* **Extend:** Realizar venda

---

## **UC06 — Verificar Estoque**

**Ator(es):** Sistema
**Descrição:** Conferir quantidade disponível
**Pré-condições:** Produto existe
**Pós-condições:** Quantidade exibida

### Fluxo Principal

1. Recebe o produto
2. Consulta estoque
3. Mostra quantidade

### Fluxos Alternativos / Exceções

* FA01 — Produto não existe

### Relacionamentos

* **Include:** —
* **Extend:** —

---

## **UC07 — Atualizar Estoque**

**Ator(es):** Sistema
**Descrição:** Atualizar após venda
**Pré-condições:** Venda feita
**Pós-condições:** Estoque atualizado

### Fluxo Principal

1. Recebe venda
2. Diminui quantidade
3. Salva

### Fluxos Alternativos / Exceções

* FA01 — Erro ao atualizar

### Relacionamentos

* **Include:** —
* **Extend:** —

---

## **UC08 — Gerar Conta a Receber**

**Ator(es):** Sistema
**Descrição:** Registrar valor a receber
**Pré-condições:** Venda a prazo
**Pós-condições:** Conta criada

### Fluxo Principal

1. Recebe dados
2. Cria registro
3. Define vencimento

### Fluxos Alternativos / Exceções

* FA01 — Erro no registro

### Relacionamentos

* **Include:** —
* **Extend:** Venda a prazo

---

## **UC09 — Emitir Comprovante**

**Ator(es):** Sistema
**Descrição:** Gerar comprovante da venda
**Pré-condições:** Venda finalizada
**Pós-condições:** Comprovante exibido

### Fluxo Principal

1. Pega dados da venda
2. Gera comprovante
3. Mostra na tela

### Fluxos Alternativos / Exceções

* FA01 — Erro na geração

### Relacionamentos

* **Include:** —
* **Extend:** —

---

## **UC10 — Gerenciar Clientes**

**Ator(es):** Atendente
**Descrição:** Consultar e editar cliente
**Pré-condições:** Cliente existe
**Pós-condições:** Dados atualizados

### Fluxo Principal

1. Busca cliente
2. Edita dados
3. Salva

### Fluxos Alternativos / Exceções

* FA01 — Cliente não encontrado

### Relacionamentos

* **Include:** —
* **Extend:** —

---

Se quiser, posso te mandar agora **os diagramas prontos (bonitos)** pra você só colocar no GitHub e entregar 👍
