---
marp: true
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
---

![bg left:40% 80%](./img/logo.png)

# **GitItDone**

Slides voor GitItDone workshop van het IT-lab

---

<!-- Link naar Marp documentatie: https://marpit.marp.app/ -->

<!-- # How to write slides

Split pages by horizontal ruler (`---`). It's very simple! :satisfied:

```markdown
# Slide 1

foobar

---

# Slide 2

foobar
```

--- -->



![Git logo](./img/Git-Logo-2Color.png)

---

# Meevolgen op:
https://hogent-it-lab.github.io/gititdone-workshop/slides

![QR bg right contain](./img/link_qr.png)

---

# Wat is Git?
- Git is een version control system (VCS)
  - Hou een historie bij van je project en alle wijzigingen
  - Wijzigingen worden systematisch bijgehouden
  - Keer eenvoudig terug naar oudere versies (handig bij fouten...)
  - Leuk om evolutie en voortgang van project te zien

---

# Een beetje geschiedenis...

- Ontworpen en uitgebracht in 2005
- Gemaakt door Linus Torvalds voor development van Linux
- Grote populariteit en meestgebruikte VCS vandaag de dag

![bg right:40% 90%](./img/Linus_Torvalds.jpg)

---

# Account maken op een git server
https://www.github.com (**GitHub ≠ Git**)

![git_signup w:1140](./img/git_signup.png)

---

# Je git account

**Stuur nu het gebruikte email-adres door naar alexander.veldeman@hogent.be**
![alexander w:1140](./img/alexander.jpg)

---

# Git installeren

- Beschikbaar voor Windows, MacOS en Linux (uiteraard)
  - Download voor jouw systeem de juiste [versie](https://git-scm.com/downloads)
  - Windows: [Git Bash](https://gitforwindows.org/) is ook een optie

![bg right:50% 80%](./img/git_download_prentje.png)

---

# Installatie controleren

Commando `git`
Bijvoorbeeld: `git --version`

```
C:\Users\sion_\Documents\gititdone-workshop> git --version
git version 2.30.1.windows.1
```

---

# Git configureren

Commando: `git config`
- `git config -l`: oplijsten
- `git config --global -l`: instellingen voor heel het systeem
- In een git map (later): `git config --local -l`
- Instellingen aanpassen: `git config --global user.name NieuweNaam`

---

- Email en naam instellen **op waarden van GitHub account**
```
git config --global user.name <USERNAME>
```
```
git config --global user.email <JOUW@EMAIL.ADRES>
```
Resultaat:
```
git config --global -l
user.email=sion.verschraege@hogent.be
user.name=sionverschraege
```

---

# Geavanceerde configuratie

- Lokaal heeft voorrang op globaal
- Mensen die meerdere accounts hebben:
  - Globaal meest gebruikte naam/email
  - Lokaal per repo voor andere account
  - Verschillende SSH-keys nodig

---

# Git configureren - SSH sleutels

Data **encrypteren** en **handtekenen**
Hoe genereer ik zo'n sleutelpaar? `ssh-keygen -t ed25519 -C "email@hogent.be"` 
- aanhaalingstekens (`"`) moeten er staan

Terug te vinden in `[je home folder]/.ssh`:
![keys](./img/keys.png)

---

# Public key uploaden op GitHub

Settings -> SSH and GPG keys -> new SSH key
- Kies een goede naam
- Kies "Authentication Type"
- Plak de sleutel **vanuit het pub bestand** in het tekstvak
- Test met `ssh -T git@github.com`
```
ssh -T git@github.com
Hi sionverschraege! You've successfully authenticated, but GitHub does not provide shell access.
```

---

# Repository clonen
Code van op de **git server** (github, **remote repository**) kopiëren naar eigen pc (**local repository**)
- Deze slides (gemaakt in **markdown-code**) zijn [publiek](https://github.com/HOGENT-IT-Lab/gititdone-workshop)!
- `git clone git@github.com:HOGENT-IT-Lab/gititdone-workshop.git` 

![Git clone link w:800](./img/git%20clone%20link.png)

---
# Git - commits

- Om veranderingen bij te houden, maken we gebruik van **commits**
- Commits bekijken: `git log` in git-mapje
- Commits bevatten één of meerdere **wijzigingen** in onze repository
- Commits hebben altijd een bijhorende **commit message**
- Commits hebben altijd een unieke **commit hash**
<!-- - Uitleg dat alle veranderingen worden bijgehouden in een 'commit'
- Elke commit krijgt dan ook een commit hash (lange en korte eens uitleggen)
- In een commit kunnen meerdere veranderingen tegelijk zitten -> we proberen ze allemaal atomair te houden!
- Commit messages - BELANGRIJK!!!
- Wat is HEAD en HEAD(~1) -->

---

# Commits - tips en best practices

- Probeer je commits **atomair** te houden! (commit heeft een doel)
- Schrijf duidelijke commit messages!
- Kom tot overeenkomst/structuur met jouw team (samenwerken)

---

# Wat is een .gitignore bestand?

Soms wil je sommige zaken niet bijhouden in jouw version control (denk aan wachtwoorden, sensitieve data,...) 
- `.gitignore` definieert wat je niet wilt tracken

- Er bestaan heel wat templates voor verschillende projecten!

- Kan ook wildcards gebruiken

---

# .gitignore - voorbeeld Java project
```
# Compiled class file
*.class

# Log file
*.log

# Package Files
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar
```

---
# Git workflow

![bg right:60% 80%](./img/git-workflow.png)

<!-- - Veranderingen bijhouden en zo doen aan version control!
- Met remote: zelfde concept, maar collaboratief!
- Meerdere slides hiervan maken hoor! -->
<!-- IMG source: https://www.dezlearn.com/getting-started-with-git/ -->

---

# Git - command line versus GUI

Git kan je zowel via de CLI als GUI gebruiken

- CLI: snel en efficiënt, iets hogere learning curve (maar niet veel!)
- GUI: handig voor een visueel overzicht, maar er gebeurt veel *under the hood*
- Vele IDE's hebben Git support ingebouwd!

---

# Voorbeeld: GitHub Desktop

![Git gui w:1120](./img/git_gui.png)

<!-- ---


# Git - command line en basiscommando's

- git clone
- git fetch
- git pull
- git add
- git commit 
- git push (remote nodig!) -->

---
# Basiscommando's - algemeen

- Huidige toestand/situatie bekijken
```
git status  
 ```
 Gebruik dit commando na/voor elk ander commando!

- Historie/commits weergeven
```
git log
```

---

# Basiscommando's - nieuwe repo
- Van een lokale map een git repository maken
```
git init
```
- Een repository binnenhalen (klonen)
```
git clone <URL>
```

---


## Basiscommando's - lokaal naar remote

- Wijzigingen in working directory aan staging toevoegen
```
git add <FILE>
```
- Alles toevoegen aan staging
```
git add .
```
- Wijzigingen in stage aan de lokale git-repository toevoegen

```
git commit
```

---

- Meteen een (duidelijke!) commit message toevoegen
```
git commit -m "DIT IS MIJN COMMIT MESSAGE"
```

- Lokale repository naar een remote repository
```
git push
```
Tip: stel pushen niet uit! Vermijd merge conflicten (zie later)

---

# Tijd voor een testpush!

- Maak een repository op github.com
- Clone: `git clone git@github.com:sionverschraege/testrepo.git`
- Maak een nieuw bestandje aan **in de lokale working directory**
- Voeg het bestand toe aan de **staging area**: `git add test.txt`
- Maak een **commit** van alles in de staging area: `git commit -m "added test file"`
- **Push** naar de remote repo: `git push`
- Bewonder je bestand op github.com

---

# Basiscommando's - lokaal

- Lokale git-repository naar working directory
```
git merge
```
---

# Basiscommando's - lokaal

- Unstagen van wijziging
```
git reset
```

- Recentste commit ongedaan maken
```
git reset HEAD~1
```

- Commit reverten met nieuwe commit
```
git revert
```
<!-- TO DO beter uitleggen in slides! -->

----
# Basiscommando's - remote

- Remote repository naar lokale repository
```
git fetch
```

Belangrijk! Je moet een remote repository ingesteld hebben

--- 

# Basiscommando's - remote

- Checken of er een remote is ingesteld

```
git remote
```

- Remote toevoegen aan lokale repository (bv origin)
```
git remote add origin <URL>
```

- Remote repository naar lokale werkomgeving (fetch + merge)

```
git pull
```

---


# Order matters...

![bg right:50% 80%](./img/git_grappig_plaatje.png)

--- 
# Demo basic workflow

- Klassieke git workflow
```
git add .

git commit -m "Fix myFunction function: supports multiple parameters now"

git pull

git push
```

---


# Git - branches

- Ruimte voor tekst, uitleg en/of oubollige meme?
![bg right:60% 80%](./img/branching_visual_cue.png)



---
# Branches - commando's

- Nieuwe branch aanmaken

```
git branch <NAAMBRANCH>
```
- Wisselen naar branch 
```
git checkout <NAAMBRANCH>
```
OF
```
git switch <NAAMBRANCH>
```

---


# Git - merge conflicten

- Wat zijn merge conflicten? 
- Wanneer ontstaan deze?
- Hoe kan je deze oplossen (BELANGRIJK - demo!!)

---

# Demo merge conflict

Laat ons eens een merge conflict veroorzaken en ook oplossen...

---
# Git - samenwerken

- Nood aan een remote repository!
- GitHub is een voorbeeld van zo'n provider/platform
- Git != GitHub
- Alternatieven bestaan ook (GitLab, Gitea, ...)



---

# GitHub specifiek

- Heel wat specifieke mogelijkheden binnen het platform
- GitHub Actions: automatisatie, testen en meer
- GitHub Pages: host statische websites en projecten gratis
- Webhooks: stel meldingen in voor veranderingen in repository (Discord, Slack, mail, ...)
- Pull requests: review en bekijk code/wijzigingen voor een push


---

# GitHub Pages

- Manier om statische websites te hosten
- Use case: deze slides! (in combinatie met GitHub Actions)
- Eenvoudige websites, basic applicaties, ...

![bg right:50% 90%](./img/pages_example.png)

---
# GitHub Actions

- Automatisatie en workflows (pipelines, testen, software bouwen,...)
- Zelf instellen van workflows en heel veel customisation

---
# GitHub Actions - voorbeeld

```
name: "Export and publish slides"
on:
  workflow_dispatch:

jobs:
  publish:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Convert markdown to PDF
        uses: KoharaKazuya/marp-cli-action@v3
```
---

# Git - advanced topics 

TO DO

- git rebase: in detail eens overgaan
<!-- - Meer advanced commando's? -->
- GitKraken of andere GUI tool demonsteren?
<!-- - Website hosten met GitHub pages -> kan gratis voor statische sites (zie huidige slides) -->
- DEMO's van vanalles moeten nog toegevoegd worden! (repo's, specifieke flows, use cases,...)

---

## Handige/interessante links

- Git(Hub) guide van HOGENT - https://hogenttin.github.io/git-hogent-gids/
- Leren branchen - https://learngitbranching.js.org/
- Templates .gitignore - https://github.com/github/gitignore
- Wat als het allemaal in de soep loopt? - https://ohshitgit.com/