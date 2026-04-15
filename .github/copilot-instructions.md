# Soc Ops - Social Bingo

## Development Checklist (Mandatory)
1. **Lint**: `dotnet build` — fix all warnings/errors
2. **Build**: `dotnet build SocOps/SocOps.csproj` — must succeed
3. **Test**: `dotnet test` — all tests must pass (when test project exists)

## Project Overview
- **App**: Social Bingo game for in-person mixers and icebreakers
- **Stack**: C# / .NET 10 / Blazor WebAssembly
- **Port**: 5166 (dev server)
- **Solution**: `vscode-agent-lab-soc-ops-csharp.sln`

## Architecture
- `SocOps/` — Main Blazor WASM app
  - `Pages/` — Razor pages (`Home.razor` is the main entry)
  - `Components/` — UI components (`StartScreen`, `GameScreen`, `BingoBoard`, `BingoSquare`, `BingoModal`)
  - `Models/` — Data models (`GameState`, `BingoSquareData`, `BingoLine`)
  - `Services/` — Game logic (`BingoGameService` for state, `BingoLogicService` for pure logic)
  - `Data/` — Question data (`Questions.cs`)
  - `wwwroot/css/app.css` — Tailwind-like utility CSS classes

## Key Patterns
- **State Management**: `BingoGameService` (scoped, event-driven via `OnStateChanged`)
- **Pure Logic**: `BingoLogicService` has static methods, immutable updates
- **Storage**: LocalStorage via `IJSRuntime` for game persistence
- **CSS**: Custom utility classes in `app.css` (no Tailwind dependency)

## Conventions
- Razor components use `@code` blocks (not code-behind)
- CSS classes compose from utility classes in `app.css`
- New utilities should follow existing naming patterns
- Game state flows: `Start → Playing → Bingo`

## Design Guide — Cyberpunk Neon Theme
- **Fonts**: `Orbitron` for titles/headings, `Rajdhani` for body text
- **Colors**: Dark backgrounds (`#0a0a0f`, `#12121a`, `#1a1a2e`) with neon accents
  - Cyan (`#00f0ff`) — primary accent, marked squares, interactive elements
  - Magenta (`#ff00e5`) — winning state, bingo alerts, emphasis
  - Yellow (`#ffe600`) — free space highlight
  - Green (`#39ff14`) — success/completion indicators
- **Effects**: Neon glow (`text-shadow`, `box-shadow`) on interactive elements; scanline overlay on backgrounds; subtle glitch-in animations
- **CSS Classes**: Use `cyber-*` prefixed classes (`cyber-title`, `cyber-btn`, `cyber-card`, `cyber-square`, etc.)
- **Aesthetic**: Dark sci-fi terminal feel. No purple gradients, no generic pastel palettes. All new components should use CSS variables from `:root`
