# Test Cases — Portfólio | demo.opencart.com
> Site de teste: https://demo.opencart.com
> Executado em: Março 2026

---

## 🔐 CASOS DE TESTE — LOGIN (TC-001 a TC-005)

---

### TC-001 — Login com credenciais válidas
- **Pré-condição:** Conta criada com email e password válidos
- **Passos:**
  1. Aceder a demo.opencart.com
  2. Clicar em "My Account" → "Login"
  3. Inserir email válido
  4. Inserir password correcta
  5. Clicar em "Login"
- **Resultado Esperado:** Utilizador entra na conta e vê o dashboard
- **Resultado Obtido:** Utilizador entrou na conta com sucesso e visualiza o dashboard "My Account" com opções de Orders, Address Book e Logout
- **Status:** ✅ Pass

---

### TC-002 — Login com password incorrecta
- **Pré-condição:** Conta existente no sistema
- **Passos:**
  1. Aceder à página de login
  2. Inserir email válido
  3. Inserir password errada
  4. Clicar em "Login"
- **Resultado Esperado:** Mensagem de erro "Invalid email or password"
- **Resultado Obtido:** Apareceu mensagem de erro "Warning: No match for E-Mail Address and/or Password."
- **Status:** ✅ Pass

---

### TC-003 — Login com email sem formato válido
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Aceder à página de login
  2. Inserir "emailsemarroba" no campo email
  3. Inserir qualquer password
  4. Clicar em "Login"
- **Resultado Esperado:** Erro de validação no campo email antes de submeter
- **Resultado Obtido:** Formulário foi submetido sem validação do browser; servidor processou o pedido e retornou mensagem genérica — sem validação de formato no lado do cliente
- **Status:** ❌ Fail
- **Bug relacionado:** BUG-001

---

### TC-004 — Login com campos vazios
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Aceder à página de login
  2. Deixar email e password em branco
  3. Clicar em "Login"
- **Resultado Esperado:** Mensagem de erro nos campos obrigatórios
- **Resultado Obtido:** Formulário foi submetido com campos vazios sem qualquer validação — sem indicação de campos obrigatórios no lado do cliente
- **Status:** ❌ Fail
- **Bug relacionado:** BUG-002

---

### TC-005 — Login com email de utilizador inexistente
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Aceder à página de login
  2. Inserir email que não existe no sistema
  3. Inserir qualquer password
  4. Clicar em "Login"
- **Resultado Esperado:** Mensagem de erro sem revelar se o email existe
- **Resultado Obtido:** Mensagem genérica "Warning: No match for E-Mail Address and/or Password." — não revela se o email existe ✅ Comportamento seguro
- **Status:** ✅ Pass

---

## 🔍 CASOS DE TESTE — PESQUISA DE PRODUTOS (TC-006 a TC-010)

---

### TC-006 — Pesquisa com termo válido existente
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Na barra de pesquisa escrever "phone"
  2. Premir Enter ou clicar na lupa
- **Resultado Esperado:** Lista de produtos relacionados aparece
- **Resultado Obtido:** Página de resultados exibiu produtos relacionados com "phone", incluindo imagem, nome e preço
- **Status:** ✅ Pass

---

### TC-007 — Pesquisa com termo que não existe
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Na barra de pesquisa escrever "xyzabcdef123"
  2. Premir Enter
- **Resultado Esperado:** Mensagem "There is no product that matches the search criteria"
- **Resultado Obtido:** Sistema exibiu mensagem "There is no product that matches the search criteria" conforme esperado
- **Status:** ✅ Pass

---

### TC-008 — Pesquisa com campo vazio
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Deixar a barra de pesquisa vazia
  2. Clicar na lupa ou premir Enter
- **Resultado Esperado:** Mensagem de aviso ou lista de produtos
- **Resultado Obtido:** Sistema redirecionou para página de pesquisa exibindo mensagem "There is no product that matches the search criteria" sem erro de sistema
- **Status:** ✅ Pass

---

### TC-009 — Pesquisa com caracteres especiais
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Na barra de pesquisa escrever "@#$%"
  2. Premir Enter
- **Resultado Esperado:** Nenhum produto encontrado, sem erro de sistema
- **Resultado Obtido:** Sistema tratou os caracteres especiais sem gerar erro, exibindo mensagem "There is no product that matches the search criteria"
- **Status:** ✅ Pass

---

### TC-010 — Pesquisa com nome parcial de produto
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Na barra de pesquisa escrever "ipho"
  2. Premir Enter
- **Resultado Esperado:** Produtos com "iphone" aparecem nos resultados
- **Resultado Obtido:** Sistema retornou o produto iPhone nos resultados — pesquisa parcial por prefixo funciona correctamente
- **Status:** ✅ Pass

---

## 🛒 CASOS DE TESTE — CARRINHO (TC-011 a TC-015)

---

### TC-011 — Adicionar produto ao carrinho
- **Pré-condição:** Nenhuma
- **Passos:**
  1. Pesquisar por "MacBook"
  2. Clicar no produto
  3. Clicar em "Add to Cart"
- **Resultado Esperado:** Produto adicionado, contador do carrinho actualiza
- **Resultado Obtido:** Produto adicionado com sucesso; contador actualizou para "1 item(s)" e apareceu mensagem de confirmação verde
- **Status:** ✅ Pass

---

### TC-012 — Ver produtos no carrinho
- **Pré-condição:** Ter produto no carrinho
- **Passos:**
  1. Clicar no ícone do carrinho no topo
  2. Ver lista de produtos
- **Resultado Esperado:** Produtos adicionados aparecem com preço e quantidade
- **Resultado Obtido:** Dropdown do carrinho exibiu o produto com nome, quantidade e preço unitário correctos
- **Status:** ✅ Pass

---

### TC-013 — Remover produto do carrinho
- **Pré-condição:** Ter produto no carrinho
- **Passos:**
  1. Abrir o carrinho
  2. Clicar no botão de remover (X) ao lado do produto
- **Resultado Esperado:** Produto removido, carrinho actualiza
- **Resultado Obtido:** Produto removido com sucesso; carrinho actualizou para "0 item(s) - $0.00"
- **Status:** ✅ Pass

---

### TC-014 — Alterar quantidade no carrinho
- **Pré-condição:** Ter produto no carrinho
- **Passos:**
  1. Abrir o carrinho completo via "View Cart"
  2. Alterar a quantidade para 2
  3. Clicar em "Update"
- **Resultado Esperado:** Quantidade e preço total actualizam correctamente
- **Resultado Obtido:** Quantidade actualizada para 2 e o preço total foi recalculado correctamente
- **Status:** ✅ Pass

---

### TC-015 — Iniciar checkout sem estar logado
- **Pré-condição:** Utilizador não está logado
- **Passos:**
  1. Ter produto no carrinho
  2. Clicar em "Checkout"
- **Resultado Esperado:** Sistema pede login ou registo antes de continuar
- **Resultado Obtido:** Sistema redirecionou para página de checkout com opção obrigatória de fazer login ou criar conta antes de prosseguir
- **Status:** ✅ Pass

---

## 📊 Resumo dos Resultados

| ID | Título | Status |
|----|--------|--------|
| TC-001 | Login com credenciais válidas | ✅ Pass |
| TC-002 | Login com password incorrecta | ✅ Pass |
| TC-003 | Login com email sem formato válido | ❌ Fail |
| TC-004 | Login com campos vazios | ❌ Fail |
| TC-005 | Login com email inexistente | ✅ Pass |
| TC-006 | Pesquisa com termo válido | ✅ Pass |
| TC-007 | Pesquisa com termo inexistente | ✅ Pass |
| TC-008 | Pesquisa com campo vazio | ✅ Pass |
| TC-009 | Pesquisa com caracteres especiais | ✅ Pass |
| TC-010 | Pesquisa com nome parcial | ✅ Pass |
| TC-011 | Adicionar produto ao carrinho | ✅ Pass |
| TC-012 | Ver produtos no carrinho | ✅ Pass |
| TC-013 | Remover produto do carrinho | ✅ Pass |
| TC-014 | Alterar quantidade no carrinho | ✅ Pass |
| TC-015 | Checkout sem login | ✅ Pass |

**Total: 13 Pass | 2 Fail**

---

## 🐛 Bugs Identificados

### BUG-001 — Sem validação de formato de email no login
- **TC Relacionado:** TC-003
- **Severidade:** Média
- **Descrição:** O formulário de login não valida o formato do email no lado do cliente. Um email sem "@" é submetido e processado pelo servidor.
- **Passos para reproduzir:**
  1. Aceder à página de login
  2. Inserir "emailsemarroba" no campo email
  3. Clicar em Login
- **Resultado Actual:** Formulário submetido; servidor retorna mensagem genérica
- **Resultado Esperado:** Sistema deve bloquear o envio com aviso de formato inválido
- **Sugestão:** Adicionar validação HTML5 `type="email"` ou validação JavaScript no cliente

---

### BUG-002 — Sem validação de campos obrigatórios no login
- **TC Relacionado:** TC-004
- **Severidade:** Média
- **Descrição:** O formulário de login permite submissão com campos email e password completamente vazios.
- **Passos para reproduzir:**
  1. Aceder à página de login
  2. Deixar email e password em branco
  3. Clicar em Login
- **Resultado Actual:** Formulário submetido vazio; servidor retorna mensagem genérica
- **Resultado Esperado:** Sistema deve indicar que os campos são obrigatórios antes de submeter
- **Sugestão:** Adicionar atributo `required` nos campos do formulário

---

*Portfólio de QA Testing — Manual Test Cases v1.0*
