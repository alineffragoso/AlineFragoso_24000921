## Sistema Integrado de Gestão de Farmácia – Saúde & Vida

### Regras de Negócio

* Não é permitido vender produtos que não tenham estoque
* Toda venda a prazo deve gerar uma conta a receber automaticamente
* Quando uma compra é registrada, o estoque precisa ser atualizado
* Apenas o farmacêutico pode autorizar vendas com receita
* O gerente pode cadastrar e alterar produtos
* O sistema deve avisar quando o estoque estiver baixo

---

### Requisitos Funcionais

* Cadastrar clientes
* Buscar produtos pelo nome ou código
* Realizar vendas
* Registrar vendas a prazo
* Controlar o estoque
* Registrar compras de fornecedores
* Gerar contas a pagar
* Gerar contas a receber
* Emitir relatórios
* Gerenciar usuários

---

### Requisitos Não Funcionais

* O sistema deve funcionar pela internet
* Deve ter login com usuário e senha
* Precisa ser estável e não cair facilmente
* Os dados devem ser protegidos

---

### Casos de Uso

* Cadastrar produto
* Consultar produto
* Realizar venda
* Cadastrar cliente
* Registrar venda a prazo
* Registrar compra
* Controlar estoque
* Gerar relatórios
* Controlar contas a pagar
* Controlar contas a receber

---

### Includes

* A venda depende de consultar o produto
* A venda também precisa verificar o estoque
* Antes de finalizar, é necessário identificar o cliente

---

### Extends

* Venda a prazo é uma variação da venda normal
* Cadastro de cliente pode acontecer durante a venda
* O alerta de estoque acontece quando o estoque é controlado

---

### Exemplo de Caso de Uso

**Realizar Venda**

Ator: Atendente

Fluxo principal:
O cliente pede um produto, o atendente busca no sistema, verifica se tem no estoque, informa a quantidade, e finaliza a venda.

Exceções:
Se não tiver estoque ou o produto não for encontrado, a venda não pode continuar.
