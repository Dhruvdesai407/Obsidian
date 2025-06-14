Okay, let's make it even more concise for quick spaced recall. I'll focus on **keywords** and **brief definitions** for each concept and tag.

***

# HTML Quick Recall Guide

## Tags: #Programming #Webdev #revision
## Priority :Medium
## Core Concept (One Sentence Summary)

>HTML **structures web content** using **elements (tags)**.

---

## Minimal HTML Example (Structure)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
</head>
<body>
    <header><h1>Header</h1></header>
    <nav><ul><li><a href="#">Nav Link</a></li></ul></nav>
    <main>
        <article>
            <h2>Article Title</h2>
            <p>Paragraph with <span>inline text</span>.</p>
            <a href="#">Link</a>
            <img src="img.jpg" alt="Image Desc">
            <ul><li>Unordered Item</li></ul>
            <ol><li>Ordered Item</li></ol>
            <form><label>Name:<input type="text"></label><button>Submit</button></form>
            <table><thead><tr><th>Table Head</th></tr></thead><tbody><tr><td>Table Data</td></tr></tbody></table>
        </article>
        <aside><h3>Sidebar</h3></aside>
    </main>
    <footer><p>&copy; Footer</p></footer>
</body>
</html>
```

---

## Key HTML Elements & Purpose (Ultra-Concise)

* **`<!DOCTYPE html>`**: HTML5 declaration.
* `<html lang="en">`: **Root** of document.
* `<head>`: **Page metadata** (not visible).
    * `<meta charset="UTF-8">`: Character encoding.
    * `<meta name="viewport" ...>`: Responsive display.
    * `<title>`: Browser tab title.
* `<body>`: **Visible page content**.

* **Semantic Structure (HTML5):** Add **meaning** to sections.
    * `<header>`: Intro/Nav container.
    * `<nav>`: Navigation links.
    * `<main>`: Dominant content.
    * `<article>`: Self-contained content.
    * `<aside>`: Sidebar/related content.
    * `<footer>`: Section/document footer.

* **Text:**
    * `<h1>`-`<h6>`: Headings (importance).
    * `<p>`: Paragraph.
    * `<span>`: Inline text (styling).

* **Lists:**
    * `<ul>`: Unordered (bullets).
    * `<ol>`: Ordered (numbers).
    * `<li>`: List item.

* **Links & Images:**
    * `<a href="url">`: Hyperlink (`target="_blank"` new tab).
    * `<img src="path" alt="desc">`: Image (`alt` for accessibility).

* **Containers:**
    * `<div>`: Generic **block-level** container.
    * `<span>`: Generic **inline** container.

* **Forms:**
    * `<form action="url" method="post">`: Input form.
    * `<label for="id">`: Input label.
    * `<input type="text">`: Input field.
    * `<button type="submit">`: Form button.

* **Tables:**
    * `<table>`: Table container.
    * `<thead>`: Table header row group.
    * `<tbody>`: Table body row group.
    * `<tr>`: Table row.
    * `<th>`: Table header cell.
    * `<td>`: Table data cell.

---

This guide provides an **ultra-concise reference** to key HTML elements, perfect for **quick spaced recall**.
