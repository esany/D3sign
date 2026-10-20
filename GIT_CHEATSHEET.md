# Git-Cheat-Sheet für D3sign

Repository: [github.com/esany/D3sign](https://github.com/esany/D3sign)

Der Hauptbranch heißt `main`.

## Einmalige Einrichtung auf einem Rechner

### 1. GitHub-Anmeldung einrichten

Die GitHub CLI ist bereits installiert. Wegen der verwalteten macOS-Konfiguration wird ein eigenes Konfigurationsverzeichnis verwendet:

```bash
mkdir -p ~/.gh-config
chmod 700 ~/.gh-config
export GH_CONFIG_DIR="$HOME/.gh-config"
```

Anmelden:

```bash
gh auth login
```

Im Dialog auswählen:

```text
GitHub.com
HTTPS
Login with a web browser
```

Danach Git für GitHub konfigurieren:

```bash
gh auth setup-git
gh auth status
```

Damit die Konfiguration auch in neuen Terminal-Sitzungen gilt:

```bash
echo 'export GH_CONFIG_DIR="$HOME/.gh-config"' >> ~/.zshrc
source ~/.zshrc
```

### 2. Repository frisch lokal holen

```bash
cd /Users/elapczyna/projects
git clone https://github.com/esany/D3sign.git
cd D3sign
```

Prüfen:

```bash
git branch --show-current
git remote -v
```

## Änderungen von GitHub lokal aktualisieren

Zuerst in den lokalen Repository-Ordner wechseln:

```bash
cd /Users/elapczyna/projects/D3sign
```

Lokalen Zustand prüfen:

```bash
git status
```

Wenn keine lokalen Änderungen vorhanden sind:

```bash
git pull --ff-only origin main
```

`--ff-only` verhindert, dass Git ungefragt einen Merge-Commit erzeugt.

## Lokale Änderungen online sichern

### 1. Vor dem Arbeiten den aktuellen Remote-Stand holen

```bash
git pull --ff-only origin main
```

### 2. Lokal arbeiten

Dateien bearbeiten, neue Dateien anlegen oder Dokumentation aktualisieren.

### 3. Änderungen prüfen

```bash
git status
git diff
```

### 4. Änderungen für den Commit vormerken

```bash
git add -A
```

Danach kontrollieren, was tatsächlich in den Commit kommt:

```bash
git status
```

### 5. Commit erstellen

```bash
git commit -m "Beschreibung der Änderung"
```

Beispiele:

```bash
git commit -m "docs: update toggle migration learnings"
git commit -m "fix: update semantic token mappings"
```

### 6. Zum Online-Repository pushen

```bash
git push origin main
```

Beim ersten Push eines neuen lokalen Branches kann zusätzlich nötig sein:

```bash
git push -u origin main
```

## Wenn das Remote inzwischen weiter ist

Wenn `git push` mit `rejected` oder `non-fast-forward` abbricht, zuerst aktualisieren:

```bash
git pull --rebase origin main
```

Danach erneut pushen:

```bash
git push origin main
```

Bei Konflikten:

```bash
git status
```

Konfliktdateien bearbeiten, danach:

```bash
git add <DATEI>
git rebase --continue
```

Den laufenden Rebase abbrechen:

```bash
git rebase --abort
```

Kein `git push --force` auf `main` verwenden, solange nicht ausdrücklich entschieden wurde, dass der Remote-Stand überschrieben werden darf.

## Schneller Standardablauf

Für einen normalen Arbeitstag genügt:

```bash
cd /Users/elapczyna/projects/D3sign
git pull --ff-only origin main

# Dateien bearbeiten
git status
git add -A
git commit -m "Beschreibung der Änderung"
git push origin main
```

## Abschlusskontrolle

```bash
git status --short --branch
git log -1 --oneline --decorate
```

Ein sauberer Stand sieht ungefähr so aus:

```text
## main...origin/main
```

Das bedeutet: lokaler Branch und Online-Branch zeigen auf denselben Stand.

## Was Git nicht automatisch sichert

- Figma-Dateien und Figma-Canvas-Änderungen bleiben in Figma.
- Nicht mit `git add` vorgemerkte Dateien werden nicht committed.
- Durch `.gitignore` ausgeschlossene Dateien wie `.DS_Store` werden nicht versioniert.
- Ungesicherte lokale Änderungen gehen beim Löschen des Ordners oder bei einem verworfenen Arbeitsstand verloren.

