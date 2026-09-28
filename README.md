# Férová cena akcie – webová aplikace (PWA)

Kalkulačka férové ceny akcie podle zisku, volného peněžního toku nebo tržeb. Jde nainstalovat na plochu telefonu i počítače a funguje i offline.

## Obsah složky

- `index.html` – celá aplikace
- `manifest.webmanifest` – název, barvy a ikony pro instalaci
- `sw.js` – service worker, díky kterému aplikace funguje offline
- `icons/` – ikony aplikace

## Zveřejnění na GitHub Pages

1. Založte si účet na github.com (pokud ho nemáte).
2. Vpravo nahoře klikněte na **+** → **New repository**. Jako název zadejte třeba `ferova-cena`, nastavte **Public** a klikněte na **Create repository**.
3. Na stránce nového repozitáře klikněte na odkaz **uploading an existing file** (nebo **Add file → Upload files**).
4. Přetáhněte do okna všechny soubory z této složky **včetně složky `icons`**. Dole klikněte na **Commit changes**.
5. Zkontrolujte, že v repozitáři je vidět složka `icons` s pěti obrázky. Pokud chybí, nahrajte ji znovu.
6. Otevřete **Settings** → v levém menu **Pages**.
7. V části **Build and deployment** zvolte u **Source** možnost **Deploy from a branch**, u větve **main** a složku **/ (root)**. Klikněte na **Save**.
8. Za pár minut bude aplikace na adrese `https://VAS-NICK.github.io/ferova-cena/`. Adresa se zobrazí i nahoře na stránce **Pages**.

Poznámky:
- Na bezplatném účtu GitHub funguje Pages jen pro veřejné repozitáře. Kód tedy uvidí kdokoli. Nejsou v něm žádná hesla ani osobní data, takže to nevadí.
- Názvy tlačítek na GitHubu se časem mohou mírně změnit.

## Sdílení na Discordu

Vložte do kanálu odkaz `https://VAS-NICK.github.io/ferova-cena/` a zprávu připněte. Kamarádi nepotřebují žádný účet.

## Instalace aplikace

- **Android (Chrome):** otevřete odkaz → menu ⋮ → **Instalovat aplikaci** nebo **Přidat na plochu**.
- **iPhone (Safari):** otevřete odkaz → tlačítko **Sdílet** → **Přidat na plochu**.
- **Počítač (Chrome, Edge):** ikona instalace v adresním řádku, nebo tlačítko **Nainstalovat aplikaci** přímo v kalkulačce (zobrazí se jen v prohlížečích, které to podporují).

## Aktualizace

1. V repozitáři otevřete soubor, klikněte na tužku (úprava) nebo nahrajte novou verzi přes **Add file → Upload files** (soubor se stejným názvem se přepíše).
2. Při větší změně otevřete `sw.js` a zvyšte `VERSION` (např. `'v1'` na `'v2'`). Tím se u všech smaže stará uložená verze.
3. Uživatelé s internetem dostanou novou verzi při příštím otevření. Offline se použije poslední uložená verze.

## Dobré vědět

- **Data zůstávají v zařízení.** Uložené scénáře a poslední zadání jsou jen v prohlížeči konkrétního zařízení, nikam se neodesílají a nesynchronizují se mezi zařízeními.
- **iPhone:** aplikace přidaná na plochu má vlastní úložiště oddělené od Safari. Scénáře uložené v Safari v nainstalované aplikaci neuvidíte (a naopak).
- **Písmo Archivo** se načítá z Google Fonts, takže při prvním otevření se odešle požadavek na servery Google. Offline nebo bez načteného písma se použije systémové písmo. Pokud chcete Google Fonts úplně vynechat, dá se písmo (licence OFL) nahrát přímo do repozitáře.
- **Otevření souboru dvojklikem** (adresa začínající `file://`) funguje, ale bez instalace a offline režimu. Ty fungují jen přes `https://` (GitHub Pages) nebo lokální server, např. `python3 -m http.server` ve složce a adresa `http://localhost:8000`.
