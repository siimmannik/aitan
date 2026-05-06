# GitHubi laadimine — samm-sammult

Sellest kaustast (`aitan-website`) saab GitHubi hoidla, mille saab GitHub Pagesiga avaldada.

## 1. Loo GitHubis tühi hoidla

Mine: https://github.com/new

- **Repository name:** `aitan-website`
- **Owner:** `siimmannik`
- **Public** (vajalik, et GitHub Pages tasuta töötaks)
- **ÄRA** lisa README, .gitignore ega litsentsi (need on juba siin kaustas)
- Vajuta **Create repository**

## 2. Lükka kaust GitHubi

Ava terminal selles kaustas (`aitan-website`).

> ⚠️ **Enne `git init`-i:** kustuta peidetud `.git` kaust, kui see kausta on jäänud (mina üritasin selle ettevalmistuse tegemise käigus algatada, aga sandbox ei lubanud lõpuni viia). Windowsis: vaata Failidel **Hidden items** ja kustuta `.git`. Või terminalis:
> ```bash
> rmdir /s /q .git
> ```
> macOS / Linux:
> ```bash
> rm -rf .git
> ```

Seejärel jooksuta need käsud üksteise järel:

```bash
git init
git add .
git commit -m "Esimene versioon: AITAN! koduleht"
git branch -M main
git remote add origin https://github.com/siimmannik/aitan-website.git
git push -u origin main
```

Kui Git küsib autentimist:
- **Soovituslik:** kasuta GitHub CLI-d (`gh auth login`) või SSH-võtit.
- Või: GitHubi **Personal Access Token** (Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token, õigus `repo`). Sisesta token parooli asemel.

## 3. Lülita GitHub Pages sisse

1. Mine hoidla lehele: https://github.com/siimmannik/aitan-website
2. **Settings** (paremas ülanurgas)
3. Vasakus menüüs **Pages**
4. **Source** → vali **Deploy from a branch**
5. **Branch** → vali `main` ja `/ (root)` → **Save**

Mõne minuti pärast (1–5 min) on leht elus aadressil:

**https://siimmannik.github.io/aitan-website/**

## 4. (Valikuline) Oma domeen

Kui sul on domeen `aitan.ee` vms:

1. Lisa kaustasse fail `CNAME` (ilma laiendita), sisuks ainult domeen:
   ```
   aitan.ee
   ```
2. Pushi GitHubi: `git add CNAME && git commit -m "domain" && git push`
3. Domeeniregistraatoris (Zone, Veebimajutus, jne) sea DNS:
   - `A` kirjed `@` jaoks neljale IP-le:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - VÕI `CNAME` `www` jaoks → `siimmannik.github.io`
4. GitHubis: **Settings → Pages → Custom domain** → sisesta `aitan.ee` → Save
5. Kui DNS levib (võib võtta kuni 24h), märgi linnukesega **Enforce HTTPS**

## Hilisemad muudatused

```bash
# muuda index.html
git add .
git commit -m "kirjeldus mida muutsin"
git push
```

GitHub Pages uuendab lehe automaatselt umbes minuti jooksul.
