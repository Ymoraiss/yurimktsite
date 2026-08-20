# Setup GitHub e Vercel - Guia Passo-a-Passo

## 1️⃣ Pré-requisitos

### Instalar Git
- Baixe em: https://git-scm.com/download/win
- Durante a instalação, escolha as opções padrão
- Após instalar, reinicie o terminal/VS Code

### Criar conta GitHub
- Acesse: https://github.com/signup
- Crie sua conta ou faça login se já tiver

## 2️⃣ Inicializar Git Localmente

Após instalar Git, abra o Terminal no VS Code e execute:

```bash
# Navegar para a pasta do projeto
cd "c:\Users\55219\Desktop\Yuri Site"

# Inicializar repositório git
git init

# Configurar seu nome e email (se não tiver configurado globalmente)
git config user.name "Seu Nome"
git config user.email "seu.email@github.com"

# Adicionar todos os arquivos
git add .

# Fazer o primeiro commit
git commit -m "Initial commit - Yuri Site"
```

## 3️⃣ Criar Repositório no GitHub

1. Acesse: https://github.com/new
2. Preencha os dados:
   - **Repository name**: `yuri-site` (ou outro nome)
   - **Description**: "Portfólio e website de Yuri Fonseca - Tráfego Pago & Web Design"
   - **Public** ou **Private** (escolha sua preferência)
   - Deixe as outras opções desmarcadas
3. Clique em "Create repository"

## 4️⃣ Conectar Repositório Local ao GitHub

Após criar o repositório no GitHub, você receberá instruções. Execute no terminal:

```bash
# Adicionar o repositório remoto (substitua SEU_USUARIO e SEU_REPO)
git remote add origin https://github.com/SEU_USUARIO/yuri-site.git

# Renomear branch para main (se necessário)
git branch -M main

# Fazer o push dos arquivos
git push -u origin main
```

**Ao executar `git push`, você será pedido para autenticar:**
- Pode usar seu token de acesso pessoal do GitHub
- Ou usar GitHub CLI (`gh auth login`)

## 5️⃣ Conectar com Vercel

### Opção A: Via GitHub (Recomendado)

1. Acesse: https://vercel.com/new
2. Clique em "Import Git Repository"
3. Conecte sua conta GitHub
4. Selecione o repositório `yuri-site`
5. Vercel detectará automaticamente como um projeto estático
6. Clique em "Deploy"
7. Seu site estará disponível em: `seu-projeto.vercel.app`

### Opção B: Via Upload Direto

1. Acesse: https://vercel.com/new
2. Escolha "Create Git Repository"
3. Siga as instruções para criar um novo repositório GitHub diretamente pelo Vercel

## 6️⃣ Arquivos Recomendados (Opcional)

Para melhorar a organização, crie estes arquivos:

### `.gitignore`
```
node_modules/
.env
.env.local
.DS_Store
.vercel
dist/
build/
```

### `vercel.json` (para configurações específicas)
```json
{
  "buildCommand": "",
  "outputDirectory": ".",
  "redirects": [
    {
      "source": "/index.html",
      "destination": "/",
      "permanent": false
    }
  ]
}
```

## 7️⃣ Próximos Passos

✅ Atualizações automáticas:
- Sempre que você faz `git push`, o Vercel detecta e redeploy automaticamente
- Seu site fica online em: `https://seu-projeto.vercel.app`

✅ Domínio customizado:
- No Vercel: Settings → Domains
- Adicione seu domínio customizado

✅ Variáveis de ambiente:
- No Vercel: Settings → Environment Variables
- Configure o que for necessário

---

**Dúvidas?** Acesse:
- GitHub Docs: https://docs.github.com
- Vercel Docs: https://vercel.com/docs
