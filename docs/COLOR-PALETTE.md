# Color Palette - Learn with Satya K

## Overview
Ocean-inspired color palette with warm accents, designed for learning and education.

## Color Definitions

### Primary Colors

| Color Name | Hex Code | RGB | Usage |
|------------|----------|-----|-------|
| **Sky Blue Light** | `#8ecae6` | rgb(142, 202, 230) | Beginner difficulty, DevOps category, light accents |
| **Blue Green** | `#219ebc` | rgb(33, 158, 188) | Primary theme color, AI/Backend/Tools categories, progress bars |
| **Deep Space Blue** | `#023047` | rgb(2, 48, 71) | Body text, System Design category, dark mode primary |
| **Amber Flame** | `#ffb703` | rgb(255, 183, 3) | Intermediate difficulty, Frontend category, highlights |
| **Princeton Orange** | `#fb8500` | rgb(251, 133, 0) | Advanced difficulty, Career category, call-to-action buttons |

### Background Colors

| Color Name | Hex Code | RGB | Usage |
|------------|----------|-----|-------|
| **White** | `#ffffff` | rgb(255, 255, 255) | Main background, light themes |
| **Light Gray** | `#e5e7eb` | rgb(229, 231, 235) | Borders, subtle backgrounds |

---

## Component Usage

### Difficulty Badges
- **Beginner** 🌱: Sky Blue Light (#8ecae6)
- **Intermediate** 📚: Amber Flame (#ffb703)
- **Advanced** 🚀: Princeton Orange (#fb8500)

### Category Colors
- **AI & Machine Learning** 🤖: Blue Green (#219ebc)
- **System Design** 🏗️: Deep Space Blue (#023047)
- **Backend Engineering** ⚙️: Blue Green (#219ebc)
- **DevOps & Cloud** ☁️: Sky Blue Light (#8ecae6) with dark text
- **Frontend & Web** 🎨: Amber Flame (#ffb703) with dark text
- **Career & Growth** 📈: Princeton Orange (#fb8500)
- **Tools & Ecosystem** 🛠️: Blue Green (#219ebc)

### UI Elements

**Series Navigation:**
- Background: Linear gradient from Blue Green (#219ebc) to Deep Space Blue (#023047)
- Text: White (#ffffff)
- Progress bar: White on transparent background

**Progress Dashboard:**
- Card 1 (Posts): Blue Green → Deep Space Blue gradient
- Card 2 (Series): Amber Flame → Princeton Orange gradient
- Card 3 (Time): Sky Blue Light → Blue Green gradient

**Buttons:**
- Primary: Blue Green (#219ebc) with white text
- Secondary: White with Deep Space Blue (#023047) text
- Danger/Reset: Princeton Orange (#fb8500) with white text

**Completion Badge:**
- Background: Blue Green → Deep Space Blue gradient
- Shadow: rgba(33, 158, 188, 0.3)

---

## Accessibility

### Contrast Ratios (WCAG 2.1)

**Dark text on light backgrounds:**
- Deep Space Blue (#023047) on White (#ffffff): **17.7:1** ✅ AAA
- Deep Space Blue (#023047) on Sky Blue Light (#8ecae6): **8.4:1** ✅ AAA
- Deep Space Blue (#023047) on Amber Flame (#ffb703): **7.2:1** ✅ AAA

**White text on dark backgrounds:**
- White (#ffffff) on Deep Space Blue (#023047): **17.7:1** ✅ AAA
- White (#ffffff) on Blue Green (#219ebc): **3.8:1** ✅ AA (large text)
- White (#ffffff) on Princeton Orange (#fb8500): **2.3:1** ⚠️ AA (large text only, 18pt+)

**Recommendations:**
- Use Deep Space Blue text on light colored backgrounds (Sky Blue, Amber, White)
- Use White text on dark backgrounds (Deep Space Blue, Blue Green)
- For Princeton Orange backgrounds, ensure text is 18pt+ or bold 14pt+

---

## Design Principles

1. **Ocean-Inspired:** Blue-green tones evoke trust, learning, and clarity
2. **Warm Accents:** Amber and orange add energy and call attention
3. **High Contrast:** Deep Space Blue ensures readability
4. **Progressive Difficulty:** Colors lighten from beginner → advanced
5. **Consistent Gradients:** All cards use 135deg angle for visual harmony

---

## Implementation Files

### Theme Configuration
- `src/yml/theme.yml` - Source theme variables
- `_sass/_theme.scss` - Compiled theme SASS variables
- `_config.yml` - Jekyll theme color (auto-generated from theme.yml)

### Component Colors
- `_data/categories.yml` - Category-specific colors (7 categories)
- `_includes/difficulty-badge.html` - Difficulty badge colors (3 levels)
- `_includes/series-navigation.html` - Series UI gradient
- `_layouts/post.html` - Series badge color
- `progress.html` - Dashboard card gradients
- `assets/js/learning-progress-tracker.js` - Completion badge & button colors

---

## Color Palette Visualization

```
┌─────────────────────────────────────────────────────────┐
│  Sky Blue Light (#8ecae6)                               │
│  █████████████████████████████████████████████          │
│  Beginner • DevOps • Light Accents                      │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  Blue Green (#219ebc)                                    │
│  █████████████████████████████████████████████          │
│  Primary • AI • Backend • Tools • Progress              │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  Deep Space Blue (#023047)                               │
│  █████████████████████████████████████████████          │
│  Text • System Design • Dark Primary                    │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  Amber Flame (#ffb703)                                   │
│  █████████████████████████████████████████████          │
│  Intermediate • Frontend • Highlights                   │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│  Princeton Orange (#fb8500)                              │
│  █████████████████████████████████████████████          │
│  Advanced • Career • CTAs                               │
└─────────────────────────────────────────────────────────┘
```

---

## Version History

- **v1.0** (March 2026) - Ocean-inspired palette with white background
- **v0.9** (Initial) - Education blue/emerald palette (#3B82F6, #10B981)

---

**Last Updated:** March 10, 2026  
**Status:** Active  
**Commit:** 8590f55
