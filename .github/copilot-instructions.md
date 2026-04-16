# Unicorn Princess Party Drinking Game

## Development Checklist (Mandatory)
1. **Lint**: `dotnet build` — fix all warnings/errors
2. **Build**: `dotnet build SocOps/SocOps.csproj` — must succeed
3. **Test**: `dotnet test` — all tests must pass (when test project exists)

## Project Overview
- **App**: Unicorn Princess Party Drinking Game — a magical party game with sip/drink/chug prompts
- **Stack**: C# / .NET 10 / Blazor WebAssembly
- **Port**: 5166 (dev server)

## Architecture
- `SocOps/` — Main Blazor WASM app
  - `Pages/` — Razor pages (`Home.razor` is the main entry)
  - `Components/` — UI components (`StartScreen`, `GameScreen`, `BingoBoard`, `BingoSquare`, `BingoModal`, `ScavengerHunt`, `CardDeck`)
  - `Models/` — Data models (`GameState`, `BingoSquareData`, `BingoLine`)
  - `Services/` — Game logic (`BingoGameService` for state, `BingoLogicService` for pure logic)
  - `Data/` — Drinking game prompts (`Questions.cs`)
  - `wwwroot/css/app.css` — Theme CSS with princess variables and utility classes

## Game Modes
- **Bingo Grid** (🥂) — 5×5 bingo board, tap squares when someone drinks, get 5 in a row
- **Drink Checklist** (🔮) — Scrollable checklist of all drinking prompts
- **Card Deck** (🃏) — Flip cards one at a time for surprise drinking prompts

## Key Patterns
- **State Management**: `BingoGameService` (scoped, event-driven via `OnStateChanged`)
- **Pure Logic**: `BingoLogicService` has static methods, immutable updates
- **Storage**: LocalStorage via `IJSRuntime` for game persistence
- **CSS**: Custom utility classes in `app.css` (no Tailwind dependency)

## Conventions
- Razor components use `@code` blocks (not code-behind)
- CSS classes compose from utility classes in `app.css`
- New utilities should follow existing naming patterns
- Game state flows: `Start → Playing → Bingo`, `Start → ScavengerHunt`, `Start → CardDeck`

## Design Guide — Unicorn Princess Theme
- **Fonts**: `Pacifico` (cursive) for titles/headings, `Quicksand` for body text
- **Colors**: Soft blush/pink backgrounds (`#fdf2f8`, `#fae8ff`, `#ffffff`) with girly accents
  - Pink (`#ec4899`) — primary accent, marked squares, interactive elements
  - Purple (`#a78bfa`) — winning state, bingo alerts, emphasis
  - Gold (`#fbbf24`) — free space highlight
  - Magenta (`#f472b6`) — secondary buttons, card deck mode
  - Lavender (`#c4b5fd`) — gradients, progress bars
- **Effects**: Soft pink/purple shadows, sparkle animations, extra-rounded corners (1.5–2rem), shimmer highlights
- **CSS Classes**: Use `cyber-*` prefixed classes (`cyber-title`, `cyber-btn`, `cyber-card`, `cyber-square`, etc.) — names kept for backward compat
- **Emojis**: 🦄 🥂 👑 ✨ 🍷 🔮 💖 ♥ — used throughout the UI
- **Aesthetic**: Magical princess/unicorn drinking game theme. Rounded shapes, heart/sparkle/crown emojis, pink-to-purple gradients. All new components should use CSS variables from `:root`

## Question/Prompt Style
- Drinking prompts use "Sip if…", "Drink if…", "Chug if…", "Everyone drinks…" format
- Each prompt includes a relevant emoji
- Keep prompts fun, inclusive, and low-stakes
- Works equally well with non-alcoholic drinks
