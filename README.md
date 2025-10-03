## 🛡️ SecureTasks – DevSecOps Pipeline para Juice Shop

### 📌 **Contexto**
A **SecureTasks** é uma startup fictícia em processo de transformação digital. Após receber alertas sobre vulnerabilidades críticas em sua aplicação web pública (baseada no [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/)), a empresa decidiu adotar práticas de **DevSecOps** para elevar sua maturidade em segurança, mantendo a agilidade de entrega.

Este repositório contém a implementação prática de um **pipeline CI/CD seguro e automatizado**, que integra detecção de falhas, testes, análise estática, análise dinâmica e deploy contínuo em ambiente de staging.

---

## 🎯 **Objetivos do Projeto**
- Automatizar a detecção de vulnerabilidades em diferentes estágios do ciclo de vida da aplicação.  
- Integrar ferramentas de segurança ao pipeline CI/CD (Shift-Left Security).  
- Estabelecer gates de segurança que impeçam o deploy de código vulnerável.  
- Garantir entregas contínuas e seguras para a aplicação Juice Shop.  
- Fornecer documentação e evidências auditáveis do processo.

---

## 🧭 **Arquitetura da Solução**

```text
┌──────────────┐
│   Dev Push   │
└──────┬───────┘
       │
       ▼
┌────────────────────┐
│ GitHub Actions CI  │
└────────────────────┘
       │
       ├── 🧪 Build & Test (Node.js + Docker)
       ├── 🔍 SAST (Semgrep)
       ├── 📦 Dependency Scan (npm audit)
       ├── 🐳 Container Scan (Trivy)
       ├── 🌐 DAST (OWASP ZAP Baseline)
       ▼
┌────────────────────────┐
│ Deploy Staging (VPS)   │
└────────────────────────┘