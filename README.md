# Projeto IA-001 - Sistema de Autenticação Full-Stack

Este é um projeto full-stack que implementa um sistema de autenticação completo com backend em Node.js/TypeScript e frontend em React/TypeScript.

## 📋 Estrutura do Projeto

```
projeto-IA-001/
├── backend001/          # API REST (Node.js + TypeScript)
├── frontend001/         # Aplicação React (TypeScript)
└── Ambos com configurações de produção
```

## 🚀 Build e Deploy para Produção

### Pré-requisitos

- Node.js (versão 16 ou superior)
- npm ou yarn
- Python (para servir o frontend em produção)
- Git

### Sequência de Comandos via Terminal

#### 1. Backend (API REST)

```bash
# Navegar para o diretório do backend
cd backend001

# Instalar dependências
npm install

# Build do projeto (compilar TypeScript)
npm run build

# Iniciar servidor em produção
npm start
```

**Porta padrão:** 3000 (configurável via variável de ambiente PORT)

#### 2. Frontend (React App)

```bash
# Navegar para o diretório do frontend
cd frontend001

# Instalar dependências
npm install

# Build completo para produção
npm run build:all
```

**Opções para servir o frontend:**

**Opção A - Servidor de desenvolvimento (para testes):**
```bash
npm start
```

**Opção B - Servidor HTTP simples (produção):**
```bash
# Usando Python (requer Python instalado)
python -m http.server 4000 --directory dist
```

**Porta padrão:** 4000

### Sequência Completa (Terminal)

```bash
# Terminal 1 - Backend
cd backend001
npm install
npm run build
npm start

# Terminal 2 - Frontend
cd frontend001
npm install
npm run build:all
python -m http.server 4000 --directory dist
```

## 🖱️ Usando os Arquivos .bat (Windows)

### Backend

#### Opção 1: Build e Inicialização Manual
```bash
cd backend001
npm install
npm run build
```

Depois execute:
```bash
cd backend-prod
start-server.bat
```

#### Opção 2: Scripts NPM
```bash
cd backend001
npm install
npm run build
npm start
```

### Frontend

#### Opção 1: Build Completo + Servidor de Desenvolvimento
```bash
cd frontend001
build-and-start.bat
```
Este script:
- Limpa a pasta `dist/`
- Executa o build de produção
- Copia arquivos para `dist/`
- Inicia o servidor de desenvolvimento

#### Opção 2: Build Manual + Servidor de Produção
```bash
cd frontend001
npm install
npm run build:all
```

Depois execute:
```bash
cd frontend-prod
start-dist.bat
```

#### Opção 3: Servidor de Produção (se build já foi feito)
```bash
cd frontend001
start-dist.bat
```

## 📁 Descrição dos Arquivos .bat

### Backend
- `backend001/backend-prod/start-server.bat`
  - Inicia o servidor Node.js em produção
  - Executa `node dist/server.js`
  - Mantém a janela aberta para manter o servidor rodando

### Frontend
- `frontend001/build-and-start.bat`
  - Executa build completo do projeto
  - Limpa e recria a pasta `dist/`
  - Copia arquivos de `build/` para `dist/`
  - Inicia servidor de desenvolvimento

- `frontend001/start-dist.bat`
  - Inicia servidor HTTP simples para pasta `dist/`
  - Usa Python para servir arquivos estáticos
  - Porta 4000

- `frontend001/frontend-prod/start-dist.bat`
  - Mesmo que `start-dist.bat`, mas na pasta de produção

## 🔧 Scripts NPM Disponíveis

### Backend (`backend001/package.json`)
- `npm run dev` - Inicia servidor de desenvolvimento com nodemon
- `npm run build` - Compila TypeScript para JavaScript
- `npm start` - Inicia servidor em produção
- `npm run restart` - Reinicia servidor de desenvolvimento

### Frontend (`frontend001/package.json`)
- `npm start` - Inicia servidor de desenvolvimento
- `npm run build` - Build de produção (pasta `build/`)
- `npm run build:all` - Build completo (pasta `dist/`)
- `npm run build:clean` - Limpa pasta `dist/`
- `npm run build:copy` - Copia arquivos para `dist/`

## 🌐 URLs de Acesso

Após iniciar os serviços:

- **Frontend:** http://localhost:4000
- **Backend API:** http://localhost:3000

## ⚠️ Observações Importantes

1. **Ordem de inicialização:** Sempre inicie o backend antes do frontend
2. **Dependências:** Certifique-se de que todas as dependências estão instaladas
3. **Portas:** Verifique se as portas 3000 e 4000 estão disponíveis
4. **Python:** O frontend em produção requer Python instalado
5. **Variáveis de ambiente:** Configure arquivo `.env` no backend se necessário

## 🐛 Troubleshooting

### Backend não inicia
- Verifique se a porta 3000 está livre
- Execute `npm install` novamente
- Verifique se o build foi executado (`npm run build`)

### Frontend não carrega
- Verifique se o backend está rodando
- Execute `npm run build:all` novamente
- Verifique se Python está instalado (para servidor de produção)

### Erro de CORS
- Verifique se o backend está configurado para aceitar requisições do frontend
- Verifique as configurações de CORS no arquivo `server.ts`
