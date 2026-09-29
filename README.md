# portfolio.kairodev.it

Personal portfolio — static site, no build step. Push to GitHub, it goes live.

## Deploy (una sola volta)

```bash
cd ~/kairodev-portfolio
git init -b main
git add index.html CNAME
git commit -m "Portfolio live"
gh repo create portfolio --public --source=. --push
# oppure senza gh: crea il repo "portfolio" su github.com/Test-create-ops e poi:
# git remote add origin https://github.com/Test-create-ops/portfolio.git
# git push -u origin main
```

Poi: repo Settings → Pages → deploy from branch `main`, cartella `/ (root)`.
GitHub legge il file CNAME e lega il dominio da solo. Attendi ~2 minuti + HTTPS automatico.

## DNS (una sola volta, dal pannello del registrar di kairodev.it)

Aggiungi questo record:

| Tipo  | Nome (host) | Valore                    |
|-------|-------------|---------------------------|
| CNAME | portfolio   | test-create-ops.github.io. |

Nota il punto finale sul valore, se il pannello lo richiede. Propagazione: da pochi minuti a qualche ora.

## Aggiornare

Modifica `index.html`, poi `git add -A && git commit -m "..." && git push`. Live in ~1 minuto.
