# SpeedCorrer ⚡

> **Plataforma de Agendamento Automático e Gerenciamento para Instagram Reels & Mídias**

SpeedCorrer é um sistema completo de automação e agendamento de posts e Reels para o Instagram. Desenvolvido com um frontend ultra-responsivo em **React + Vite** e um backend de alta performance em **FastAPI (Python)** integrado diretamente com a **Meta Graph API (Instagram Business API)**.

---

## 🚀 Principais Recursos

- 📸 **Agendamento e Publicação de Reels:** Faça upload de vídeos verticais (9:16) e agende disparos automáticos para o Instagram.
- 🔄 **Agendamento em Lote (Bulk Schedule):** Selecione vários vídeos, defina uma data de início e os horários diários de postagem (ex: 09:00, 14:00, 18:00, 21:00).
- 👤 **Multi-Contas Instagram:** Gerencie e troque facilmente entre diferentes perfis do Instagram conectados.
- ⚡ **Disparo Imediato:** Botão "Disparar Agora" no Dashboard para publicar qualquer post pendente imediatamente via API.
- 📊 **Dashboard em Tempo Real:** Acompanhamento completo dos posts (Status: *Pendente*, *Publicado*, *Falhou*) com logs detalhados de erros para fácil diagnóstico.
- 🤖 **IA & Geração de Conteúdo:** Integração com modelos Gemini e OpenAI para suporte na criação de conteúdo e mídias.

---

## 🛠️ Tecnologias Utilizadas

- **Frontend:** React 18, TypeScript, Vite, Tailwind CSS, Lucide Icons, Zustand.
- **Backend:** Python 3.13, FastAPI, Uvicorn, SQLite (`reels_scheduler.db`), HTTPX, Playwright.
- **Integração Externa:** Meta Graph API (v20.0), Gemini API, OpenAI API.

---

## ⚙️ Como Rodar o Projeto Localmente

### 1. Pré-requisitos
- **Node.js** (v18+) e **pnpm** (`npm i -g pnpm`)
- **Python** (v3.11+) e **Poetry** (`pip install poetry`)

---

### 2. Configurando o Backend (Porta 7001)

1. Navegue até a pasta do backend:
   ```bash
   cd backend
   ```

2. Instale as dependências com o Poetry:
   ```bash
   poetry install
   ```

3. Crie o arquivo `.env` na pasta `backend/` com as suas credenciais da Meta:
   ```env
   INSTAGRAM_APP_ID=seu_app_id
   INSTAGRAM_APP_SECRET=sua_chave_secreta
   INSTAGRAM_DEFAULT_TOKEN=seu_access_token_instagram
   INSTAGRAM_USER_ID=seu_instagram_user_id
   ```

4. Popule o banco de dados inicial:
   ```bash
   poetry run python update_db.py
   ```

5. Inicie o servidor FastAPI:
   ```bash
   poetry run python start.py
   ```
   *O backend estará rodando em `http://localhost:7001`.*

---

### 3. Configurando o Frontend (Porta 5173)

1. Em um novo terminal, navegue até a pasta do frontend:
   ```bash
   cd frontend
   ```

2. Instale as dependências:
   ```bash
   pnpm install
   ```

3. Inicie o servidor de desenvolvimento:
   ```bash
   pnpm dev
   ```
   *O frontend estará acessível em `http://localhost:5173`.*

---

## 🔐 Configuração na Meta Developers (Instagram Business API)

Para habilitar a publicação de Reels na sua conta do Instagram:

1. Acesse o [Meta for Developers](https://developers.facebook.com/apps/) e crie/abra seu App do tipo **Empresa (Business)**.
2. Adicione o produto **Instagram (Configuração da API com login empresarial)**.
3. Certifique-se de que sua conta do Instagram é **Profissional / Business** e está vinculada a uma **Página do Facebook**.
4. Em modo de desenvolvimento, sua conta do Facebook (Administradora do App) tem permissões totais (`instagram_basic`, `instagram_content_publish`).
5. Gerador de Tokens: Use a ferramenta de tokens na Meta para obter o `Instagram Access Token` e o `Instagram User ID`.

---

## 📝 Licença

Desenvolvido para **SpeedCorrer**. Todos os direitos reservados.
