
# 🐍 Snake.py

A classic Snake game built with **Python**, **Pygame**, and pixel-art graphics. Eat apples to grow longer, increase your score, collect hearts to restore health, and try to beat the local high scores.

## 🎬 Gameplay Preview

https://github.com/user-attachments/assets/29cb55c2-c8ce-4968-ae3f-4dcbae7ad498

[▶ Watch the gameplay preview](preview.mov)

## 🎮 Features

- **Score:** each apple increases your score and makes the snake longer.
- **Health system:** lose a health point when you hit the edge of the play area or collide with your own body.
- **Collectible hearts:** a heart appears every 10 points. Collect it to restore one health point, up to a maximum of **3 HP**.
- **Personal and global records:** compare your current score with your personal best and the highest score stored locally.
- **Player profiles:** enter a username to save a personal record.
- **Increasing speed:** the snake speeds up as it grows.
- **Pixel-art graphics:** the snake, apples, and hearts use a retro pixel-art style.

High scores are saved locally in `assets/records.xlsx` and are not synced online between computers.

## ⌨️ Controls

| Key | Action |
| --- | --- |
| `Z` / `Q` / `S` / `D` | Move up, left, down, or right |
| `↑` / `←` / `↓` / `→` | Move with the arrow keys |
| `Enter` | Start from the menu or restart after Game Over |
| `Esc` | Change the username from the main menu; quit from the username screen or Game Over screen |
| `Backspace` | Delete the last character when entering a username |
| Left mouse button | Click the **START** button |

The snake cannot immediately reverse direction.

## 🧰 Installation and Setup (Windows + Visual Studio Code)

### Requirements

- Windows
- [Python 3.10 or newer](https://www.python.org/downloads/)
- [Visual Studio Code](https://code.visualstudio.com/)
- The **Python** extension for VS Code

### 1. Download the project

On the GitHub repository page, select **Code → Download ZIP**. Extract the ZIP file, then open the extracted project folder in Visual Studio Code.

### 2. Create a virtual environment

Open **Terminal → New Terminal** in VS Code and run:

```powershell
py -m venv .venv
```

This creates a virtual environment named `.venv` inside the project folder.

### 3. Activate the virtual environment

In the VS Code PowerShell terminal, run:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 4. Install the dependencies

With the virtual environment activated, run:

```powershell
python -m pip install --upgrade pip
python -m pip install pygame openpyxl
```

The game uses **Pygame** for graphics and keyboard input, and **openpyxl** to manage the Excel high-score file.

### 5. Select the Python interpreter in VS Code

1. Press `Ctrl` + `Shift` + `P` to open the Command Palette.
2. Select **Python: Select Interpreter**.
3. Choose the Python interpreter located in `.venv` (usually `.venv\Scripts\python.exe`).

### 6. Launch the game

In the VS Code Explorer, open the Python file that starts the game and select **Run Python File**. The game opens in full-screen mode.

## 📁 Project Structure

```text
project-root/
├── assets/
│   ├── font.otf
│   └── records.xlsx
├── preview.mov
└── *.py
```

Keep the `assets` folder alongside the Python game file. The game uses `font.otf` for its text and stores local high scores in `records.xlsx`. If the records file is missing, the game can create it automatically.

## 🕹️ Objective

Get the highest score possible, collect hearts to maintain your health, and beat your personal best!
