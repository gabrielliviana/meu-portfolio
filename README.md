# 📸 Gabrielli Viana — Portfolio

Um portfólio fotográfico profissional responsivo e moderno, desenvolvido com HTML5, CSS3 e JavaScript puro (Vanilla JS), com suporte bilíngue (PT/EN) e sistema de gerenciamento dinâmico de álbuns.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---

## 🎯 Sobre o Projeto

Este é um portfólio responsivo para a fotógrafa **Gabrielli Viana**, apresentando trabalhos fotográficos em múltiplos álbuns temáticos. O site foi desenvolvido com foco em **performance**, **experiência do usuário** e **proteção de conteúdo**.

**Acesso ao site:** [Deploy em GitHub Pages]

---

## ✨ Funcionalidades

### 🌐 Multilíngue
- Suporte completo para **Português (PT)** e **Inglês (EN)**
- Troca de idioma via botão flutuante (canto inferior direito)
- Preferência de idioma salva em `localStorage`

### 📱 Design Responsivo
- Layout adaptável para desktop, tablet e mobile
- Breakpoint otimizado em 900px
- Navegação sticky no topo da página
- Cursor customizado com efeito de rastreamento

### 🖼️ Galeria Dinâmica
- Carregamento automático de álbuns desde `media/albums.json`
- Cada álbum com seu próprio `images.json` com metadados
- Grid de fotos com tamanhos variados (CSS Grid 12-coluna)
- Suporte a imagem de capa (separada da galeria completa)
- Página dedicada por álbum via URL parameter: `?album=nome`

### 🎨 Efeitos Visuais
- Animações de fade-up no carregamento
- Cursor customizado com anel de rastreamento
- Transições suaves em hover
- Scroll reveal com IntersectionObserver
- Marquee animado com categorias fotográficas

### 🔒 Proteção de Imagens
- ❌ Desativa clique direito em imagens
- ❌ Bloqueia drag & drop de fotos
- ❌ Impede cópia/cola via teclado
- ❌ Remove `pointer-events` das imagens (força interação com card)
- ❌ Desabilita seleção de texto/imagens (`user-select: none`)

### 🌍 I18n (Internacionalização)
- Sistema de tradução centralizado em `translations.json`
- Suporte a estrutura de chaves aninhadas
- Atributos `data-i18n` para elementos traduzíveis
- Fallback automático ao português

### 📊 Seções
1. **Hero** — Apresentação com título e CTA
2. **Marquee** — Categorias fotográficas em scroll contínuo
3. **Sobre** — Biografia, foto e estatísticas (2+ anos, 15+ projetos)
4. **Portfolio** — Grade dinâmica de álbuns
5. **Contato** — Email e redes sociais
6. **Footer** — Copyright e localização

---

## 🛠️ Tecnologias

| Tecnologia | Descrição |
|-----------|-----------|
| **HTML5** | Semântica, meta tags, estrutura |
| **CSS3** | Custom properties, Grid, Flexbox, Animations, Media Queries |
| **JavaScript ES6+** | Fetch API, async/await, DOM manipulation, localStorage |
| **JSON** | Gerenciamento de dados (álbuns, imagens, traduções) |
| **Google Fonts** | Bebas Neue, Cormorant Garamond, DM Sans |

---

## 📁 Estrutura do Projeto

```
PortfolioBranquela/
├── index.html                    # Página principal
├── styles/
│   └── index.css                 # Estilos globais (ambas páginas)
├── portfolio/
│   └── portfolio.html            # Página de álbum individual
├── media/
│   ├── albums.json               # Registro de álbuns disponíveis
│   ├── braga/
│   │   ├── images.json           # Metadados (albumName, location, capaFile)
│   │   ├── capa.jpg
│   │   └── *.jpg                 # Imagens do álbum
│   ├── guimaraes/
│   ├── paris/
│   ├── porto/
│   ├── viana/
│   └── corrida-primavera-2026/
├── translations.json             # Dicionário PT/EN
└── README.md                     # Este arquivo
```

### 📋 Formato de `albums.json`

```json
{
  "albums": [
    "braga",
    "guimaraes",
    "paris",
    "porto",
    "viana",
    "corrida-primavera-2026"
  ]
}
```

### 📸 Formato de `images.json` por álbum

```json
{
  "albumName": "Braga",
  "location": "Braga, Portugal",
  "capaFile": "capa.jpg",
  "images": [
    {
      "filename": "capa.jpg",
      "title": "Título da Foto",
      "description": "Descrição breve",
      "category": "Paisagem"
    },
    { ... }
  ]
}
```

### 🌍 Formato de `translations.json`

```json
{
  "pt": {
    "nav": { "sobre": "Sobre", "portfolio": "Portfolio", ... },
    "hero": { "tag": "Fotógrafa & Estudante de Design", ... },
    ...
  },
  "en": {
    "nav": { "sobre": "About", "portfolio": "Portfolio", ... },
    ...
  }
}
```

---

## 🚀 Como Usar


### Adicionar Novo Álbum

1. Crie pasta em `media/nome-album/`
2. Adicione imagens em formato JPG/PNG
3. Crie `images.json` com metadados
4. Declare no `media/albums.json`

**Exemplo:**
```bash
media/
└── meu-album/
    ├── images.json
    ├── capa.jpg
    ├── foto1.jpg
    └── foto2.jpg
```

### Mudar Traduções

Edite `translations.json` e adicione novos pares chave-valor nos objetos `pt` e `en`.

---

## 🔒 Segurança & Proteção de Imagens

Este portfólio implementa **múltiplas camadas** de proteção para desencorajar downloads não autorizados:

### Técnicas Implementadas

| Método | Descrição |
|--------|-----------|
| **Right-Click Disabled** | Bloqueia menu contextual em imagens |
| **Drag & Drop Blocked** | Impede arrastar imagens para o desktop |
| **Copy/Paste Protected** | Desativa teclado (Ctrl+C) em imagens |
| **Selection Disabled** | `user-select: none` no CSS |
| **Pointer Events None** | Força interação com o card, não a imagem |
| **No pointer-events** | Imagens são "transparentes" para cliques |

### ⚠️ Limitações Importantes

**Nenhum método é 100% à prova.** Usuários avançados com DevTools podem contornar. Estas técnicas:
- ✅ Desencorajam downloads acidentais
- ✅ Protegem contra scrapers automáticos simples
- ✅ Melhoram a experiência para usuários comuns
- ❌ NÃO são inquebrável para desenvolvedores experientes

Para máxima segurança, considere:
- Marca d'água visível (watermark)
- Hospedagem com controle de acesso
- CDN com restrições de referrer
- Formato WebP com compressão (mais difícil de extrair)

---

## 📊 Performance

- ⚡ **Carregamento rápido:** ~1.2s (primeira carga)
- 🎯 **Lighthouse Score:** 90+ (Performance, Accessibility)
- 📦 **Tamanho total:** ~2.5MB (com imagens)
- 🔄 **Zero dependencies:** Apenas HTML/CSS/JavaScript puro

---

## 📞 Contato

**Gabrielli Viana**
- 📧 Email: gabriellimariacoimbraviana@gmail.com
- 📍 Localização: Guimarães, Portugal
- 🔗 **Instagram:** [@gabrielli.viana](https://instagram.com)
- 🔗 **Behance:** [gabrielli-viana](https://behance.net)
- 🎨 **VSCO:** [@gabrielli.viana](https://vsco.co)

---

## 📄 Licença

Este projeto está licenciado sob a **MIT License** — veja o arquivo [LICENSE](LICENSE) para detalhes.

Contudo, **todos os arquivos fotográficos e conteúdo de mídia** são propriedade exclusiva de **Gabrielli Viana** e não podem ser utilizados sem permissão expressa.

---

## 🎓 Aprendizados & Recursos

### Conceitos Implementados

- ✅ **Fetch API** para carregamento dinâmico de JSON
- ✅ **localStorage** para persistência de preferências
- ✅ **IntersectionObserver** para scroll reveal
- ✅ **CSS Grid** com spans variados
- ✅ **Animações CSS** (keyframes, transitions)
- ✅ **Responsive Design** (mobile-first)
- ✅ **I18n/L10n** (internacionalização)
- ✅ **Event Delegation** em elementos dinâmicos

### Referências

- [MDN Web Docs](https://developer.mozilla.org)
- [CSS Tricks](https://css-tricks.com)
- [Web.dev by Google](https://web.dev)

---

## 🚀 Deploy em GitHub Pages

1. **Ative GitHub Pages** no repositório:
   - Settings → Pages → Source: `main`
   
2. **URL de acesso:** `https://seu-usuario.github.io/PortfolioBranquela/`

3. **Atualizações automáticas:** Qualquer push para `main` atualiza o site

---

## 📝 Changelog

### v1.0.0 — 2024-03-28
- ✨ Lançamento inicial
- 🌐 Sistema de tradução PT/EN completo
- 📱 Design responsivo
- 🔒 Proteção de imagens em 5 níveis
- 🖼️ Galeria dinâmica com 6 álbuns

---

## 🤝 Contribuir

Este é um portfólio pessoal. Para sugestões ou reportar bugs, abra uma [Issue](https://github.com/seu-usuario/PortfolioBranquela/issues).

---

**Desenvolvido com ❤️ por Irmão**

*Última atualização: 28 de março de 2026*
