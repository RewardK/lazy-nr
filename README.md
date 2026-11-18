// readme facut 90% cu ai


<div align="center">
  <img src="docs/screenshots/icon.png" width="104" alt="Lazy NR by RewardK">
  <h1>Lazy NR <code>by RewardK</code></h1>
  <p><b>Autopilot AG pentru News Reporters.</b></p>
  <p>
    <a href="#download"><img src="https://img.shields.io/badge/version-1.2.0.0-22c55e?style=flat-square" alt="Version"></a>
    <a href="#cerinte"><img src="https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078d4?style=flat-square" alt="Platform"></a>
    <a href="#download"><img src="https://img.shields.io/badge/portable-.exe-8b5cf6?style=flat-square" alt="Portable"></a>
    <a href="https://www.virustotal.com/gui/file/872aff25d01aa2f2885539501a18c468e749347b390e24e2cae9b2ae8db226c6"><img src="https://img.shields.io/badge/VirusTotal-verific%C4%83%20hash--ul-f5c542?style=flat-square" alt="VirusTotal"></a>
    <a href="#credits"><img src="https://img.shields.io/badge/made%20by-RewardK-22c55e?style=flat-square" alt="Made by RewardK"></a>
  </p>
  <p>
    <a href="../../releases/latest"><b>⬇️ download exe</b></a> ·
    <a href="#own-key"><b>🔑 cheie gemini (gratis)</b></a> ·
    <a href="#nou"><b>✨ ce e nou în 1.2</b></a> ·
    <a href="#demo"><b>📸 screenshots</b></a> ·
    <a href="#faq"><b>❓ faq</b></a>
  </p>
</div>

---

## Ce este Lazy NR?

un soft care foloseste gemini prin api (ai 300 de requests gratis pe zi) pentru ca tu sa nu faci absolut nimic pentru aceasta factiune.

> [!IMPORTANT]
> **nu poti organiza fara sa participi**.

---

<a id="nou"></a>
## ✨ Ce e nou în 1.2

- **Interfață nouă** — stil modern, grafit, mai lizibil; Dashboard refăcut (stare, următoarea acțiune, anunțuri vs țintă, cereri Gemini, chei).
- **Prompt rescris după Ghidul reporterului** — nu mai refuză SMS-uri doar pentru că jucătorul a scris `!!`, `100.000.000$`, „astept oferte” sau bonusuri; le curăță și publică.
- **Validator care compară anunțul cu SMS-ul** — numele, telefonul și fiecare număr (preț, buget, zile, kilometri, ID) trebuie să vină din SMS. Nu mai ies bugete inventate de tipul `$30.000.000.000`.
- **Corectură automată** — dacă validatorul găsește o greșeală (VIP pe vehicul care nu poate fi VIP, „si” lipsă, preț greșit), Gemini primește o singură dată erorile și corectează; anunțurile prea lungi sunt scurtate local (preț, apoi hidden).
- **Maxim 122 de caractere** pe anunț (cu `/news ` = 128, cât acceptă jocul) — nu mai iese nimic tăiat.
- **Regula de 5 minute fără refuzuri** — dacă un jucător a primit anunț de curând, SMS-ul nou așteaptă și pleacă automat când trec cele 5 minute.
- **`/number` automat** — la `:49:30`, cine a pus `.` dar nu și-a dat telefonul primește `/number Nume`, iar numărul intră în formulă.
- **`Atentie, :58.`** pe `/f` (regula 25 din regulament), când organizezi.
- **Somații staff** — pagină nouă care te alertează (sunet, notificare, banner) când un admin/helper îți verifică prezența, pe orice chat.
- **`0 zile` → „cu 0 zile”**, `x1`/`1x` = hidden, `x2`/`2x` = dublu hidden, ID-ul casei opțional, FBI Truck acceptat, NRG-500 nu mai e VIP — toate după ghid.

---

<a id="demo"></a>
## 📸 screenshots

| Dashboard live | Autopilot AG |
|:---:|:---:|
| ![Dashboard](docs/screenshots/dashboard.png) | ![Autopilot](docs/screenshots/autopilot.png) |

| Limite & publicare | Fallback manual & ghid |
|:---:|:---:|
| ![Limite](docs/screenshots/autopilot-limits.png) | ![Ghid AG](docs/screenshots/autopilot-guide.png) |

| Inbox & validator | Formatter |
|:---:|:---:|
| ![Inbox](docs/screenshots/inbox.png) | ![Formatter](docs/screenshots/formatter.png) |

| Somații staff | Chei & limite |
|:---:|:---:|
| ![Somații staff](docs/screenshots/alerts.png) | ![Chei](docs/screenshots/keys.png) |

---

<a id="features"></a>
## ⚡ functii (scrise de AI, ca imi e lene)

| Funcție | Detaliu |
|---|---|
| **Autopilot AG complet** | Scanare `/f`, anunț, dots, listă, telefoane, start, continuare, stop. |
| **3 moduri** | `ORGANIZEZ AG` și `SOLO` selectabile; `ALĂTURAT` pornește automat când anunță alt organizator. |
| **Nu organizează peste altcineva** | Dacă alt organizator anunță primul, trimite `.` pe `/f` și intră ca participant. |
| **Organizator = s/c/s** | Participă mereu. Max **3** alți jucători, adică 4 telefoane în formulă. |
| **Formule la `:20`** | Start `:50:20`, continuare `:55:20`, stop `:59:20`; secunda este configurabilă. |
| **Fără formule târzii** | O acțiune ratată cu peste **10 secunde** este sărită intenționat. |
| **Alăturat = fără formule** | Nu trimite niciodată start/continuare/stop când organizează altcineva. |
| **Gemini + validator local** | Modelul formează după Ghidul reporterului; validatorul verifică structura și compară anunțul cu SMS-ul (nume, telefon, fiecare număr). Detaliile inventate sunt blocate, greșelile reparabile primesc o corectură. |
| **Regula de 5 minute** | SMS-ul venit prea devreme de la același jucător așteaptă și e procesat automat când trec cele 5 minute (dacă mai e timp până la stop). |
| **`/number` automat** | La `:49:30`, cine a dat `.` fără telefon primește `/number Nume`; răspunsul serverului e citit din chatlog. |
| **Somații staff** | Detectează verificările de prezență de la admin/helper pe orice chat și te alertează să răspunzi. |
| **Min / max anunțuri** | Minimul avertizează la stop; maximul este limită dură înainte de Gemini. Formulele nu se numără. |
| **Ritm `/news`** | Maximum un `/news` la fiecare **6.0s** (configurabil), atât anunțuri cât și formule. |
| **Publicare full auto** | Aduce SA-MP în față, verifică focusul, lipește și apasă Enter. Alternativ, clipboard. |
| **`/f` mereu SendInput** | Comenzile de organizare nu depind niciodată de clipboard. |
| **Multi-cheie** | Rotește automat cheile, pune cheia în cooldown la `429` și încearcă următoarea. |
| **Inbox + Formatter** | Vezi fiecare SMS, anunțul final, motivul refuzului și validează manual. |
| **Mod simulare** | Parcurge tot fluxul AG fără să trimită nimic în joc. |
| **Portabil** | Un singur `.exe`. Datele stau în `%APPDATA%\LazyNR`. |

### De ce e util în practică

- **Nu ratezi fereastra de `:20`** — acțiunile sunt programate pe secundă, nu la `:00`.
- **Nu publici peste limită** — SMS-urile peste maxim sunt refuzate înainte de a consuma Gemini.
- **Nu trimiți formulă când ești alăturat** — exact greșeala care enervează organizatorul.
- **Nu rămâi cu dots necolectate** — parserul este tolerant, iar fallback-ul manual completează ce a scăpat.
- **Nu publici anunț invalid** — validatorul local este a doua poartă după model.
- **Nu publici detalii inventate** — un preț sau un buget care nu e în SMS nu trece.
- **Nu ratezi o somație** — banner, sunet și notificare până confirmi.

---

<a id="cerinte"></a>
## 🖥️ system reqs

- Windows **10 / 11** (64-bit).
- **SA-MP** pornit, cu fereastra jocului detectabilă.
- **Chatlog activ**: `Documents\GTA San Andreas User Files\SAMP\chatlog.txt`.
- **Internet** pentru Gemini.
- O cheie Gemini — e gratuită, ți-o faci în 2 minute: [tutorial](#own-key).
- Pentru SendInput: dacă SA-MP rulează ca Administrator, pornește și Lazy NR ca Administrator.

> Dacă `chatlog.txt` nu există, scrie `/chatlog` în SA-MP și verifică din nou folderul `SAMP`.

---

<a id="start"></a>
## 🚀 cum instalez ai u

1. **Descarcă** `Lazy NR by RewardK.exe` din [Releases](../../releases/latest) și rulează-l. Nu are installer.
2. Fă-ți o [cheie Gemini gratuită](#own-key) și adaug-o în **Chei & limite**.
3. Mergi la **Autopilot**:
   - nume exact din joc;
   - telefon propriu;
   - rolul AG: `ORGANIZEZ AG` sau `SOLO` (`ALĂTURAT` pornește automat când anunță altcineva);
   - orele sesiunilor;
   - minimul / maximul de anunțuri.
4. Deschide SA-MP și asigură-te că chatlog-ul este activ.
5. Apasă **Pornește autopilotul**. Prima dată folosește **Simulare** ca să vezi tot fluxul fără să trimiți nimic.
6. La `:45` începe scanarea. Tu doar verifici panoul „Pașii AG în timp real” și logul.
7. Opțional: în **Somații staff** pune numele adminilor/helperilor de pe server.

> [!TIP]
> Pentru prima sesiune, pune `:46:30` ca oră de anunț. Este recomandarea pentru orice membru și îți lasă timp să citești chatul.

---

<a id="download"></a>
## 📦 Descărcare & integritate

**Fișier:** `Lazy NR by RewardK.exe`  
**Versiune:** `1.2.0.0`  
**Mărime:** `49.436.519` bytes (≈ 47,1 MiB)  
**SHA-256:**

```text
872aff25d01aa2f2885539501a18c468e749347b390e24e2cae9b2ae8db226c6
```

**VirusTotal:** [raport pentru hash-ul de mai sus](https://www.virustotal.com/gui/file/872aff25d01aa2f2885539501a18c468e749347b390e24e2cae9b2ae8db226c6).

> [!WARNING]
> Un `.exe` nesemnat, împachetat cu PyInstaller, poate primi 1–2 detecții izolate, care sunt de obicei **false positive de heuristică**. Nu există garanție absolută pentru niciun binar: verifică hash-ul, uită-te la raport și rulează doar din sursa în care ai încredere.
>
> Windows SmartScreen poate cere confirmare la prima rulare: **More info → Run anyway**. Dacă antivirusul tău blochează fișierul, verifică hash-ul înainte de orice altceva.

---

<a id="own-key"></a>
## 🛠️ Tutorial: cum îți pui propria cheie Gemini (facut de AI)

### 1. Ia o cheie din Google AI Studio

1. Intră pe [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey).
2. Autentifică-te cu contul Google.
3. Apasă **Create API key** / **Get API key**.
4. Alege un proiect (sau creează unul nou).
5. Copiază cheia generată. Poate începe cu `AQ.` sau `AIza`.

### 2. Adaugă cheia în aplicație

1. Deschide **Chei & limite**.
2. Scrie o etichetă utilă: `principal`, `rezervă`, `acasă`.
3. Lipește cheia.
4. Apasă **ADAUGĂ**.
5. Aplicația o testează imediat. Dacă e validă, apare un mesaj verde.

### 3. Dacă vrei mai multă capacitate

- Poți adăuga **mai multe chei**. Aplicația le rotește automat.
- La `429`, cheia intră în cooldown și se încearcă următoarea.
- Poți dezactiva temporar o cheie din checkbox-ul **activă**, fără să o ștergi.
- Butonul **TESTEAZĂ TOATE** verifică toate cheile dintr-o singură acțiune.

### 4. Unde se salvează

Cheile sunt salvate în **text simplu** în:

```text
%APPDATA%\LazyNR\config.json
```

Nu urca `config.json` pe GitHub și nu îl trimite nimănui. Dacă vrei să resetezi tot, închide aplicația și șterge folderul `%APPDATA%\LazyNR`.

![Chei & limite](docs/screenshots/keys.png)

---

<a id="ag"></a>
## 🧠 Moduri AG & cronologie

### Roluri

| Rol | Ce face |
|---|---|
| **ORGANIZEZ AG** | Scanează `/f` de la `:45`, anunță la ora aleasă dacă nu organizează altcineva, colectează maximum **3** dots, trimite lista, colectează telefoanele și pornește sesiunea ca **s/c/s**. |
| **SOLO** | Nu anunță și nu colectează. Pornește doar cu telefonul propriu și publică anunțuri între `:50–:59`. |
| **ALĂTURAT** | Dacă alt organizator anunță primul, trimite `.` pe `/f`, intră ca participant și **nu trimite niciodată formulele de sesiune**. |

### Cronologie

| Ora | Acțiune |
|---|---|
| `:45:00` | Începe scanarea chatului `/f`, inclusiv mesajele dinainte de pornirea aplicației. |
| `:45:00` / `:45:30` | Opțiuni de anunț doar pentru **lider / colider / tester / responsabil**. Aplicația afișează un warning galben, dar opțiunile rămân selectabile. |
| `:46:00` / `:46:30` | Anunț pentru orice membru. **`:46:30` este recomandat** și este default-ul. |
| `:47:00` | Lista de participanți pe `/f`. |
| `:49:30` | Termen pentru telefoane. Cine a dat `.` dar nu și numărul primește automat `/number Nume`. |
| `:50:20` | Start sesiune + formula oficială. |
| `:55:20` | Continuare + formula oficială. |
| `:58:00` | `Atentie, :58.` pe `/f` (doar când organizezi și ai participanți). Anunțurile continuă și după. |
| `:59:20` | Stop + formula oficială. |

### Reguli respectate automat

- **Nu organizezi peste primul anunț.** Dacă altcineva a anunțat între `:45` și ora ta, aplicația trimite `.` și se alătură.
- **Organizatorul este mereu s/c/s.** Nu există „organizez fără să joc”.
- **Maximum 3 alți participanți.** Tu + 3 = 4 telefoane în formulă.
- **Lista este trimisă la `:47`**, nu la `:50`.
- **Formulele sunt oficiale**, nu texte scrise de model.
- **O formulă întârziată este mai riscantă decât una lipsă.** După fereastra de 10 secunde, acțiunea este sărită.
- **Când ești alăturat, nu trimiți formule.** Publici doar anunțuri.
- **5 minute între anunțuri pentru același jucător.** SMS-ul venit mai devreme așteaptă, nu e refuzat.

### De ce `:20`?

Pentru că ceasul din joc se actualizează cu întârziere față de cel al PC-ului. Trimiterea la `:50:20` reduce riscul ca formula să apară la `:49:59` sau să fie considerată târzie. Secunda este configurabilă, dar **20** este alegerea sigură.

---

<a id="limits"></a>
## 📊 Limite de anunțuri & ritm `/news`

| Setare | Comportament |
|---|---|
| **Minim / sesiune** | Țintă. `auto` = regula 40: minimum 5 anunțuri între 11:00–00:00 și 3 între 00:00–11:00. Dacă nu este atinsă, la stop apare un warning. Nu blochează publicarea. |
| **Lungime maximă** | `122` de caractere pe anunț (`/news ` + anunț = `128`, cât acceptă jocul). Anunțurile prea lungi sunt scurtate (preț, apoi hidden) sau refuzate. |
| **Maxim / sesiune** | Limită dură. SMS-urile peste ea sunt refuzate **înainte** de Gemini. `0` = fără limită. |
| **Interval minim `/news`** | Implicit `6.0s`. Se aplică anunțurilor și formulelor. Fiecare formulă are fereastră de 10 secunde; dacă throttle-ul ar face-o prea târzie, este sărită. |

- Se numără **doar anunțurile publicate**. Formulele de start / continuare / stop sunt excluse.
- Dacă o formulă ar trebui să aștepte peste fereastra de 10 secunde din cauza throttle-ului, este sărită.
- Minimul este o țintă, nu o garanție: dacă nu ai SMS-uri, nu are ce publica.

---

<a id="publish"></a>
## 📤 Publicare

| Mod | Cum funcționează |
|---|---|
| **FULL AUTO** | Aduce SA-MP în prim-plan, verifică focusul, lipește textul cu `Ctrl+V` (sau tastează caracter cu caracter) și apasă `Enter`. Recomandat. |
| **CLIPBOARD** | Copiază anunțul și așteaptă confirmarea „Am lipit” din Inbox. Pentru formule, trebuie să lipești imediat — aplicația avertizează. |

- Alegerea de publicare se aplică **doar anunțurilor** trimise cu `/news`.
- Comenzile pe `/f` (anunț AG, listă, `.`) folosesc **mereu full auto SendInput**, indiferent de modul de publicare.
- Dacă SA-MP rulează ca Administrator, pornește și Lazy NR ca Administrator. Altfel Windows blochează SendInput.

---

<a id="pages"></a>
## 🧭 Paginile aplicației

### Dashboard
Vezi dintr-o privire dacă autopilotul este pornit, următoarea acțiune cu numărătoare inversă, sesiunea, pasul AG, anunțurile publicate față de țintă, cererile Gemini de azi, ultimele evenimente și consumul pe chei.

### Autopilot
Aici configurezi tot fluxul:
- rolul AG;
- ora anunțului;
- numele și telefonul;
- orele de sesiune;
- secunda formulelor;
- limitele de anunțuri;
- modul de publicare;
- fallback-ul manual.

### Inbox
Fiecare SMS are un rând: textul primit, anunțul formatat, statusul, cheia folosită, durata și motivul refuzului. Poți copia anunțul sau confirma lipirea în modul clipboard.

### Formatter
Lipești un SMS complet (`SMS from Nume (1234): text`) sau completezi nume + telefon + text. Aplicația formatează cu Gemini și validează local. Verificările de oră și sesiune sunt relaxate, dar structura anunțului rămâne strictă.

### Somații staff
Detector pentru verificările de prezență de la admin/helper („esti la PC? raspunde…”), pe orice chat, indiferent de format. La o somație: banner roșu, sunet repetat, notificare Windows, iconița clipește, iar anunțurile noi așteaptă până apeși **Am văzut, răspund eu**. Poți adăuga numele staff-ului și cuvinte cheie proprii. Aplicația nu răspunde în locul tău.

### Chei & limite
Adaugi, testezi, activezi/dezactivezi sau ștergi chei. Vezi consumul pe fiecare cheie și erorile recente.

### Setări
Model, limite, fișiere, loguri și alte opțiuni tehnice.

### Loguri
Butonul **LOGURI** deschide un CMD separat, cu titlul `Lazy NR - LOGS`. Poți porni și direct:

```powershell
"Lazy NR by RewardK.exe" --console-log
```

<details>
<summary><b>Comenzi disponibile în fereastra de loguri</b></summary>

```text
/all /info /warn /err /debug /cat gemini /grep text /since HH:MM
/pause /follow /clear /help /close
```

</details>

---

<a id="fallback"></a>
## 🧩 Fallback manual pentru participanți

Parserul citește tolerant chatul `/f`: dots, liste de participanți și telefoane în formate uzuale. Când un jucător folosește un format necunoscut sau un mesaj este ratat, completează manual în **Autopilot → Participanți & fallback manual**, câte o linie:

```text
Rexxo: 1000
Daze - 0183
[NR] Andreea
# comentariu ignorat
```

- Fallback-ul completează **dots și telefoanele lipsă**.
- Nu suprascrie ce a fost deja colectat automat.
- Golește câmpul după fiecare sesiune, ca să nu reiei participanți vechi.

---

<a id="data"></a>
## 🔒 Date & confidențialitate

Toate datele stau în `%APPDATA%\LazyNR`:

| Fișier | Conținut |
|---|---|
| `config.json` | model, ore, identitate, rol AG, limite, chei API (text simplu) |
| `usage.json` | consum pe cheie și pe zi (ultimele 30 de zile) |
| `inbox.json` | SMS-uri procesate și rezultate |
| `logs\lazy-YYYY-MM-DD.log` | log text pentru fereastra CMD |
| `logs\events-YYYY-MM-DD.jsonl` | evenimente structurate |

- Exe-ul este portabil, dar datele rămân pe PC.
- Poți muta folderul de date cu variabila `LAZYNR_DATA` (util pentru teste).
- Aplicația nu are server propriu și nu trimite telemetrie.
- Textul SMS-urilor și contextul necesar sunt trimise la **Gemini** pentru formatare. Cheile sunt folosite doar pentru API-ul Gemini.
- `config.json` conține cheile în clar. Nu îl distribui.

---

<a id="faq"></a>
## ❓ faq

<details>
<summary><b>Pot folosi aplicația fără cheie Gemini?</b></summary>

Nu. Formatarea și decizia PUBLISH/REFUSE trec prin Gemini. Cheia e gratuită: [tutorial](#own-key).
</details>

<details>
<summary><b>Pot organiza dacă nu sunt lider / colider / tester / responsabil?</b></summary>

Da. Alege `:46:00` sau `:46:30`. Opțiunile de `:45` există, dar sunt pentru rangurile care au voie să deschidă AG-ul atât de devreme; aplicația afișează un warning galben.
</details>

<details>
<summary><b>Pot organiza fără să particip?</b></summary>

Nu. Organizatorul este mereu s/c/s și este primul telefon din formulă. Regula este intenționată.
</details>

<details>
<summary><b>Pot colecta mai mult de 3 dots?</b></summary>

Nu. Maximum 3 alți participanți. Al patrulea dot este ignorat.
</details>

<details>
<summary><b>De ce nu trimite formule când sunt alăturat?</b></summary>

Pentru că organizatorul este altcineva. Aplicația publică anunțuri între `:50–:59`, dar nu trimite start / continuare / stop peste el.
</details>

<details>
<summary><b>Ce se întâmplă dacă un alt organizator apare după ora mea?</b></summary>

Ideal este să nu se întâmple: ai anunțat primul. Dacă apare în timpul scanării, aplicația se alătură. Dacă apare după ce ai trimis anunțul, discută în joc și respectă regulile AG — aplicația nu poate negocia.
</details>

<details>
<summary><b>De ce s-a sărit o formulă?</b></summary>

Fereastra de 10 secunde a expirat. O formulă trimisă prea târziu poate fi sancționată, așa că aplicația o marchează ca sărită. Verifică logul și ceasul PC-ului.
</details>

<details>
<summary><b>De ce a stat un SMS „în așteptare”?</b></summary>

Jucătorul a primit anunț acum mai puțin de 5 minute (regula AG 33), sau ai o somație de la staff neconfirmată. SMS-ul se procesează automat când trec cele 5 minute, respectiv după ce apeși **Am văzut, răspund eu**.
</details>

<details>
<summary><b>Răspunde aplicația la somațiile staff-ului?</b></summary>

Nu. Te alertează ca să răspunzi tu în joc.
</details>

<details>
<summary><b>Datele mele ajung pe un server?</b></summary>

Nu există server Lazy NR. Doar cererile către Gemini pleacă în internet. Logurile și configul rămân local.
</details>

---

<a id="troubleshooting"></a>
## 🧯 Troubleshooting

| Problemă | Verifică |
|---|---|
| **JOC OPRIT** deși SA-MP este deschis | Rulează ambele cu aceleași drepturi (Administrator sau normal). Verifică numele ferestrei și procesul `gta_sa.exe`. Restartează aplicația după ce intri în joc. |
| **Nu vine niciun SMS** | Chatlog-ul este activ? Există `Documents\GTA San Andreas User Files\SAMP\chatlog.txt`? Scrie `/chatlog` în joc. |
| **`429` / `403` / cheie respinsă** | Quota s-a terminat sau cheia este invalidă. Testează cheia, adaugă una nouă sau folosește alta. |
| **Formulele sunt sărite** | Ceasul PC-ului este sincronizat? Ai pornit autopilotul prea târziu? Fereastra este de 10 secunde. |
| **Nu apasă Enter / nu lipește** | SA-MP rulează ca Administrator? Pornește Lazy NR la fel. Folosește **FULL AUTO** și verifică focusul. |
| **SmartScreen / antivirus** | `More info → Run anyway` după ce ai verificat hash-ul și raportul VirusTotal. |
| **Fallback-ul nu completează** | Folosește formatul `Nume: telefon`, câte o linie. Golește câmpul după sesiune. |
| **Alt organizator a apărut primul** | Aplicația trimite `.` și se alătură. Nu forța organizarea peste el. |

---

<a id="build"></a>
## 🧑‍💻 Build din sursă

```powershell
# clonează repo-ul, apoi intră în folder
cd lazy-nr
python -m pip install -r requirements.txt

python app.py                 # GUI
python app.py --selftest      # test rapid, fără afișare
python -m unittest discover -s tests -v
```

Build `.exe`:

```powershell
python -m PyInstaller --onefile --windowed --clean --noconfirm `
  --name "Lazy NR by RewardK" --icon assets/icon.ico `
  --add-data "assets;assets" --version-file build/version_info.txt `
  app.py
```

Rezultatul apare în `dist\Lazy NR by RewardK.exe`.

---

<a id="credits"></a>
## ❤️ Credits & disclaimer

**Făcut de RewardK** pentru toti smecherii

- Regulile AG ale comunității au prioritate față de orice automatizare.

<p align="center"><b>Lazy NR by RewardK · v1.2.0.0</b><br><code>made by RewardK</code></p>
