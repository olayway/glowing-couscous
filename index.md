---
title: Welcome to Flowershow Demo!
description: Explore Flowershow's features and configuration options in this demo site!
image: "[[hiroshige.jpg]]"
showHero: true
cta:
  - label: Explore syntax
    href: "#-markdown-syntax"
  - label: See demo blog →
    href: /blog
---

This site is published from https://github.com/flowershow/demo using [Flowershow](https://flowershow.app). You can check all the underlying markdown and source code in that repo and see the resulting website powered by Flowershow live online at https://demo.flowershow.app/.

## 🎯 What's Inside?

This demo showcases various Flowershow features and configuration options:

- 📝 **Rich Markdown Support**
    - Tables, code blocks, and diagrams
    - Math equations and LaTeX
    - Callouts and blockquotes
    - Obsidian wiki-links
    - …and more!
- 🎨 **Customization Options**
    - Comments
    - Navigation setup
    - Custom domains

## 📚 Markdown Syntax

### Text Formatting

**Bold text**, *italic text* and ***bold italic text***
~~Strikethrough text~~
`Inline code`
==Highlighted text== (🚧 [issue #894](https://github.com/flowershow/flowershow/issues/894))

### Lists

Unordered list:
* Item 1
* Item 2
  * Nested item 2.1
  * Nested item 2.2
* Item 3

Ordered list:
1. First item
2. Second item
   1. Nested item 2.1
   2. Nested item 2.2
3. Third item

### Task Lists

- [x] Completed task
- [ ] Incomplete task
- [ ] Another task
  - [x] Nested completed task
  - [ ] Nested incomplete task

### Code Blocks

Inline code: `const greeting = "Hello, World!";`

```javascript
// JavaScript example
function calculateSum(a, b) {
  return a + b;
}
const result = calculateSum(5, 3);
console.log(result); // Output: 8
```

```python
# Python example
def greet(name):
    return f"Hello, {name}!"
print(greet("Flowershow"))
```

### Tables

| Book Type | Average Length | Reading Time |
|-----------|---------------|--------------|
| Novel | 300 pages | 5 hours |
| Magazine | 50 pages | 1 hour |
| Comic Book | 30 pages | 30 minutes |
| Cookbook | 200 pages | 2 hours |

### Blockquotes

> Single line quote

> Multi-line quote
> with multiple paragraphs
> > Nested quote
> > > Deeper nested quote

### Links & Embeds

Markdown link:
```md
[Visit Flowershow](https://flowershow.app)
```
→ [Visit Flowershow](https://flowershow.app)

Image embed:
```md
![Hiroshige art](/assets/hiroshige-2.jpg)
```
→
![Hiroshige art](/assets/hiroshige-2.jpg)

### Obsidian Wiki-links

Flowershow supports **Obsidian-style wiki-links** too.

**Link by shortest-possible path:**
```md
[[Lorem ipsum]]
```
→ [[Lorem ipsum]]

**Link by full path:**
```md
[[blog/Lorem ipsum]]
```
→ [[blog/Lorem ipsum]]

**Use an alias:**
```md
[[Lorem ipsum|Alias]]
```
→ [[Lorem ipsum|Alias]]
