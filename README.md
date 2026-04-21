# 🧪 QA Automation Project

Projeto de automação de testes end-to-end utilizando **Cypress** com **TypeScript**, seguindo boas práticas de QA como Page Object Model (POM), testes de regressão, smoke tests e integração contínua via GitHub Actions.

---

## 📁 Estrutura do Projeto

```
qa-automation-repo/
├── cypress/
│   ├── e2e/                  # Testes end-to-end
│   │   ├── smoke/            # Smoke tests
│   │   ├── regression/       # Testes de regressão
│   │   └── api/              # Testes de API
│   ├── fixtures/             # Dados de teste (JSON)
│   ├── support/
│   │   ├── commands.ts       # Comandos customizados
│   │   └── e2e.ts            # Configuração global
│   └── reports/              # Relatórios gerados
├── src/
│   ├── pages/                # Page Objects
│   ├── utils/                # Funções utilitárias
│   └── data/                 # Constantes e tipos
├── docs/                     # Documentação de QA
├── .github/
│   ├── workflows/            # Pipelines CI/CD
│   └── ISSUE_TEMPLATE/       # Templates de bug report
├── cypress.config.ts
├── tsconfig.json
└── package.json
```

---

## 🚀 Como Executar

### Pré-requisitos
- Node.js >= 18
- npm >= 9

### Instalação

```bash
git clone https://github.com/seu-usuario/qa-automation-repo.git
cd qa-automation-repo
npm install
```

### Executar testes

```bash
# Abre interface gráfica do Cypress
npm run cy:open

# Executa todos os testes em modo headless
npm run cy:run

# Executa apenas smoke tests
npm run cy:smoke

# Executa apenas testes de regressão
npm run cy:regression

# Executa com relatório HTML
npm run cy:report
```

---

## 🏗️ Padrões Utilizados

### Page Object Model (POM)
Cada página da aplicação possui uma classe correspondente em `src/pages/`, encapsulando seletores e ações.

```typescript
// Exemplo de uso
import { LoginPage } from '../../src/pages/LoginPage'

const loginPage = new LoginPage()
loginPage.visit()
loginPage.fillEmail('user@example.com')
loginPage.fillPassword('senha123')
loginPage.submit()
```

### Fixtures
Dados de teste centralizados em `cypress/fixtures/` no formato JSON, separados por contexto (usuários, produtos, etc.).

### Custom Commands
Comandos reutilizáveis definidos em `cypress/support/commands.ts`:

```typescript
cy.login('user@example.com', 'senha123')
cy.checkToast('Operação realizada com sucesso!')
```

---

## 🧩 Tipos de Teste

| Tipo | Localização | Descrição |
|------|-------------|-----------|
| Smoke | `cypress/e2e/smoke/` | Verificações rápidas das funcionalidades críticas |
| Regressão | `cypress/e2e/regression/` | Cobertura completa de funcionalidades |
| API | `cypress/e2e/api/` | Testes de endpoints REST |

---

## 📊 Relatórios

Os relatórios são gerados via **Mochawesome** em `cypress/reports/` após cada execução com `npm run cy:report`.

---

## 🔁 CI/CD

Pipeline configurado com **GitHub Actions** (`.github/workflows/ci.yml`) que executa automaticamente a cada push e pull request na branch `main`.

---

## 📄 Documentação

- [Plano de Testes](docs/test-plan.md)
- [Casos de Teste](docs/test-cases.md)
- [Bug Report Guide](docs/bug-report-guide.md)

---

## 🛠️ Stack

- [Cypress](https://www.cypress.io/) - Framework de testes E2E
- [TypeScript](https://www.typescriptlang.org/) - Tipagem estática
- [Mochawesome](https://github.com/adamgruber/mochawesome) - Relatórios HTML
- [GitHub Actions](https://github.com/features/actions) - CI/CD

---

## 👤 Autor

Feito com 💙 por **[Seu Nome]** — QA Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin)](https://linkedin.com/in/seu-perfil)
[![GitHub](https://img.shields.io/badge/GitHub-black?style=flat&logo=github)](https://github.com/seu-usuario)
