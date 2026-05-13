# 🚀 Guia de Deployment — GitHub Pages

Este guia descreve como hospedar seu portfólio **gratuitamente** no GitHub Pages.

## ✅ Pré-requisitos

- Conta no GitHub
- Git instalado localmente
- Seu projeto versionado no GitHub

## 📋 Passo a Passo

### 1️⃣ Criar Repositório no GitHub

1. Acesse [github.com/new](https://github.com/new)
2. **Repository name:** `PortfolioBranquela`
3. **Description:** "Portfólio fotográfico de Gabrielli Viana"
4. **Public** (para hospedar em Pages)
5. **Clique em "Create repository"**

### 2️⃣ Fazer Upload Local

Abra um terminal na pasta do projeto:

```bash
# Inicializar git (se ainda não tiver)
git init

# Adicionar todos os arquivos
git add .

# Commit inicial
git commit -m "Initial commit - Portfolio site"

# Adicionar repositório remoto (substitua seu-usuario)
git remote add origin https://github.com/seu-usuario/PortfolioBranquela.git

# Enviar para GitHub
git push -u origin main
```

### 3️⃣ Ativar GitHub Pages

1. No GitHub, acesse seu repositório
2. **Settings** → **Pages** (lado esquerdo)
3. **Source:** Selecione `main` (ou `master`)
4. **Folder:** `/` (raiz)
5. **Clique em "Save"**

### 4️⃣ Aguardar Deployment

- GitHub criará um workflow automaticamente
- Acesse **Actions** para acompanhar
- Após 1-2 minutos, seu site estará ao vivo!

## 🌐 Acessar seu Site

**URL:** `https://seu-usuario.github.io/PortfolioBranquela/`

Substitua "seu-usuario" pelo seu username do GitHub.

## 📤 Atualizar Conteúdo

Após fazer mudanças locais:

```bash
# Editar arquivos localmente...

# Adicionar mudanças
git add .

# Commit
git commit -m "Descrição da mudança"

# Enviar
git push
```

O site atualizará automaticamente em poucos minutos!

## 🔧 Configurações Avançadas

### Usar Domínio Customizado

1. **Settings** → **Pages**
2. **Custom domain:** Digite seu domínio
3. Configure DNS (veja instruções do GitHub)

### Proteger Branch main

1. **Settings** → **Branches**
2. **Add rule** → Proteja `main`
3. Exija pull requests antes de merge

### Usar GitHub Actions para CI/CD

Crie `.github/workflows/deploy.yml`:

```yaml
name: Deploy

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Deploy to Pages
        uses: actions/upload-artifact@v3
```

## 📊 Monitorar Performance

1. **Configurar Google Analytics:**
   - Crie conta em analytics.google.com
   - Copie tracking ID
   - Adicione ao `<head>` do HTML

2. **Usar Lighthouse:**
   - Chrome DevTools → Lighthouse
   - Analise Performance, Accessibility, SEO

3. **Page Insights:**
   - GitHub mostra velocidade de deploy
   - Monitore em **Deployments** → **Activity log**

## 🆘 Troubleshooting

### Site não aparece
- ✅ Verifique se repositório é **Public**
- ✅ Aguarde 2-3 minutos após primeira ativação
- ✅ Limpe cache do navegador (Ctrl+Shift+Del)

### Imagens não carregam
- ✅ Use caminhos relativos: `./media/album/image.jpg`
- ✅ Evite paths absolutos: `/media/...` ❌

### Domínio customizado não funciona
- ✅ Verifique registros DNS (A ou CNAME)
- ✅ Aguarde 24h para propagação DNS
- ✅ Settings → Pages → Custom domain (salve 1x mais)

### Performance lenta
- ✅ Comprima imagens com [TinyPNG](https://tinypng.com)
- ✅ Use WebP em vez de JPG
- ✅ Minifique CSS/JS
- ✅ ative gzip no servidor

## 📚 Recursos Úteis

- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [GitHub Actions](https://github.com/features/actions)
- [Guia de Domínios Customizados](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

---

**Pronto! Seu portfólio está online! 🎉**
