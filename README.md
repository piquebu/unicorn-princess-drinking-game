# 🦄🥂 Unicorn Princess Party Drinking Game

A magical, sparkly party drinking game built with Blazor WebAssembly. Gather your friends, pour your drinks, and let the princess-themed prompts decide who sips, drinks, or chugs!

![.NET 10](https://img.shields.io/badge/.NET-10.0-pink?style=flat-square&logo=dotnet)
![Blazor WASM](https://img.shields.io/badge/Blazor-WebAssembly-purple?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-lavender?style=flat-square)

---

## ✨ Game Modes

| Mode | Description |
|------|-------------|
| 🥂 **Bingo Grid** | 5×5 bingo board — tap squares as people drink. Get 5 in a row and everyone cheers! |
| 🔮 **Drink Checklist** | Checklist of drinking prompts — work through them all for a royal toast |
| 🃏 **Draw a Card** | Flip cards one at a time for surprise drinking prompts |

## 🍷 How It Works

1. Pick a game mode
2. Read the prompt out loud
3. Sip, drink, or chug as instructed
4. Tap to mark it done
5. Celebrate when you complete a line / the list / the deck!

> **Please drink responsibly.** This game works just as well with non-alcoholic drinks! 🧃

---

## 🎨 Theme

Unicorn Princess aesthetic with:
- **Fonts**: Pacifico (cursive headings) + Quicksand (body)
- **Colors**: Pink `#ec4899`, Purple `#a78bfa`, Gold `#fbbf24`, Magenta `#f472b6`, Lavender `#c4b5fd`
- **Vibes**: Sparkle animations, rounded corners, heart checkmarks, crown & unicorn emojis

---

## 🚀 Getting Started

### Prerequisites

- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0)

### Run

```bash
cd SocOps
dotnet run
```

Open http://localhost:5166 in your browser.

### Build

```bash
cd SocOps
dotnet build
```

---

## 🏗️ Tech Stack

- **C# / .NET 10** — Blazor WebAssembly (client-side, no server needed)
- **CSS** — Custom utility classes with princess theme variables
- **Fonts** — Google Fonts (Pacifico + Quicksand)
- **No external JS dependencies**

## 📁 Project Structure

```
SocOps/
├── Components/     # Razor components (StartScreen, GameScreen, BingoBoard, etc.)
├── Data/           # Drinking game prompts (Questions.cs)
├── Models/         # Game state models
├── Services/       # Game logic services
├── Pages/          # Main entry page (Home.razor)
└── wwwroot/        # Static assets, CSS, index.html
```

---

## 🦄 Contributing

Got ideas for new drinking prompts? Want to add a new game mode? PRs welcome!

## 📜 License

MIT
