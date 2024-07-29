
### Zweck von Branches in der Entwicklung

Branches sind parallele Arbeitsbereiche innerhalb eines Git-Repositories. Sie ermöglichen es Entwicklern, neue Features oder Bugfixes zu entwickeln, ohne den Hauptzweig (oft `main` oder `master` genannt) zu beeinträchtigen. Dies fördert eine saubere und organisierte Entwicklung und erleichtert die Zusammenarbeit im Team.
Um mit Branches in GitHub zu arbeiten, folgen hier die Schritte, die du in der GitHub-Benutzeroberfläche und lokal über Git ausführen kannst:

### 1. Branches in GitHub erstellen

#### Erstellen eines Branches in der GitHub-Weboberfläche

1. Navigiere zu deinem Repository auf GitHub.
2. Klicke auf das Dropdown-Menü mit dem Branch-Namen (standardmäßig `main` oder `master`).
3. Gib den Namen des neuen Branches ein und drücke `Enter`.

#### Erstellen eines Branches lokal und pushen zu GitHub

1. Erstelle und wechsle zu einem neuen Branch lokal:

    ```bash
    git checkout -b <branch-name>
    ```

2. Push den neuen Branch zu GitHub:

    ```bash
    git push origin <branch-name>
    ```

### 2. Änderungen committen und pushen

1. Nachdem du Änderungen gemacht hast, füge sie zur Staging-Area hinzu und committe sie:

    ```bash
    git add <datei-name>
    git commit -m "Beschreibung der Änderung"
    ```

2. Push die Änderungen zu deinem Branch auf GitHub:

    ```bash
    git push origin <branch-name>
    ```

### 3. Einen Pull Request (PR) erstellen

1. Gehe zu deinem Repository auf GitHub.
2. Klicke auf die Schaltfläche "Pull request" im Hauptmenü.
3. Klicke auf die Schaltfläche "New pull request".
4. Wähle den Branch, den du mergen möchtest (z.B. `feature/new-feature`), und den Zielbranch (z.B. `main`).
5. Klicke auf "Create pull request".
6. Gib eine Beschreibung für deinen PR ein und klicke auf "Create pull request".

### 4. Merging von Branches in GitHub

Nachdem ein Pull Request erstellt wurde, kann der Branch gemergt werden:

1. Gehe zum Pull Request auf GitHub.
2. Klicke auf "Merge pull request".
3. Bestätige das Merging durch Klicken auf "Confirm merge".

### Merging von Branches im Terminal

#### Branches zusammenführen

Um einen Branch in den Hauptzweig zu mergen, wechsle zunächst zu dem Branch, in den du mergen möchtest (z.B. `main`), und führe dann den Merge-Befehl aus:

```bash
git checkout main
git merge <branch-name>
```

Beispiel:

```bash
git checkout main
git merge feature/new-feature
```

### 5. Merge-Konflikte

#### Was ist ein Merge-Konflikt?

Ein Merge-Konflikt tritt auf, wenn Änderungen in zwei Branches dasselbe Teil einer Datei betreffen und Git nicht automatisch entscheiden kann, welche Änderungen beibehalten werden sollen.

#### Lösen von Merge-Konflikten

Wenn ein Konflikt auftritt, musst du die betroffenen Dateien manuell bearbeiten. Git markiert die Konfliktstellen in der Datei, zum Beispiel so:

```plaintext
<<<<<<< HEAD
deine Änderungen
=======
die Änderungen aus dem anderen Branch
>>>>>>> branch-name
```

1. Ziehe die neuesten Änderungen vom Zielbranch:

    ```bash
    git checkout <branch-name>
    git pull origin <target-branch>
    ```

2. Bearbeite die betroffenen Dateien, um die Konflikte zu lösen.
3. Markiere die Konflikte als gelöst:

    ```bash
    git add <datei-name>
    ```

4. Committe die gelösten Konflikte:

    ```bash
    git commit -m "Resolve merge conflict"
    ```

5. Push die Änderungen:

    ```bash
    git push origin <branch-name>
    ```

6. Aktualisiere den Pull Request auf GitHub.

#### Änderung David