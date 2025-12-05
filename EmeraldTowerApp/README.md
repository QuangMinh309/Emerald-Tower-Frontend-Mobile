# EmeraldTowerApp

## Features

- Expo Router (App Router) with file-based routing
- Full Dark/Light mode with automatic system preference detection
- Beautiful custom UI components:

  - `ParallaxScrollView` – Stunning parallax header effect
  - `ThemedText` & `ThemedView` – Auto theme-aware components
  - `HelloWave` – Cute hand-wave greeting animation
  - `HapticTab` – Native haptic feedback on tab press (iOS/Android)

- Optimized for both mobile and web (`use-color-scheme-web.ts`)
- Clean, scalable folder structure
- Full TypeScript support

---

## Project Structure (Important Files)

```
app/
├── (tabs)/
│   ├── index.tsx          Home screen (main screen)
│   ├── explore.tsx        Second tab (list/feed screen)
│   ├── profile.tsx        Profile screen
│   └── _layout.tsx        Tab navigation configuration
components/ui/
├── parallax-scroll-view.tsx
├── themed-text.tsx
├── themed-view.tsx
├── hello-wave.tsx
├── haptic-tab.tsx
└── external-link.tsx
constants/
└── theme.ts               Global color palette (edit here to change app theme)
hooks/
├── use-color-scheme.ts    Get current theme (light/dark)
└── use-theme-color.ts     Update status bar color dynamically
```

---

## Quick Start

### 1. Install dependencies

```bash
npm install
```

### 2. Start the development server

```bash
cd EmeraldTowerApp
npm start
```

- Open **Expo Go** app on your phone → scan QR code → app runs instantly!

### 3. Start coding

- Most edits will happen in `app/(tabs)/` and `components/ui/`.

---

## File Purpose

| File                     | Purpose                            |
| ------------------------ | ---------------------------------- |
| `app/(tabs)/index.tsx`   | Main Home screen                   |
| `app/(tabs)/explore.tsx` | Second tab (lists, feeds)          |
| `app/(tabs)/profile.tsx` | User profile screen                |
| `constants/theme.ts`     | Change entire app color theme here |
| `components/ui/*`        | Reusable beautiful components      |

---

## Try Your First Edit (Live Reload!)

Open `app/(tabs)/index.tsx` and change this line:

```tsx
<ThemedText type="title">Welcome!</ThemedText>
```

→ Change "Welcome!" to your name → save → watch it update instantly on your phone!

---

## How to Add a New Tab (Example: Favorites)

1. Create file: `app/(tabs)/favorites.tsx`

```tsx
import { ThemedText, ThemedView } from "@/components/ui";

export default function FavoritesScreen() {
  return (
    <ThemedView style={{ flex: 1, padding: 20 }}>
      <ThemedText type="title">Favorites</ThemedText>
      <ThemedText>This is your favorites screen</ThemedText>
    </ThemedView>
  );
}
```

2. Add to tab navigator → Open `app/(tabs)/_layout.tsx`

```tsx
<Tabs.Screen
  name="favorites"
  options={{
    title: "Favorites",
    tabBarIcon: ({ color }) => <TabBarIcon name="heart" color={color} />,
  }}
/>
```

✅ Done! New tab with heart icon appears.

---

## Customize Theme (Change App Colors)

Edit `constants/theme.ts`:

```ts
const tint = "#244B35";

export const Colors = {
  light: {
    text: "#11181C",
    background: "#F8FFFD",
    tint,
    icon: "#687076",
    tabIconDefault: "#687076",
    tabIconSelected: tint,
  },
  dark: {
    text: "#ECEDEE",
    background: "#0D1F1C",
    tint,
    icon: "#9BA1A6",
    tabIconDefault: "#9BA1A6",
    tabIconSelected: tint,
  },
};
```

---

## Useful Scripts

```bash
# Reset everything (clear cache, reinstall)
node scripts/reset-project.js

# Run
npm start
```

---

## Tech Stack

- Expo SDK 51+
- React Native
- TypeScript
- Expo Router (App Directory)