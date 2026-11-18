<div align="center">
  <img src="docs/screenshots/icon.png" width="104" alt="Lazy NR by RewardK">
  <h1>Lazy NR <code>by RewardK</code></h1>
  <p><b>Autopilot AG pentru News Reporters.</b><br>
  De la SMS la anunț validat, de la <code>:45</code> la <code>:59</code>, fără să stai cu ochii pe chat.</p>
  <p>
    <a href="#download"><img src="https://img.shields.io/badge/version-1.3.0.0-00ff6a?style=flat-square" alt="Version"></a>
    <a href="#cerinte"><img src="https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078d4?style=flat-square" alt="Platform"></a>
    <a href="#download"><img src="https://img.shields.io/badge/portable-.exe-8b5cf6?style=flat-square" alt="Portable"></a>
    <a href="https://www.virustotal.com/gui/home/upload"><img src="https://img.shields.io/badge/VirusTotal-scan%20before%20run-f5c542?style=flat-square" alt="VirusTotal"></a>
    <a href="#credits"><img src="https://img.shields.io/badge/made%20by-RewardK-00ff6a?style=flat-square" alt="Made by RewardK"></a>
  </p>
  <p>
    <a href="../../releases/latest"><b>⬇️ Descarcă exe-ul</b></a> ·
    <a href="#own-key"><b>🔑 Cheia Gemini</b></a> ·
    <a href="#demo"><b>📸 Screenshot-uri</b></a> ·
    <a href="#faq"><b>❓ Întrebări</b></a>
  </p>
</div>

---

## Ce este Lazy NR?

Lazy NR este un **copilot pentru sesiunile AG** din SA-MP. Primește SMS-urile din chatlog, le formatează cu Gemini, le verifică încă o dată cu un validator local și le publică pe `/news` cu limită de ritm. Pentru organizare, rulează singur toată coloana oficială: scanare `/f`, anunț, colectare dots, listă, telefoane, start, continuare și stop.

Nu trebuie să fii lider ca să organizezi. Trebuie doar să respecți regula: **nu organizezi peste primul anunț** și **participi mereu ca s/c/s**.

> [!IMPORTANT]
> Organizatorul joacă. Aplicația nu are modul „organizez fără să particip”. Dacă intri ca organizator, ești primul nume din formulă, mereu ca **s/c/s**.

---

<a id="demo"></a>
## 📸 Cum arată

| Dashboard live | Autopilot AG |
|:---:|:---:|
| ![Dashboard](docs/screenshots/dashboard.png) | ![Autopilot](docs/screenshots/autopilot.png) |

| Limite & publicare | Fallback manual & ghid |
|:---:|:---:|
| ![Limite](docs/screenshots/autopilot-limits.png) | ![Ghid AG](docs/screenshots/autopilot-guide.png) |

| Inbox & validator | Formatter |
|:---:|:---:|
| ![Inbox](docs/screenshots/inbox.png) | ![Formatter](docs/screenshots/formatter.png) |

| NO Autoclicker |
|:---:|
| ![NO Autoclicker](docs/screenshots/alerts.png) |

---

<a id="features"></a>
## ⚡ Ce face

| Funcție | Detaliu |
|---|---|
| **Autopilot AG complet** | Scanare `/f`, anunț, dots, listă, telefoane, start, continuare, stop. |
| **3 moduri** | `ORGANIZEZ AG` și `SOLO` selectabile; `ALĂTURAT` pornește automat când anunță alt organizator. |
| **Nu organizează peste altcineva** | Dacă alt organizator anunță primul, trimite `.` pe `/f` și intră ca participant. |
| **Organizator = s/c/s** | Participă mereu. Max **3** alți jucători, adică 4 telefoane în formulă. |
| **Formule la `:20`** | Start `:50:20`, continuare `:55:20`, stop `:59:20`; secunda este configurabilă. |
| **Fără formule târzii** | O acțiune ratată cu peste **10 secunde** este sărită intenționat. |
| **Alăturat = fără formule** | Nu trimite niciodată start/continuare/stop când organizează altcineva. |
| **Gemini + validator local** | Modelul formează, validatorul verifică structura după Ghidul reporterului și compară anunțul cu SMS-ul: telefonul, numele și fiecare număr (sumă, zile, kilometri, ID) trebuie să vină din SMS — detaliile inventate sunt blocate. |
| **Regula de 5 minute** | Dacă un jucător a primit anunț acum mai puțin de 5 minute, SMS-ul nou intră în așteptare și e procesat automat când trec cele 5 minute (dacă mai e timp până la stop). |
| **Min / max anunțuri** | Minimul avertizează la stop; maximul este limită dură înainte de Gemini. Formulele nu se numără. |
| **Ritm `/news`** | Maximum un `/news` la fiecare **6.0s** (configurabil), atât anunțuri cât și formule. |
| **Publicare full auto** | Aduce SA-MP în față, verifică focusul, lipește și apasă Enter. Alternativ, clipboard. |
| **`/f` mereu SendInput** | Comenzile de organizare nu depind niciodată de clipboard. |
| **Multi-cheie** | Rotește automat cheile, pune cheia în cooldown la `429` și încearcă următoarea. |
| **Inbox + Formatter** | Vezi fiecare SMS, anunțul final, motivul refuzului și validează manual. |
| **NO Autoclicker** | Detectează somațiile de prezență pe orice chat și răspunde automat pe chatul public, cu mesaj formulat de Gemini sau prestabilit. Dacă răspunsul nu pleacă în 2 minute, trimite `/q`. |
| **Mod simulare** | Parcurge tot fluxul AG fără să trimită nimic în joc. |
| **Portabil** | Un singur `.exe`. Datele stau în `%APPDATA%\LazyNR`. |

### De ce e util în practică

- **Nu ratezi fereastra de `:20`** — acțiunile sunt programate pe secundă, nu la `:00`.
- **Nu publici peste limită** — SMS-urile peste maxim sunt refuzate înainte de a consuma Gemini.
- **Nu trimiți formulă când ești alăturat** — exact greșeala care enervează organizatorul.
- **Nu rămâi cu dots necolectate** — parserul este tolerant, iar fallback-ul manual completează ce a scăpat.
- **Nu publici anunț invalid** — validatorul local este a doua poartă după model.

---

<a id="cerinte"></a>
## 🖥️ Cerințe

- Windows **10 / 11** (64-bit).
- **SA-MP** pornit, cu fereastra jocului detectabilă.
- **Chatlog activ**: `Documents\GTA San Andreas User Files\SAMP\chatlog.txt`.
- **Internet** pentru Gemini.
- O cheie Gemini — îți faci una proprie, vezi [tutorialul de mai jos](#own-key).
- Pentru SendInput: dacă SA-MP rulează ca Administrator, pornește și Lazy NR ca Administrator.

> Dacă `chatlog.txt` nu există, scrie `/chatlog` în SA-MP și verifică din nou folderul `SAMP`.

---

<a id="start"></a>
## 🚀 Pornire rapidă

1. **Descarcă** `Lazy NR by RewardK.exe` din [Releases](../../releases/latest) și rulează-l. Nu are installer.
2. Mergi la **Chei & limite** și adaugă o cheie a ta Gemini.
3. Mergi la **Autopilot**:
   - nume exact din joc;
   - telefon propriu;
   - rolul AG: `ORGANIZEZ AG` sau `SOLO` (`ALĂTURAT` pornește automat când anunță altcineva);
   - orele sesiunilor;
   - minimul / maximul de anunțuri.
4. Deschide SA-MP și asigură-te că chatlog-ul este activ.
5. Apasă **PORNEȘTE AUTOPILOTUL**. Prima dată folosește **Mod simulare** ca să vezi tot fluxul fără să trimiți nimic.
6. La `:45` începe scanarea. Tu doar verifici panoul „Pașii AG în timp real” și logul.

> [!TIP]
> Pentru prima sesiune, pune `:46:30` ca oră de anunț. Este recomandarea pentru orice membru și îți lasă timp să citești chatul.

---

<a id="download"></a>
## 📦 Descărcare & integritate

**Fișier:** `Lazy NR by RewardK.exe`  
**Versiune:** `1.3.0.0`  
**Mărime:** `46.826.797` bytes (≈ 44,7 MiB)  
**SHA-256:**

```text
d1b8f579e467b08e8e29abd172ed5bb546d0409074fb81c1cd0ae10a4744f870
```

**VirusTotal:** [încarcă hash-ul de mai sus](https://www.virustotal.com/gui/home/upload) înainte de prima rulare — exe-ul este nesemnat.

> [!WARNING]
> Raportul arată **1 detecție izolată din 69**. Pentru un `.exe` nesemnat, împachetat cu PyInstaller, este cel mai probabil un **false positive de heuristică**. Nu există garanție absolută pentru niciun binar: verifică hash-ul, uită-te la raport și rulează doar din sursa în care ai încredere.
>
> Windows SmartScreen poate cere confirmare la prima rulare: **More info → Run anyway**. Dacă antivirusul tău blochează fișierul, verifică hash-ul înainte de orice altceva.

---

<a id="own-key"></a>
## 🛠️ Tutorial: cum îți pui propria cheie Gemini

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
| `:49:30` | Termen pentru telefoane. Cine a dat `.` dar nu și numărul primește automat `/number Nume`; răspunsul (`Name: X | Number: 1234`) e citit din chatlog. |
| `:50:20` | Start sesiune + formula oficială. |
| `:55:20` | Continuare + formula oficială. |
| `:58:00` | `Atentie, :58.` pe `/f` (regula 25; doar ca organizator, dacă ai participanți). Anunțurile continuă și după. |
| `:59:20` | Stop + formula oficială. |

### Reguli respectate automat

- **Nu organizezi peste primul anunț.** Dacă altcineva a anunțat între `:45` și ora ta, aplicația trimite `.` și se alătură.
- **Organizatorul este mereu s/c/s.** Nu există „organizez fără să joc”.
- **Maximum 3 alți participanți.** Tu + 3 = 4 telefoane în formulă.
- **Lista este trimisă la `:47`**, nu la `:50`.
- **Formulele sunt oficiale**, nu texte scrise de model.
- **O formulă întârziată este mai riscantă decât una lipsă.** După fereastra de 10 secunde, acțiunea este sărită.
- **Când ești alăturat, nu trimiți formule.** Publici doar anunțuri.

### De ce `:20`?

Pentru că ceasul din joc se actualizează cu întârziere față de cel al PC-ului. Trimiterea la `:50:20` reduce riscul ca formula să apară la `:49:59` sau să fie considerată târzie. Secunda este configurabilă, dar **20** este alegerea sigură.

---

<a id="limits"></a>
## 📊 Limite de anunțuri & ritm `/news`

| Setare | Comportament |
|---|---|
| **Minim / sesiune** | Țintă. `auto` (0) = regula 40: minimum 5 anunțuri între 11:00–00:00, 3 între 00:00–11:00. Dacă nu este atinsă, la stop apare un warning. Nu blochează publicarea. |
| **Maxim / sesiune** | Limită dură. SMS-urile peste ea sunt refuzate **înainte** de Gemini. `0` = fără limită. |
| **Lungime maximă** | `122` de caractere pentru anunț (`/news ` + anunț = maxim `128`, cât acceptă inputul SA-MP). Dacă Gemini dă un anunț prea lung, aplicația cere o singură dată o variantă scurtată; altfel îl refuză. |
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
Vezi dintr-o privire dacă autopilotul este pornit, ce sesiune rulează, în ce pas este AG-ul, câte cereri ai făcut azi și ultimele evenimente.

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
- Dacă un participant nu are telefon nici din `/f`, nici din fallback, la `:49:30` aplicația trimite `/number Nume` și ia numărul din răspuns.
- Nu suprascrie ce a fost deja colectat automat.
- Golește câmpul după fiecare sesiune, ca să nu reiei participanți vechi.

---

<a id="staff"></a>
## 🚨 NO Autoclicker

Pagina **NO Autoclicker** citește toate chaturile din chatlog și detectează când un admin, un helper sau alt jucător îți verifică prezența (ex: `(/w) X whispers: esti la PC? Raspunde sau vei fi sanctionat`), pe orice chat și fără să depindă de un format anume. Fiecare linie primește un scor: mesaj adresat ție / privat (+2), verificare de prezență — „la pc”, „afk”, „autoclick”, „macro” (+2), amenințare cu sancțiune (+1), „raspunde” (+1), expeditor din lista ta de staff (+2). De la 4 puncte: banner roșu, sunet repetat, notificare Windows, iar anunțurile noi așteaptă până confirmi.

Dacă opțiunea de răspuns automat este pornită, aplicația formulează un răspuns scurt, iritat, fără jigniri („da ma normal ca sunt”) și îl trimite pe **chatul public** după circa 2 secunde — timp în care poți apăsa **Anulează**. Dacă Gemini nu răspunde, folosește mesajul prestabilit. Deduplicarea este pe expeditor + text (10 minute), cu maximum 5 răspunsuri pe oră. Dacă răspunsul nu poate fi trimis în 120 de secunde, aplicația trimite `/q` și închide jocul, ca să nu rămâi cu autoclickerul pornit.

Butoanele din pagină: **Trimite acum**, **Regenerează**, **Anulează**, **Am răspuns eu**. «Am răspuns eu» confirmă somația și oprește și răspunsul automat și `/q`.

---

<a id="eval"></a>
## 🧪 Evaluarea promptului

`tests/cases.jsonl` conține SMS-uri reale și exemple din Ghidul reporterului, fiecare cu anunțul corect (sau `REFUSE`). Scriptul le trece prin Gemini și validator și dă un scor:

```powershell
python tools/eval_prompt.py              # toate cazurile (~1 cerere Gemini / caz)
python tools/eval_prompt.py --source inbox
python tools/eval_prompt.py --offline    # fără Gemini: verifică doar validatorul
python tools/eval_prompt.py --hard       # doar cazurile grele
python tools/eval_prompt.py --grep Mihai # doar cazurile care conțin textul
```

Când vezi în joc un refuz greșit sau un anunț greșit, adaugă SMS-ul în `cases.jsonl` cu rezultatul corect și rulează din nou după ce schimbi promptul.

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
## ❓ Întrebări rapide

<details>
<summary><b>Pot folosi aplicația fără cheie Gemini?</b></summary>

Nu. Formatarea și decizia PUBLISH/REFUSE trec prin Gemini, deci ai nevoie de o cheie proprie — vezi [tutorialul de mai sus](#own-key).
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

**Făcut de RewardK** pentru comunitatea News Reporters.

- Nu este afiliat oficial cu **buGGed.ro**, **SA-MP** sau **Rockstar Games**.
- Regulile AG ale comunității au prioritate față de orice automatizare.
- Aplicația este un ajutor, nu un scut: verifică întotdeauna ce trimite.
- Exe-ul este nesemnat, deci SmartScreen sau antivirusul pot cere confirmare.
- Dacă îți place proiectul, lasă un **star** pe GitHub și spune-mi ce mai adaugi.

<p align="center"><b>Lazy NR by RewardK · v1.3.0.0</b><br><code>made by RewardK</code></p>
