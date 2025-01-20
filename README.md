### Mikä on Git?
Git on hajautettu versionhallintajärjestelmä, joka auttaa seuraamaan projektien, kuten ohjelmistojen, muutoksia. Se mahdollistaa useiden henkilöiden työskentelyn samassa projektissa samanaikaisesti ja auttaa hallitsemaan projektin eri versioita. Git on erityisen hyödyllinen, kun haluat:
- Yhteistyötä tiimissä ilman tiedostojen ylikirjoitusriskiä.
- Säilyttää täydellisen historiallisen näkymän projektin muutoksista.
- Palauttaa tiedostot aiempiin versioihin tarvittaessa.

Git toimii komentorivipohjaisesti, mutta siihen on saatavilla myös graafisia käyttöliittymiä, kuten GitHub Desktop, Sourcetree tai IDE-työkalujen (esim. Visual Studio Code) Git-integraatiot.

---

### Gitin peruskäyttö
Tässä on lyhyt opas Gitin peruskomentoihin ja käyttöön.

#### 1. **Gitin asentaminen**
Asenna Git tietokoneellesi [Git-sivustolta](https://git-scm.com/) ja varmista, että se on saatavilla komentorivillä:
```bash
git --version
```

---

#### 2. **Projektin aloittaminen**
- **Uuden Git-repositorion luominen:**
  Jos sinulla on projekti, jota et vielä hallinnoi Gitillä, mene projektikansioon ja kirjoita:
  ```bash
  git init
  ```
  Tämä luo `.git`-kansion, joka sisältää projektin versionhallintatiedot.

- **Clonaa olemassa oleva repositorio:**
  Jos haluat kopioida jo olemassa olevan Git-repositorion (esim. GitHubista):
  ```bash
  git clone <repository-url>
  ```

---

#### 3. **Tiedostojen lisääminen ja tallentaminen**
- **Muutosten tarkistaminen:**
  Näet kaikki muutetut ja uudet tiedostot komennolla:
  ```bash
  git status
  ```

- **Tiedostojen lisääminen commit-valmiiksi:**
  Lisää yksittäinen tiedosto:
  ```bash
  git add tiedosto.txt
  ```
  Tai kaikki muutokset:
  ```bash
  git add .
  ```

- **Muutosten tallentaminen (commit):**
  Tee commit lisätyille tiedostoille:
  ```bash
  git commit -m "Lyhyt kuvaus muutoksista"
  ```

---

#### 4. **Muutosten jakaminen ja hakeminen**
- **Push (muutosten lähettäminen palvelimelle):**
  Jos haluat jakaa paikalliset muutokset etärepositorioon, kuten GitHubiin:
  ```bash
  git push origin päähaara
  ```

- **Pull (uusien muutosten hakeminen):**
  Hae ja yhdistä viimeisimmät muutokset etärepositoriosta:
  ```bash
  git pull origin päähaara
  ```

---

#### 5. **Haarojen hallinta**
Haarat mahdollistavat erillisten ominaisuuksien tai korjausten kehittämisen ilman, että ne vaikuttavat pääprojektiin.
- **Uuden haaran luominen:**
  ```bash
  git branch uusi-haara
  ```

- **Haaran vaihtaminen:**
  ```bash
  git checkout uusi-haara
  ```

- **Haarojen yhdistäminen:**
  Palaa päähaaraan ja yhdistä uusi haara siihen:
  ```bash
  git merge uusi-haara
  ```

---

### Esimerkki Git-työskentelystä
1. **Aloita projekti ja lisää Git:**
   ```bash
   git init
   ```
2. **Lisää tiedostoja ja tee commit:**
   ```bash
   git add .
   git commit -m "Ensimmäinen commit"
   ```
3. **Linkitä etärepositorio (esim. GitHub):**
   ```bash
   git remote add origin <repository-url>
   git push -u origin main
   ```
4. **Tee muutoksia, commit ja push:**
   ```bash
   git add .
   git commit -m "Lisätty uusi ominaisuus"
   git push
   ```
   # Git-ohjeet

## Git-peruskomennot

1. **`git add`**
   - Lisää tiedostoja tai muutoksia versiohallintaan.
   - Esimerkki:
     ```bash
     git add tiedosto.txt
     git add . # Lisää kaikki muutokset nykyisessä hakemistossa
     ```

2. **`git commit`**
   - Tallentaa lisätyt muutokset versiohistoriaan.
   - Esimerkki:
     ```bash
     git commit -m "Kuvaus muutoksista"
     ```

3. **`git status`**
   - Näyttää tilan, kuten muuttuneet ja lisäystä odottavat tiedostot.
   - Esimerkki:
     ```bash
     git status
     ```

4. **`git push`**
   - Lähettää paikalliset muutokset etärepositorioon (esim. GitHub).
   - Esimerkki:
     ```bash
     git push origin main
     ```

5. **`git branch`**
   - Näyttää olemassa olevat haarat tai luo uuden haaran.
   - Esimerkki:
     ```bash
     git branch # Näyttää haarat
     git branch uusi-haara # Luo uuden haaran
     ```

---

## Muutosten peruminen

1. **`git checkout`**
   - Palauttaa tiedoston aiempaan tilaan tai vaihtaa haaraan.
   - Esimerkki:
     ```bash
     git checkout tiedosto.txt # Palauttaa tiedoston muutokset
     git checkout toinen-haara # Vaihtaa haaraan
     ```

2. **`git revert`**
   - Luo uuden commitin, joka kumoaa tietyn commitin muutokset.
   - Esimerkki:
     ```bash
     git revert COMMIT_ID
     ```

3. **`git reset`**
   - Peruuttaa committeja tai siirtää muutoksia takaisin työhakemistoon.
   - Esimerkki:
     ```bash
     git reset --soft HEAD~1 # Peruuttaa commitin, mutta säilyttää muutokset
     git reset --hard HEAD~1 # Peruuttaa commitin ja poistaa muutokset
     ```

---

## GitHub ja paikallisen repositorion yhdistäminen

1. **Linkitys GitHub-repositorioon**
   - Alusta paikallinen repositorio ja linkitä se GitHubiin:
     ```bash
     git init
     git remote add origin https://github.com/kayttaja/repo.git
     ```

2. **Tietojen lähettäminen paikallisesta GitHubiin**
   - Lisää, commitoi ja lähetä:
     ```bash
     git add .
     git commit -m "Ensimmäinen commit"
     git push -u origin main
     ```

3. **Tietojen hakeminen GitHubista**
   - Hae ja yhdistä muutokset paikallisesti:
     ```bash
     git pull origin main
     ```

---

## Forkkaaminen ja forkkaamisen käyttö

1. **Forkkaa toisen henkilön repositorio GitHubissa**
   - Paina *Fork* -painiketta halutun repositorion GitHub-sivulla.

2. **Kloonaa fork paikalliseen hakemistoon**
   - Lataa fork paikallisesti:
     ```bash
     git clone https://github.com/oma-kayttajanimi/forkattu-repo.git
     ```

3. **Lisää upstream alkuperäiselle repositoriolle**
   - Linkitä alkuperäinen repositorio (upstream):
     ```bash
     git remote add upstream https://github.com/alkuperainen-kayttajanimi/alkuperainen-repo.git
     ```

4. **Käytä upstreamia**
   - Hae alkuperäisen repositorion muutokset:
     ```bash
     git fetch upstream
     ```
   - Yhdistä muutokset paikalliseen haaraan:
     ```bash
     git merge upstream/main
     ```

---

## Yhteenveto
- Opettele peruskomennot (`git add`, `git commit`, `git push` jne.).
- Hyödynnä `git revert` ja `git reset` tarvittaessa muutosten kumoamiseen.
- Linkitä paikallinen repositorio GitHubiin ja käytä `git pull` sekä `git push` tietojen synkronoimiseen.
- Forkkaa, kloonaa ja linkitä upstream, jos työskentelet toisten projektien pohjalta.





[Wikipedia Gitistä](https://fi.wikipedia.org/wiki/Git)
![image](https://github.com/user-attachments/assets/270699ee-524a-4545-a358-5c1298454d3e)
