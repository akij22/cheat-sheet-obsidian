# Github rules
**Una guida completa passo passo da consultare in ogni momento. Qui verranno trattati tutte le nozioni di base (e intermedie) riguardo la gestione delle proprie repository.**


### Init della repository
`git init`


### Verifica dello stato dello repo remota
`git remote -v`


### Commit, push e pull
* Commit: `git commit -m <comments>`
* Push: `git push origin main`
* Pull: `git pull <options>`

### .gitignore
Utilizzato per specificare repo / file da non includere nel commit e push

#### Rimozione di una repository
* `<file_repo>/`
#### Rimozione di tutti i file con estensione specifica
* `*.<extension>`


### Rimozione di un file / cartella dal version control
* `git rm -r --cached <file_name> / <repo_name>`


### Git Merge
Utilizzato per combinare due branch
* **Merge fast-forward**: si hanno due HEAD (origine e destinazione), che "puntano" a modifiche diverse. Mediante tale comando si "allineano" le due history. ![Merge fast-forward](https://lh3.googleusercontent.com/oHUfdg3aCKVzQA8-BarEdClJa3Opky1Pwm7G4lAkV_6DUwydkgChZPmPzJbccU8-ZlBVP8ijoxzd20RpLgYd1T5VdB6IbtEg0mE-xNB05RRDEuowmBOhvA_hAXEJxUGjLzv_AsuwFOueurWnFBYAFqRlNXgKJV30)
* **Three-way merge**: si combinano le history di due branch divergenti ![Three-way merge](https://lh6.googleusercontent.com/we7nfniAJIYe0J6sbUS5Gi2KnC5uitZhTpPI-87rYmR51KcgZGDct2fOe8fyyhM-LRTUuRm3qS0tz99YfE9qRyEgyLkLjW4N2sUypUKIVaWB7DX68yTD4r3CmmwmJmqtmRQuHC2-S1ZtqDtReoGybmUbKIP67EBb)