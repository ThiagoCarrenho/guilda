# 🌱 Fluxo de Colaboração e Publicação

Este projeto usa o plugin [Obsidian Digital Garden](https://github.com/oleeskild/obsidian-digital-garden) para publicar as notas do nosso vault.  
O conteúdo principal do site está em: `guilda/src/site/notes/`
Cada arquivo `.md` dentro dessa pasta representa uma nota pública no site.

---

## 🚫 Importante – Não use o botão "Publish"

O **botão “Publish” do plugin Digital Garden** **não deve ser utilizado**.  
A publicação do site é feita **automaticamente** quando as alterações são enviadas (`git push`) para o repositório principal.  

> Usar o botão “Publish” pode sobrescrever ou quebrar o fluxo automático de deploy.

---

## 🧭 1. Clonando o repositório

### 🔹 Linha de comando (CLI)
```bash
git clone https://github.com/<ORG>/<REPO>.git
cd <REPO>
````

### 🔹 GitHub Desktop

1. Abra o **GitHub Desktop**.
2. Vá em **File → Clone Repository...**
3. Selecione o repositório e clique em **Clone**.

---

## 🪶 2. Abrindo o vault no Obsidian

1. Abra o **Obsidian**.
2. Clique em **“Abrir pasta como vault”** (ou *Open folder as vault*).
3. Selecione a pasta:

   ```
   guilda/src/site/notes/
   ```
4. O Obsidian vai reconhecer essa pasta como o vault principal.
5. Certifique-se de **não alterar** a estrutura dessa pasta (ela é o conteúdo publicado no site).

---

## 🔄 3. Atualizando e enviando alterações

Antes e depois de editar qualquer nota, sempre **sincronize** o repositório com o Git.
Isso evita conflitos e perda de conteúdo.

---

### 💻 Linha de comando (Git CLI)

**Antes de editar:**

```bash
git pull origin main
```

**Após editar ou criar notas:**

```bash
git add .
git commit -m "atualiza notas"
git pull origin main  # garante que está atualizado antes de enviar
git push origin main
```

O comando `git pull` antes do `push` é obrigatório para evitar sobrescrever mudanças de outros contribuidores.

---

### 🪟 GitHub Desktop

1. Clique em **Fetch origin** para verificar se há mudanças remotas.
2. Clique em **Pull origin** antes de editar.
3. Faça suas alterações no Obsidian.
4. Retorne ao GitHub Desktop e clique em **Commit to main**.
5. Clique em **Push origin** para enviar as alterações.

O site será atualizado automaticamente após o push.

---

## ⚙️ 4. Estrutura do projeto

```
guilda/
├── src/
│   └── site/
│       └── notes/                  ← Vault do Obsidian
│           ├── .obsidian/          ← Configurações do Obsidian
│           ├── assets/             ← Imagens e anexos
│           └── *.md                ← Notas (conteúdo publicado)
└── .github/workflows/              ← CI/CD para deploy automático
```

---

## 🧱 5. Sobre o `.gitignore`

Apenas o arquivo que contém credenciais sensíveis do plugin é ignorado:

```gitignore
guilda/src/site/notes/.obsidian/plugins/obsidian-digital-garden/data.json
```

Todo o restante da configuração do Obsidian pode ser versionado normalmente.

---

## 💬 6. Boas práticas

* Sempre faça **`git pull` antes** de começar a editar.
* Nunca use o botão **“Publish”** dentro do Obsidian.
* Faça commits pequenos e com mensagens descritivas.
* Resolva conflitos de merge antes de dar `push`.
* As alterações no branch `main` são publicadas automaticamente pelo CI/CD (Vercel ou GitHub Actions).

---

💚 Com esse fluxo, todas as pessoas podem colaborar com segurança no conteúdo do Digital Garden, sem risco de sobrescrita nem vazamento de credenciais.


# Digital Obsidian Garden
This is the template to be used together with the [Digital Garden Obsidian Plugin](https://github.com/oleeskild/Obsidian-Digital-Garden). 
See the README in the plugin repo for information on how to set it up.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/oleeskild/digitalgarden)

---
## Docs
Docs are available at [dg-docs.ole.dev](https://dg-docs.ole.dev/)

