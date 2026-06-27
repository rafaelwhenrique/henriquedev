# 🎯 Projects Section Setup Guide

Your portfolio now includes a beautiful, fully-featured **Projects** section! Here's how to use it.

## Quick Start: Adding Your First Project

### Step 1: Open `index.php`

Navigate to line ~78 where you'll find the `$projects` array:

```php
$projects = [
    // Your projects go here
];
```

### Step 2: Add a Project

Remove the comments from an example project and modify it:

```php
$projects = [
    [
        'title' => 'E-Commerce Platform',
        'description' => 'Plataforma de e-commerce completa com sistema de pagamento.',
        'description_en' => 'Complete e-commerce platform with payment system integration.',
        'technologies' => ['PHP', 'JavaScript', 'MySQL', 'Stripe'],
        'github' => 'https://github.com/rafaelwhenrique/ecommerce-platform',
        'demo' => 'https://ecommerce-demo.example.com',
        'emoji' => '🛒'
    ]
];
```

### Step 3: Save & Refresh

Save the file, refresh your portfolio, and your project will appear! 🎉

---

## Project Object: All Available Properties

```php
[
    'title' => 'Project Name',                    // ✓ Required
    'description' => 'Portuguese description',    // ✓ Required
    'description_en' => 'English description',    // Optional (defaults to Portuguese)
    'technologies' => ['PHP', 'React', 'MySQL'],  // Optional but recommended
    'github' => 'https://github.com/...',         // Optional
    'demo' => 'https://live-demo.com',            // Optional
    'url' => 'https://any-url.com',               // Optional (fallback for github/demo)
    'image' => 'path/to/project-image.jpg',       // Optional (emoji used if missing)
    'emoji' => '🚀'                               // Optional fallback icon
]
```

---

## Property Details

| Property | Type | Required | Description | Example |
|----------|------|----------|-------------|---------|
| `title` | String | ✅ | Project name | `"Landing Page for Startup"` |
| `description` | String | ✅ | Portuguese description | `"Página de destino profissional..."` |
| `description_en` | String | ❌ | English description (if omitted, uses `description`) | `"Professional landing page..."` |
| `technologies` | Array | ❌ | Tech stack used | `['React', 'Tailwind', 'Node.js']` |
| `github` | String | ❌ | GitHub repo URL | `"https://github.com/user/repo"` |
| `demo` | String | ❌ | Live demo URL | `"https://project-demo.vercel.app"` |
| `url` | String | ❌ | Generic URL (shown only if `github` & `demo` are missing) | `"https://example.com"` |
| `image` | String | ❌ | Path to project screenshot | `"images/projects/ecommerce.jpg"` |
| `emoji` | String | ❌ | Fallback emoji (shown if no image) | `"🛒"` |

---

## Link Display Logic

The section automatically displays the right buttons based on what you provide:

```
✓ github + demo      → Shows both "GitHub" and "Demo" buttons
✓ github only        → Shows "GitHub" button
✓ demo only          → Shows "Demo" button  
✓ url only           → Shows "Learn More" button
✗ none               → No footer buttons
```

---

## Complete Examples

### Example 1: Simple Project (Minimal)

```php
[
    'title' => 'CLI Calculator',
    'description' => 'Calculadora CLI em Python com operações básicas.',
    'description_en' => 'Python CLI calculator with basic operations.',
    'technologies' => ['Python', 'CLI'],
    'github' => 'https://github.com/rafaelwhenrique/cli-calculator',
    'emoji' => '🧮'
]
```

### Example 2: Full-Featured Project

```php
[
    'title' => 'E-Commerce Management System',
    'description' => 'Sistema completo de e-commerce com painelministrativo, carrinho de compras, integração com Stripe e relatórios avançados.',
    'description_en' => 'Complete e-commerce system with admin dashboard, shopping cart, Stripe integration, and advanced reporting.',
    'technologies' => ['PHP', 'JavaScript', 'MySQL', 'Stripe API', 'Bootstrap'],
    'github' => 'https://github.com/rafaelwhenrique/ecommerce-system',
    'demo' => 'https://ecommerce-demo.example.com',
    'image' => 'images/projects/ecommerce-hero.jpg',
    'emoji' => '🛒'
]
```

### Example 3: Project with Just Live Demo

```php
[
    'title' => 'Portfolio Website',
    'description' => 'Meu portfólio pessoal com seção de projetos.',
    'description_en' => 'My personal portfolio with projects showcase.',
    'technologies' => ['PHP', 'JavaScript', 'HTML/CSS'],
    'demo' => 'https://rafaelhenrique.com',
    'emoji' => '💼'
]
```

---

## Multiple Projects Example

Here's how your `$projects` array looks with multiple projects:

```php
$projects = [
    [
        'title' => 'Project One',
        'description' => 'Descrição do projeto um...',
        'description_en' => 'Project one description...',
        'technologies' => ['PHP', 'MySQL'],
        'github' => 'https://github.com/...',
        'emoji' => '🎯'
    ],
    [
        'title' => 'Project Two',
        'description' => 'Descrição do projeto dois...',
        'description_en' => 'Project two description...',
        'technologies' => ['React', 'Node.js'],
        'demo' => 'https://project-two.com',
        'emoji' => '⚡'
    ],
    [
        'title' => 'Project Three',
        'description' => 'Descrição do projeto três...',
        'description_en' => 'Project three description...',
        'technologies' => ['Java', 'Spring Boot'],
        'github' => 'https://github.com/...',
        'demo' => 'https://project-three.com',
        'emoji' => '🚀'
    ]
];
```

---

## Design Features

### Visual Highlights

✨ **Automatic Features:**
- ✅ Responsive grid layout (auto-adjusts columns on mobile)
- ✅ Smooth hover animations (lift up, shadow, border glow)
- ✅ Tech stack badges with orange accent color
- ✅ Gradient overlays on hover
- ✅ Language-aware (PT/EN switches automatically)
- ✅ Supports both light and dark modes
- ✅ Fade-in animation for all cards
- ✅ Lazy loading for images (better performance)
- ✅ Orange accent border that glows on hover

### Empty State

When `$projects` is empty, a beautiful placeholder appears:
- 📋 Icon
- Motivational message in Portuguese or English
- "Stay in Touch" button linking to contact form

---

## Tips & Best Practices

### 1. **Use Consistent Emoji Icons**
Choose emojis that represent your project type:
- `🛒` E-commerce
- `📱` Mobile app
- `💻` Web app
- `🎮` Game
- `📊` Dashboard
- `📦` Library/Tool
- `⚙️` Backend/API
- `🚀` Startup/Product
- `🎨` Design/Creative

### 2. **Keep Descriptions Concise**
- 1-2 sentences max
- Highlight the key value prop
- Good: "Full e-commerce platform with Stripe integration"
- Bad: "A platform for buying and selling things online that integrates with payment..."

### 3. **Always Include Technologies**
Recruiters scan this first. Include:
- 2-5 main technologies
- Important frameworks/libraries
- API integrations (if significant)

### 4. **Prefer GitHub + Demo Over Just URL**
- `github` = shows your coding skills
- `demo` = shows it's production-ready
- Both = maximum impact

### 5. **Use Quality Project Images**
- If using `image`, make sure it's:
  - 16:9 ratio (landscape)
  - At least 600px wide
  - Shows the actual UI/interface
  - Compressed/optimized for web

### 6. **Add Projects Progressively**
Start with 1-2 of your best projects, add more as you build.

---

## Styling Customization

All colors automatically match your portfolio's theme:
- **Orange accent:** `#ff6b1a` (matches throughout)
- **Borders:** Subtle orange at 15% opacity (hover state: 100%)
- **Spacing:** Consistent with rest of portfolio
- **Typography:** Same Inter font family
- **Animations:** 0.3s transitions, cubic-bezier easing

To customize, edit the CSS in `index.php`:
- Look for `.project-card`
- Look for `.tech-badge`
- Look for `.projects-empty`

---

## Troubleshooting

### My project isn't showing?
1. Check syntax (commas between items)
2. Verify you saved the file
3. Hard refresh browser (Ctrl+F5 or Cmd+Shift+R)
4. Check for typos in property names

### Links aren't working?
- Ensure URLs start with `https://`
- Double-check for typos in URLs
- Make sure repo/demo actually exists

### Styling looks off?
- Your CSS changes in the portfolio affect all elements
- Don't modify `.project-card` unless intentional
- Check dark/light mode toggle (might be set to opposite theme)

---

## Next Steps

1. ✅ **Uncomment an example project** and customize it
2. ✅ **Add a real project** you're proud of
3. ✅ **Take a screenshot** for the `image` property
4. ✅ **Share your portfolio** with recruiters!

---

## Questions?

The projects section is designed to be intuitive, but if you need help:
- Check property syntax against examples above
- Ensure your URLs are correct
- Test in both light and dark modes
- Verify both Portuguese and English text displays

Happy showcasing! 🚀
