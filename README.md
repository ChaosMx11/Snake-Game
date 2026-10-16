# 🐍 Snake.py

Un jeu **Snake développé en Python avec Pygame**, réalisé dans le cadre de mon stage de seconde à la Faculté des sciences de Lille, au laboratoire CRIStAL.

Le but est de manger les pommes pour faire grandir le serpent et augmenter son score, tout en évitant les collisions. Le jeu propose un système de points de vie, des cœurs à récupérer et un enregistrement des meilleurs scores.

## 🎮 Fonctionnalités

- **Score** : chaque pomme mangée fait grandir le serpent et augmente le score.
- **Points de vie (HP)** : une collision avec le bord du terrain ou avec le corps du serpent fait perdre un point de vie.
- **Cœurs à récupérer** : un cœur peut apparaître tous les 10 points. Le récupérer rend un point de vie, sans dépasser le maximum de **3 HP**.
- **Records** : le meilleur score du joueur et le meilleur score enregistré dans le fichier local sont affichés.
- **Pseudo** : chaque joueur peut saisir un nom, utilisé pour retrouver son record personnel.
- **Vitesse progressive** : le serpent accélère au fur et à mesure qu'il grandit.
- **Graphismes pixel art** : le serpent, la pomme et les cœurs sont dessinés dans un style rétro.

Les records sont stockés localement dans `assets/records.xlsx` : ils ne sont pas synchronisés en ligne entre les différents utilisateurs ou ordinateurs.

## ⌨️ Commandes

| Touche | Action |
| --- | --- |
| `Z` / `Q` / `S` / `D` | Déplacer le serpent vers le haut, la gauche, le bas ou la droite |
| `↑` / `←` / `↓` / `→` | Déplacer le serpent avec les flèches directionnelles |
| `Entrée` | Démarrer depuis le menu ou relancer une partie après un Game Over |
| `Échap` | Depuis le menu, modifier le pseudo ; pendant la saisie du pseudo ou depuis l’écran de Game Over, quitter le jeu |
| `Retour arrière` | Effacer le dernier caractère du pseudo pendant sa saisie |
| Clic gauche | Cliquer sur le bouton **START** du menu |

Le serpent ne peut pas faire demi-tour directement sur lui-même.

## 🧰 Installation avec Visual Studio Code

Ces instructions sont prévues pour **Windows**, avec Python et Visual Studio Code installés.

### 1. Récupérer le projet

Clone le dépôt GitHub, ou télécharge-le puis ouvre son dossier dans Visual Studio Code.

Pour cloner le dépôt depuis le terminal de VS Code :

```powershell
git clone <URL_DU_DEPOT>
cd <NOM_DU_DEPOT>
```

Remplace `<URL_DU_DEPOT>` et `<NOM_DU_DEPOT>` par les informations de ton dépôt.

### 2. Créer l'environnement virtuel `.venv`

Dans VS Code, ouvre **Terminal → Nouveau terminal**, puis exécute :

```powershell
py -3.12 -m venv .venv
```

Cette commande crée un environnement Python isolé dans le dossier `.venv` du projet. Python **3.10 ou plus récent** est nécessaire, car le code utilise notamment `match/case`. Si la commande `py -3.12` ne fonctionne pas, utilise une autre version compatible de Python installée sur ton ordinateur, par exemple `py -3.13`.

### 3. Activer l'environnement virtuel

Dans le terminal PowerShell de VS Code :

```powershell
.\.venv\Scripts\Activate.ps1
```

Si l'activation est bloquée par la politique d'exécution PowerShell, tu peux installer les dépendances et lancer le jeu avec le chemin direct vers Python de `.venv` indiqué plus bas, sans activer l'environnement.

### 4. Installer les bibliothèques nécessaires

Une fois `.venv` activé, exécute :

```powershell
python -m pip install --upgrade pip
python -m pip install pygame openpyxl
```

Le projet utilise :

- **Pygame** pour la fenêtre, les événements clavier et l'affichage du jeu ;
- **openpyxl** pour lire et enregistrer les records dans le fichier Excel.

### 5. Sélectionner l'interpréteur Python dans VS Code

1. Ouvre la palette de commandes avec `Ctrl` + `Maj` + `P`.
2. Recherche **Python: Select Interpreter**.
3. Sélectionne l'interpréteur situé dans `.venv`, généralement `.venv\Scripts\python.exe`.

### 6. Lancer le jeu

Dans le terminal, lance le fichier Python qui contient le jeu. Par exemple, si le fichier s'appelle `main.py` :

```powershell
python main.py
```

Adapte `main.py` au nom réel du fichier dans le dépôt.

Si tu n'as pas activé l'environnement virtuel, utilise directement son interpréteur :

```powershell
.\.venv\Scripts\python.exe main.py
```

Là encore, remplace `main.py` par le nom du fichier concerné.

## 📁 Fichiers nécessaires

Le dossier `assets` doit rester à côté du fichier Python. Il contient notamment :

```text
assets/
├── font.otf       # Police utilisée dans le jeu
└── records.xlsx   # Records des joueurs
```

Le jeu utilise des chemins relatifs à son propre fichier pour retrouver ces ressources. Conserve donc cette organisation lorsque tu lances le programme.

Si `records.xlsx` n'existe pas au démarrage, le jeu peut créer le fichier lors du chargement du record d'un joueur. Garde toutefois le dossier `assets` présent, car il contient aussi la police du jeu.

## 🕹️ Objectif

Obtiens le meilleur score possible, récupère les cœurs pour conserver tes points de vie et essaie de battre ton record personnel !
