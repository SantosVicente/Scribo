# 🎓 Scribo: Plataforma SaaS para Gestão Acadêmica de Projetos Escritos

Scribo é uma plataforma SaaS (Software as a Service) projetada para impulsionar a forma como estudantes, orientadores e instituições de ensino colaboram e gerenciam trabalhos acadêmicos. A plataforma centraliza o ciclo de vida do trabalho acadêmico, desde a concepção até a formatação final, utilizando inteligência artificial para potencializar a escrita e a pesquisa.

---

## 🚀 Sobre o Projeto (A Visão Completa)

O objetivo final do Scribo é ser um ecossistema completo para a produção acadêmica, oferecendo:

* **Plataforma Web:** O principal onde toda a gestão de projetos, escrita e colaboração acontece.
    * **Perfis de Usuário:** `Aluno`, `Orientador` e `Admin (Instituição)`.
    * **Gestão de Projetos:** Alunos criam projetos (TCC, artigo, etc.) e convidam orientadores por email ou QR Code. Orientadores gerenciam múltiplos projetos em um dashboard centralizado.
    * **Editor de Texto Focado:** Um editor de texto avançado (baseado em Tiptap/Milkdown) com formatação ABNT/APA, comentários e histórico de versão.
    * **Traduções em I18N:** Versões em inglês e português.

* **Inteligência Artificial (IA):**
    * **Assistente de Escrita (Gemini):** Integrado ao editor para corrigir gramática, reescrever trechos (formal, conciso), gerar resumos e atuar como um "agente-IA-orientador" que sugere melhorias estruturais no texto.
    * **Pesquisa de Fontes (Perplexity):** Uma ferramenta de pesquisa que permite ao aluno buscar fontes e citações relevantes diretamente da plataforma, otimizando o processo de referenciamento.

* **Plano Institucional (Empresa):**
    * Um perfil de `Admin` que pode gerenciar contas de alunos e orientadores dentro de um domínio específico (ex: `@minhauniversidade.edu`), acompanhar o progresso geral e garantir a conformidade.
    * Pagamentos feitos via Stripe.

* **Aplicativo Desktop (Electron):**
    * Uma versão desktop da plataforma para escrita focada e com possibilidade de trabalho offline, sincronizando com a nuvem assim que houver conexão.

* **Aplicativo Mobile (React Native):**
    * Um **"Aplicativo Companheiro"** focado em gestão, comunicação e tarefas rápidas, não na escrita.
    * **Para Alunos:** Consulta de cronograma, captura rápida de ideias, leitura de comentários e notificações push.
    * **Para Orientadores:** Dashboard de orientandos, leitura e resposta de comentários, chat e aceitar convites de orientação (ex: lendo um QR Code gerado pelo aluno na plataforma web).

---

## 🎯 Foco Atual (MVP)

Para garantir um desenvolvimento ágil e focado no aprendizado das tecnologias, o MVP (Produto Mínimo Viável) se concentra **exclusivamente no core loop de colaboração entre Aluno e Orientador** na plataforma web.

O que **ESTÁ** no escopo do MVP:
* **Autenticação:** Sistema de login/cadastro simples (ex: Google, GitHub).
* **Landing Page:** Utilizando motion design para apresentar o produto.
* **Perfis:** Definição dos perfis `Aluno` e `Orientador`.
* **Gestão de Projeto (Mínima):**
    * `Aluno` pode criar um novo "Projeto".
    * `Aluno` pode convidar *um* `Orientador` para esse projeto (via e-mail, sem QR Code por enquanto).
    * `Orientador` pode ver a lista de projetos que orienta.
* **Editor de Texto:** Implementação do editor de texto (Tiptap ou Milkdown) dentro da página do projeto.
* **Integração IA (Mínima):**
    * **Apenas Gemini:** Implementar *uma* funcionalidade, como "Corrigir gramática" em um texto selecionado.
* **Deploy (Core):**
    * Backend (NestJS) conteinerizado com Docker.
    * Frontend (Next.js) conteinerizado com Docker.
    * Deploy do banco e dos containers no Google Cloud.
    * Banco de Dados no Cloud SQL do Google Cloud.

---

## 🧊 Backlog (Ignorado no MVP)

Todas as funcionalidades abaixo são importantes para a visão completa, mas **NÃO** serão desenvolvidas neste primeiro momento para manter o foco:

* ❌ **Aplicativo Mobile:** Todo o desenvolvimento em React Native.
* ❌ **Perfil Admin (Instituição):** Toda a lógica de "Plano Empresa".
* ❌ **Aplicativo Desktop:** Sem foco em Electron por enquanto.
* ❌ **Integração com Perplexity:** A busca de fontes fica para a V2.
* ❌ **IA Avançada:** O "agente-orientador" (IA proativa) é muito complexo para o MVP.
* ❌ **Colaboração em Tempo Real:** Edição simultânea (como Google Docs).
* ❌ **Sistema de Pagamentos:** O MVP será totalmente gratuito. Posteriormente conectado com stripe.
* ❌ **Gestão de Arquivos:** Upload de PDFs, pastas, etc.
* ❌ **Funcionalidades Mobile Avançadas:** Como o aceite de convite por QR Code.
* ❌ **Funcionalidades Avançadas:** Como transcrição/resumos de vídeos para usar como fonte, por exemplo.

---

## 🛠️ Stack de Tecnologias

Esta é a stack definida para o projeto:

### Frontend
* **Framework:** Next.js (App Router)
* **Estilização e UI:** Tailwind CSS + shadcn/ui + origin ui
* **Animação e UX:** Framer Motion (para Motion Design) + react bits
* **Editor de Texto:** Tiptap ou Milkdown
* **SEO:** Foco nas otimizações nativas do Next.js (Metadata API).

### Mobile
* **Framework:** React Native

### Backend
* **Framework:** NestJS
* **Linguagem:** TypeScript
* **ORM:** Drizzle ORM
* **Autenticação:** JWT (ou NextAuth.js/Auth.js)

### Integração de IA
* **Assistente de Escrita:** Google Gemini Pro API
* **Busca de Fontes:** Perplexity API (PPLX)

### Cloud & DevOps
* **Conteinerização:** Docker
* **Plataforma de Deploy:** Google Cloud Run (GCP)
* **CI/CD:** GitHub Actions

### Banco de Dados
* **Opção 1 (Preferencial):** Cloud SQL (PostgreSQL) no GCP.
* **Opção 2 (Backup):** Supabase (PostgreSQL) ou MongoDB Atlas.
