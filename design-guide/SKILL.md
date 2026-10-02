---
name: design-guide
description: UI/UX design rules for agents building interfaces — hierarchy before decoration, restraint with cards, borders, backgrounds, icons, badges, radii and shadows, reuse of the project's existing components, tokens and icon library, and no invented features. Use when designing or reviewing a screen, choosing layout and components, or when an interface looks like a generic AI dashboard.
---

# Design Guide

## Core Goal

Design should solve **information, hierarchy, layout, and interaction problems** before visual decoration.

Do not add visual elements simply because a page feels empty, unfinished, or insufficiently "modern".

Prefer:

1. Layout
2. Spacing
3. Alignment
4. Typography
5. Information hierarchy
6. Grouping
7. Color and contrast
8. Borders and backgrounds
9. Shadows, icons, and decoration

**Do not use decoration as a substitute for design.**

---

# 1. Understand the Task Before Designing

Before designing a UI, determine:

* What is the user trying to accomplish?
* What information do they need?
* What should they notice first?
* What should they do next?
* Which information needs to be visible at the same time?
* Which information can be hidden or deferred?
* Which elements actually belong together?
* Which elements do not need visual emphasis?

Do not turn a feature list directly into a collection of UI components.

---

# 2. Establish Visual Hierarchy First

Build hierarchy primarily through:

* Position
* Spacing
* Alignment
* Typography
* Font size
* Font weight
* Content density
* Contrast

Only use additional visual treatments when these are not sufficient:

* Backgrounds
* Borders
* Shadows
* Icons
* Decorative elements

For example, do not automatically create a card just because two sections need to be visually separated.

Sometimes this is enough:

```text
Account

Name
John Smith

Email
john@example.com


Security

Password
••••••••
```

---

# 3. Not Everything Is a Card

**Not everything is a card.**

A card should represent a meaningful independent object, task, information unit, or decision.

Do not automatically turn these into cards:

* Every section
* Every setting
* Every statistic
* Every paragraph
* Every feature
* Every form area
* Every list item

Avoid deeply nested containers:

```text
Page
└── Card
    ├── Card
    │   └── Card
    └── Card
```

If removing the card does not make the information harder to understand, the card may not be necessary.

---

# 4. Use Borders With a Purpose

Borders should communicate an actual visual relationship, such as:

* A clear boundary
* An input field
* A table
* An interactive region
* A meaningful separation
* A distinct content area

Do not add borders simply because a section "needs more definition".

Avoid giving every section its own box.

Prefer spacing and alignment when they can establish the same relationship.

---

# 5. Use Backgrounds With a Purpose

Do not give every module its own background color.

Avoid:

* A different background for every card
* Backgrounds behind every icon
* A background for every section
* Decorative gradients used to fill empty space
* Colors added simply to make the UI look richer

Backgrounds should serve a purpose, such as:

* Establishing page hierarchy
* Indicating state
* Improving readability
* Representing interaction state
* Defining a meaningful visual region

If removing a background does not reduce comprehension, consider removing it.

---

# 6. Icons Need a Reason to Exist

Use icons when they improve:

* Recognition
* Navigation
* Scanning
* Interaction
* Status communication

Do not add an icon simply because a feature or section exists.

Avoid automatically producing:

```text
🔍 Search
⚙ Settings
📁 Files
🛡 Security
⚡ Performance
```

when the text already communicates the meaning clearly.

Do not give every heading, button, menu item, and section an icon.

---

# 7. Use Proper Icon Libraries

When the project already has an icon library, use it.

Prefer existing icon systems such as the project's configured library over:

* Emoji
* Arbitrary Unicode characters
* Hand-drawn SVG icons
* Random icon sources

Do not use emoji as UI icons.

Do not use arbitrary Unicode characters as substitutes for proper icons when an appropriate icon exists.

For example, avoid using:

```text
🔍
⚙️
📁
➡
✓
```

as a replacement for a consistent icon system.

Simple typographic symbols such as `+`, `−`, or `×` can still be appropriate when they are genuinely part of the control itself.

---

# 8. Do Not Recreate Common Icons

If an appropriate icon already exists in the project's icon library, use it.

Do not manually create SVG paths for common icons such as:

* Search
* Settings
* Menu
* Close
* Chevron
* Trash
* Download
* Upload
* Edit
* Copy
* More

Custom icons are appropriate when they represent a product-specific concept, brand identity, or visual language that existing icons cannot express.

Otherwise:

**Reuse before reinventing.**

---

# 9. Do Not Overuse Badges and Pills

Badges and pills should communicate actual information, such as:

* Status
* Type
* Category
* Permission
* Count
* Special attributes

Do not turn ordinary text into a badge simply for visual variety.

Avoid:

```text
[ Active ] [ Fast ] [ Popular ] [ New ] [ Recommended ]
```

when these labels do not help the user make a decision.

---

# 10. Do Not Overuse Rounded Corners

Rounded corners are not synonymous with modern design.

Do not automatically make:

* Cards rounded
* Buttons rounded
* Inputs rounded
* Badges rounded
* Icon backgrounds rounded
* Containers rounded

Avoid excessive nested rounded shapes.

Use a consistent radius system appropriate to the product instead of applying large rounded corners everywhere.

---

# 11. Use Shadows Sparingly

Shadows should communicate spatial relationships such as:

* Elevation
* Floating elements
* Dialogs
* Dropdowns
* Popovers
* Draggable objects

Do not automatically add shadows to every card.

Avoid layered effects such as:

```text
Page background
  └── Card shadow
      └── Inner card
          └── Inner shadow
```

If the shadow does not communicate a meaningful spatial relationship, it probably does not need to exist.

---

# 12. Do Not Create Visual Noise

When every element competes for attention, nothing is actually emphasized.

Avoid excessive combinations of:

* Colors
* Icons
* Borders
* Cards
* Badges
* Shadows
* Backgrounds
* Different font sizes
* Different corner radii

More visual elements do not necessarily make information clearer.

---

# 13. Empty Space Is Not a Problem

Do not automatically fill empty areas with:

* Cards
* Illustrations
* Icons
* Backgrounds
* Decorative elements
* Extra text
* Statistics

Whitespace can establish:

* Hierarchy
* Rhythm
* Focus
* Readability

Do not try to fill every part of the screen.

---

# 14. Do Not Default to Dashboard Design

AI often turns unrelated products into the same generic dashboard:

```text
Sidebar
└── Dashboard

Top bar

┌────────┐ ┌────────┐ ┌────────┐
│ Metric │ │ Metric │ │ Metric │
└────────┘ └────────┘ └────────┘

┌───────────────────────────────┐
│ Chart                         │
└───────────────────────────────┘

┌────────────┐ ┌────────────┐
│ Card       │ │ Card       │
└────────────┘ └────────────┘
```

Use a dashboard layout only when the product actually requires one.

A settings page, editor, file manager, reader, utility, or tool window does not need to become a dashboard simply because dashboards are common in modern SaaS products.

**Design for the product's workflow, not for a popular template.**

---

# 15. Prefer Familiar Interaction Patterns

Do not reinvent common interactions without a reason.

Examples:

* Settings should use a familiar settings structure.
* Search should behave like a search interface.
* File browsers should follow familiar file-management conventions.
* Tables should use recognizable table interactions.
* Dialogs should have clear modal hierarchy.
* Navigation should follow platform conventions.

Innovation should solve an actual problem, not make familiar interactions harder to understand.

---

# 16. Components Should Serve the Information Structure

Do not use a component simply because the component library provides it.

Do not think:

```text
Card exists → use Card
Tabs exists → use Tabs
Badge exists → use Badge
Tooltip exists → use Tooltip
```

Use this order instead:

```text
Requirement
    ↓
Information structure
    ↓
Interaction
    ↓
Layout
    ↓
Visual hierarchy
    ↓
Components
```

The component should follow the design, not determine it.

---

# 17. Reuse Existing Components

Before creating a new component, check whether the project already has an equivalent.

Prefer existing:

* Components
* Patterns
* Icons
* Design tokens
* Spacing values
* Typography
* Colors
* Interaction patterns

Do not create another Button, Dialog, Dropdown, Input, or Card system if the project already has one.

**Reuse before reinventing.**

---

# 18. Do Not Reimplement Standard Interactive Components

When a mature component already exists in the project, use it instead of implementing a custom version.

This is especially important for:

* Dialogs
* Modals
* Dropdowns
* Selects
* Tooltips
* Popovers
* Tabs
* Toasts
* Accordions
* Menus

These components often involve more than visual styling:

* Keyboard navigation
* Focus management
* Accessibility
* Screen readers
* Positioning
* Interaction states
* Mobile behavior

A custom implementation that merely looks correct may still be incomplete.

---

# 19. Do Not Introduce Unnecessary UI Libraries

Do not add a new UI library for a single component when the project already has a suitable system.

Before adding a dependency, check:

* Whether the project already provides the functionality
* Whether an existing component can be reused
* Whether the framework already provides the feature
* Whether a small local implementation is genuinely appropriate

Avoid mixing multiple unrelated UI systems without a clear reason.

For example, do not turn a project into:

```text
UI Library A
+ UI Library B
+ UI Library C
+ Custom Components
+ Random CSS
```

without a deliberate architectural reason.

---

# 20. Reuse the Existing Design System

If the project already has a visual language, preserve it.

Reuse:

* Colors
* Typography
* Spacing
* Border radius
* Shadows
* Icons
* Component styles
* Interaction states

Do not create a new visual language for every feature.

A new screen should feel like part of the same product.

---

# 21. Do Not Add Features Just to Make the Design Feel Complete

Do not introduce UI for features that were not requested.

Do not automatically add:

* Dashboard
* Analytics
* Onboarding
* Notifications
* Profile systems
* Activity feeds
* Recommendations
* Extra settings
* Decorative statistics

unless they are actually part of the product requirements.

**Do not use additional UI to compensate for a lack of design decisions.**

---

# 22. Prioritize Content

Establish clear levels of importance:

### Primary

Information or actions the user needs most.

### Secondary

Information supporting the primary task.

### Tertiary

Information that can be viewed when needed.

Do not give everything the same visual weight.

If everything is bold, colored, boxed, highlighted, or decorated, there is no hierarchy.

---

# 23. Do Not Design to Demonstrate Design Skill

Avoid decisions such as:

> This area could use a nice gradient.

> This section could have an icon.

> This would look better as a card.

> This could use a glass effect.

Instead ask:

> **Why does the user need this?**

If there is no meaningful answer, do not add it.

---

# 24. AI-Specific Design Anti-Patterns

Pay particular attention to these patterns because they frequently appear in AI-generated interfaces.

### Card + Icon + Background

```text
┌─────────────────────┐
│  ◉                  │
│                     │
│  Feature Name       │
│  Description        │
└─────────────────────┘
```

Do not use this pattern for every feature simply because it looks organized.

### Icon + Colored Circle

```text
   ◉
  blue
```

If the icon is already recognizable, a colored circle behind it may add nothing.

### Everything in a Container

```text
┌─────────────────────────┐
│ ┌─────────────────────┐ │
│ │ ┌─────────────────┐ │ │
│ │ │ Content         │ │ │
│ │ └─────────────────┘ │ │
│ └─────────────────────┘ │
└─────────────────────────┘
```

### Every Section Has a Border

Do not put every section inside a bordered box.

### Everything Has an Icon

Do not add icons to every title, button, menu item, setting, and statistic.

### Everything Has a Badge

Do not turn ordinary text into pills.

### Everything Has Rounded Corners

Do not use rounded rectangles as the default solution for every UI element.

### Everything Has a Background

Do not add a background simply because an area looks empty.

---

# 25. Design Decision Process

When designing a new interface, follow this order.

### Step 1 — Task

What is the user trying to accomplish?

### Step 2 — Content

What does the user need to see?

### Step 3 — Hierarchy

What is most important?

### Step 4 — Structure

Which elements belong together?

### Step 5 — Layout

How should the elements be arranged?

### Step 6 — Interaction

How does the user interact with them?

### Step 7 — Visual Hierarchy

Can spacing, typography, alignment, and contrast establish the hierarchy?

### Step 8 — Components

Which existing components and patterns should be reused?

### Step 9 — Decoration

Only now consider:

* Borders
* Backgrounds
* Icons
* Shadows
* Gradients
* Illustrations
* Animation

If the earlier steps already solve the problem, the final step may require nothing.

---

# 26. Final Review

After designing the interface, ask:

### Remove the border

Is the relationship still clear?

### Remove the background

Is the hierarchy still clear?

### Remove the icon

Can the user still understand the meaning?

### Remove the shadow

Is the spatial relationship still clear?

### Remove the card

Is the content still well organized?

### Remove half of the decoration

Does the interface become clearer?

If yes, remove it.

Also check:

* Did I reuse existing components?
* Did I reuse the project's icon library?
* Did I introduce a new UI pattern unnecessarily?
* Did I add a dependency without a clear reason?
* Did I create a custom component that already exists?
* Did I use emoji or arbitrary Unicode as an icon?
* Did I add visual elements only because the page felt empty?
* Does the interface still feel like the same product?

---

# Core Principles

**Design the information and interaction before the decoration.**

**Use spacing, alignment, and typography to establish hierarchy before adding containers.**

**Not everything is a card.**

**Not everything needs an icon.**

**Not everything needs a border, background, shadow, or rounded corners.**

**Use the project's existing components and icon system before creating new ones.**

**Reuse before reinventing.**

**Do not add dependencies or UI systems without a reason.**

**Design for the product's workflow, not for common AI-generated templates.**

**If a visual element does not communicate information, establish hierarchy, or support interaction, it probably does not need to be there.**