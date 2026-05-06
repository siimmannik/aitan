# AITAN!

Liikumine "Aitan!" — koduleht.

Üheleheline staatiline veebileht (single-file HTML), mis kannab manifesti ja kogub liitujate e-postiaadresse.

## Struktuur

- `index.html` — kogu leht koos CSS-i ja JS-iga ühes failis.
- `img/vennad.jpg` — Adobe Stock 641765403, litsentsitud
- `img/vendlus.jpg` — Adobe Stock 772134718, litsentsitud

## Lokaalne eelvaade

Topeltklikk `index.html` peal või:

```bash
python3 -m http.server 8000
# ava http://localhost:8000
```

## Avaldamine GitHub Pages'is

1. Lükka see hoidla GitHubi (vt `DEPLOY.md` juhend).
2. GitHubis: **Settings → Pages → Source → Deploy from a branch → `main` / `root` → Save**.
3. Mõne minuti pärast on leht aadressil:
   `https://siimmannik.github.io/aitan-website/`

## Kohandatud domeen (valikuline)

Kui soovid `aitan.ee`-d või muud domeeni:

1. Loo failinimega `CNAME` (ilma laiendita) ja sisse domeen, näiteks `aitan.ee`.
2. Domeeni DNS-is suuna `A`-kirjed GitHub Pages IP-dele:
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153
3. Või `CNAME`-kirje `siimmannik.github.io`-le (alamdomeenide puhul).

## Litsents

© 2026 Liikumine "Aitan!".
