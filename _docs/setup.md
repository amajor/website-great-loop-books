## 🚀 Quick Setup (One-Time)

### 1. Create the GitHub repo

1. Go to [github.com/new](https://github.com/new)
2. Name it `greatloopbooks` (or whatever you like)
3. Set it to **Public** (required for free GitHub Pages)
4. Don't initialize with README (you already have files)

### 2. Push this folder to GitHub

```bash
cd greatloopbooks
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/greatloopbooks.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. The site will build automatically on every push

### 4. Connect your custom domain

1. In **Settings → Pages**, enter `greatloopbooks.com` under Custom Domain
2. At your domain registrar (wherever you bought greatloopbooks.com), add these DNS records:

```
Type: A     Name: @     Value: 185.199.108.153
Type: A     Name: @     Value: 185.199.109.153
Type: A     Name: @     Value: 185.199.110.153
Type: A     Name: @     Value: 185.199.111.153
Type: CNAME Name: www   Value: YOUR-USERNAME.github.io
```

DNS changes take up to 48 hours to propagate.