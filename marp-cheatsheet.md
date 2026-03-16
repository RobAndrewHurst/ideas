---
marp: true
theme: geolytix
paginate: true
header: "Marp Cheatsheet"
footer: "Geolytix"
---

<!-- _class: lead -->
<!-- _header: "" -->
<!-- _footer: "" -->
<!-- _paginate: false -->

# **Marp Cheatsheet**

Everything you need to make great slides

---

# Frontmatter

Every Marp deck starts with YAML frontmatter at the top of the file.

```yaml
---
marp: true
theme: geolytix
paginate: true
header: "My Header"
footer: "My Footer"
---
```

| Key        | Purpose                           |
| ---------- | --------------------------------- |
| `marp`     | Enable Marp rendering             |
| `theme`    | Set the CSS theme                 |
| `paginate` | Show slide numbers                |
| `header`   | Text in the top of every slide    |
| `footer`   | Text in the bottom of every slide |

---

# Slide Breaks

Separate slides with a horizontal rule `---` on its own line.

```markdown
# Slide One

Content here

---

# Slide Two

More content here
```

> Tip: Leave a blank line before and after the `---`.

---

# Headings & Text

```markdown
# Heading 1

## Heading 2

### Heading 3

#### Heading 4

Regular paragraph text.
**Bold text** and _italic text_.
~~Strikethrough~~ and `inline code`.
```

# Heading 1

## Heading 2

### Heading 3

Regular paragraph text.
**Bold text** and _italic text_.
~~Strikethrough~~ and `inline code`.

---

# Lists

```markdown
- Unordered item one
- Unordered item two
  - Nested item

1. Ordered item one
2. Ordered item two
   1. Nested ordered
```

- Unordered item one
- Unordered item two
  - Nested item

1. Ordered item one
2. Ordered item two
   1. Nested ordered

---

# Links & Images

```markdown
[Link text](https://example.com)

![Alt text](image.png)

![width:300px](image.png)

![height:200px](image.png)
```

Use Marp's **image size filters** by adding dimensions in the alt text:

| Filter         | Effect              |
| -------------- | ------------------- |
| `width:300px`  | Set image width     |
| `height:200px` | Set image height    |
| `w:50%`        | Width as percentage |
| `blur:5px`     | Blur filter         |
| `grayscale`    | Grayscale filter    |
| `sepia`        | Sepia filter        |

---

# Tables

```markdown
| Name    | Role      | Location |
| ------- | --------- | -------- |
| Alice   | Analyst   | London   |
| Bob     | Developer | Berlin   |
| Charlie | Designer  | New York |
```

| Name    | Role      | Location |
| ------- | --------- | -------- |
| Alice   | Analyst   | London   |
| Bob     | Developer | Berlin   |
| Charlie | Designer  | New York |

> Column alignment: `:---` left, `:---:` center, `---:` right.

---

# Blockquotes

```markdown
> This is a blockquote.
> It can span multiple lines.

> **Tip:** Use blockquotes for callouts and tips.
```

> This is a blockquote.
> It can span multiple lines.

> **Tip:** Use blockquotes for callouts and tips.

---

# Code Blocks

Use fenced code blocks with a language identifier for syntax highlighting.

````markdown
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
```
````

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
```

```python
def greet(name):
    return f"Hello, {name}!"
```

---

# Math (KaTeX)

Inline math: `$E = mc^2$` renders as $E = mc^2$

Block math:

```markdown
$$
\int_{a}^{b} f(x)\,dx = F(b) - F(a)
$$
```

$$
\int_{a}^{b} f(x)\,dx = F(b) - F(a)
$$

---

# Background Images

Set a full-slide background image using the `bg` keyword in the alt text.

```markdown
![bg](https://example.com/photo.jpg)
```

### Background modifiers

| Syntax                  | Effect                   |
| ----------------------- | ------------------------ |
| `![bg](url)`            | Cover background         |
| `![bg contain](url)`    | Contain (fit) background |
| `![bg fit](url)`        | Same as contain          |
| `![bg auto](url)`       | Original size            |
| `![bg 50%](url)`        | Scale to 50%             |
| `![bg opacity:.5](url)` | 50% opacity              |
| `![bg blur:5px](url)`   | Blurred background       |

---

# Split Backgrounds

Place content alongside a background image.

```markdown
![bg left](image.jpg)

# My Slide Title

Content appears on the right side.
```

| Syntax                | Effect                          |
| --------------------- | ------------------------------- |
| `![bg left](url)`     | Image on left, content on right |
| `![bg right](url)`    | Image on right, content on left |
| `![bg left:40%](url)` | Image takes 40% of the left     |

---

# Multiple Backgrounds

Stack multiple background images on one slide.

```markdown
![bg](image1.jpg)
![bg](image2.jpg)
![bg](image3.jpg)
```

This splits the background into equal columns by default.

### Vertical split

```markdown
![bg vertical](image1.jpg)
![bg](image2.jpg)
```

Splits backgrounds into rows instead of columns.

---

# Background Colour

Set a solid background colour with a directive.

```markdown
<!-- backgroundColor: #003d57 -->
<!-- color: #ffffff -->

# Dark Slide

With custom background and text colour.
```

Or use the `_backgroundColor` scoped directive to apply to a single slide only:

```markdown
<!-- _backgroundColor: #003d57 -->
<!-- _color: #ffffff -->
```

---

# Directives: Global vs Local

Directives control slide behaviour. Prefix with `_` to scope to one slide.

### Global (all slides from this point)

```html
<!-- class: lead -->
<!-- paginate: true -->
<!-- header: "Section Title" -->
```

### Local (current slide only)

```html
<!-- _class: lead -->
<!-- _paginate: false -->
<!-- _header: "" -->
<!-- _footer: "" -->
```

---

# Slide Classes

Apply CSS classes to slides using the `class` directive.

```html
<!-- _class: lead -->
```

### Built-in classes (Geolytix theme)

| Class    | Effect                                |
| -------- | ------------------------------------- |
| `lead`   | Title slide — dark primary background |
| `invert` | Inverted — dark grey background       |

```markdown
<!-- _class: lead -->

# Title Slide

This has the dark Geolytix primary background.
```

---

# Scoped Styling

Add custom CSS to individual slides using a `<style scoped>` tag.

```html
<style scoped>
  h1 {
    color: #d57120;
  }
  p {
    font-size: 16pt;
  }
  section {
    justify-content: center;
    text-align: center;
  }
</style>
```

<style scoped>
section { text-align: center; }
h1 { color: #d57120; }
</style>

# This heading is orange

And the content is centred.

---

# Global Styling

Add CSS that applies to **all slides** with a `<style>` tag (no `scoped`).

Place it at the top of your deck, right after the frontmatter.

```html
---
marp: true
theme: geolytix
---

<style>
  section {
    font-size: 18pt;
  }
  h1 {
    text-transform: uppercase;
  }
</style>
```

---

# Fragmented Lists (Animations)

Marp supports simple list animations with the `*` class.

```html
<!-- This is a Marp CLI / export feature -->

* Item one * Item two * Item three

<!-- Use "* " prefix for animated items -->
```

> Note: Fragment animations work in **HTML export** mode, not in PDF.

---

# Speaker Notes

Add speaker notes using HTML comments with the special format:

```markdown
# My Slide

Content visible to the audience.

<!--
These are speaker notes.
They will appear in presenter view
but not on the projected slide.
-->
```

> View them in **Presenter Mode** (Marp for VS Code or HTML export).

---

# HTML in Slides

You can use raw HTML for advanced layouts.

```html
<div style="display: flex; gap: 2em;">
  <div>### Column 1 Content for the left column.</div>
  <div>### Column 2 Content for the right column.</div>
</div>
```

> Leave blank lines between HTML tags and Markdown content.

---

# Emoji

Marp supports GitHub-style emoji shortcodes.

```markdown
:rocket: :tada: :thumbsup: :warning: :bulb:
```

:rocket: :tada: :thumbsup: :warning: :bulb:

---

# Exporting Slides

### Marp CLI

```bash
# HTML
marp slides.md

# PDF
marp slides.md --pdf

# PowerPoint
marp slides.md --pptx

# Images (PNG per slide)
marp slides.md --images png

# With custom theme
marp slides.md --theme geolytix.css --pdf
```

### VS Code

Use the **Marp for VS Code** extension and run:
`Marp: Export Slide Deck...` from the command palette.

---

# Page Number Formatting

```yaml
---
paginate: true
---
```

Hide page number on a specific slide:

```html
<!-- _paginate: false -->
```

Skip pagination (keep counting but hide):

```html
<!-- _paginate: skip -->
```

Show pagination as "hold" (keep showing the previous number):

```html
<!-- _paginate: hold -->
```

---

# Fitting Text

Use Marp's `<!-- fit -->` directive to auto-scale a heading to fill the slide width.

```markdown
# <!-- fit --> This heading scales to fit
```

# <!-- fit --> Auto-scaled heading

---

<!-- _class: lead -->
<!-- _header: "" -->
<!-- _footer: "" -->
<!-- _paginate: false -->

# **Quick Reference**

| Syntax                      | What it does     |
| --------------------------- | ---------------- |
| `---`                       | New slide        |
| `<!-- _class: lead -->`     | Title slide      |
| `![bg](url)`                | Background image |
| `![bg left:40%](url)`       | Split layout     |
| `![w:300px](url)`           | Sized image      |
| `$...$` / `$$...$$`         | Math             |
| `<!-- fit -->`              | Auto-fit heading |
| `<!-- _paginate: false -->` | Hide page number |
| `<style scoped>`            | Per-slide CSS    |

---

<!-- _class: lead -->
<!-- _header: "" -->
<!-- _footer: "" -->
<!-- _paginate: false -->

# **Happy Presenting!**

Built with the **Geolytix** Marp theme
