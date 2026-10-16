# 🐍 Snake.py

A **Snake game built with Python and Pygame**, created during my second-year high-school internship at the University of Lille's science faculty, in the CRIStAL laboratory.

Eat apples to make the snake grow and increase your score while avoiding collisions. The game features a health system, collectible hearts, and a local high-score system.

## 🎬 Gameplay Preview

[▶ Watch the gameplay preview](preview.mov)

Place `preview.mov` in the repository root, next to this `README.md`, for the link above to work.

## 🎮 Features

- **Score:** each apple eaten makes the snake grow and increases your score.
- **Health points (HP):** hitting the edge of the play area or the snake's own body costs one health point.
- **Collectible hearts:** a heart can appear every 10 points. Collecting it restores one health point, up to a maximum of **3 HP**.
- **High scores:** the game displays your personal best and the highest score recorded locally.
- **Player name:** enter a username to keep track of your personal best.
- **Increasing speed:** the snake gets faster as it grows.
- **Pixel-art graphics:** the snake, apple, and hearts are drawn in a retro pixel-art style.

Scores are stored locally in `assets/records.xlsx`. They are **not synced online** between different users or computers.

## ⌨️ Controls

| Key | Action |
| --- | --- |
| `Z` / `Q` / `S` / `D` | Move up, left, down, or right |
| `↑` / `←` / `↓` / `→` | Move using the arrow keys |
| `Enter` | Start the game from the menu or restart after Game Over |
| `Esc` | In the menu, change the username; while entering a username or on the Game Over screen, quit the game |
| `Backspace` | Delete the last character while entering your username |
| Left mouse click | Click the **START** button in the menu |

The snake cannot immediately reverse direction and move directly back into itself.

## 🧰 Installation with Visual Studio Code

These instructions are for **Windows**, with Python and Visual Studio Code installed.

### 1. Get the project

Clone the GitHub repository, or download it and open its folder in Visual Studio Code.

To clone it from the VS Code terminal:

```powershell
git clone <REPOSITORY_URL>
cd <REPOSITORY_FOLDER>
```

Replace `<REPOSITORY_URL>` and `<REPOSITORY_FOLDER>` with your repository's URL and folder name.

### 2. Create the `.venv` virtual environment

In VS Code, open **Terminal → New Terminal**, then run:

```powershell
py -3.12 -m venv .venv
```

This creates an isolated Python environment in the project's `.venv` folder. The code requires **Python 3.10 or newer**, because it uses features such as `match/case`. If `py -3.12` is not available, use another compatible Python version installed on your computer, such as `py -3.13`.

### 3. Activate the virtual environment

In the VS Code PowerShell terminal, run:

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation because of its execution policy, you can install the dependencies and run the game using the direct path to `.venv`'s Python interpreter, as shown below, without activating the environment.

### 4. Install the required libraries

With `.venv` activated, run:

```powershell
python -m pip install --upgrade pip
python -m pip install pygame openpyxl
```

The project uses:

- **Pygame** for the game window, keyboard input, and graphics;
- **openpyxl** to read and save high scores in the Excel file.

### 5. Select the Python interpreter in VS Code

1. Open the Command Palette with `Ctrl` + `Shift` + `P`.
2. Search for **Python: Select Interpreter**.
3. Select the interpreter inside `.venv`, usually `.venv\Scripts\python.exe`.

### 6. Run the game

In the terminal, run the Python file containing the game. For example, if the file is named `main.py`:

```powershell
python main.py
```

Replace `main.py` with the actual filename in your repository.

If you have not activated the virtual environment, run it using its Python interpreter directly:

```powershell
.\.venv\Scripts\python.exe main.py
```

Again, replace `main.py` with the name of your Python file.

## 📁 Required files

Keep the `assets` folder alongside the Python file. It should contain at least:

```text
assets/
├── font.otf       # Font used by the game
└── records.xlsx   # Player high scores
```

The game uses paths relative to its Python file to locate these resources, so keep this folder structure intact when running the program.

If `records.xlsx` does not exist, the game can create it when loading a player's record. However, keep the `assets` folder in place because it also contains the game's font.

## 🕹️ Objective

Get the highest score you can, collect hearts to maintain your health, and try to beat your personal best!
