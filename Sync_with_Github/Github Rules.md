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