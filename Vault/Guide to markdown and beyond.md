Obsidian understands standard markdown syntaxes, including: **bold**, *italic*, ~~strikethrough~~, ==highlight== and many more:

## Headings

```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

## Links

Links use a set of square brackets (`[]`) for describing the link text, followed by regular parentheses (`()`) containing the URL.

[Rick and Morty](https://www.imdb.com/title/tt2861424/).

Also link to other files [[Guide to markdown and beyond]]

## Lists

Press supports ordered (numbered) and unordered (bulleted) lists. Unordered lists use "-".


- National Treasure
- Ghost Rider
- Face/Off


Ordered lists use numbers followed by periods:

1. The Last of Us
2. Death Stranding
3. Cyberpunk 2077

### Thematic breaks

Lines starting with three asterisks (`*`), hyphens (`-`) or underscores (`_`) are rendered as horizontal rules, a.k.a. “thematic breaks”.

---

## Quotes

> A paragraph starting with a `>` are rendered as a quote.

## Callouts

> [!warning] 
> Callout


## Code blocks

```
fun helloWorld() {
  println("""
    Code blocks are wrapped inside
    three ticks.
  """)
}
```


## Tables

| Title              | Watched |
| ------------------ | ------- |
| Brooklyn Nine-Nine | ✅       |
| The Expanse        | ✅       |

## *full-on* LaTeX



```latexsvg
\documentclass{standalone}
\usepackage{pgfplots}
\pgfplotsset{compat=newest}

\begin{document}
\begin{tikzpicture}
  \begin{axis}[
    view={60}{30}, % Change the viewing angle
    axis lines=middle,
    domain=-2:2, % X and Y domain limits
    samples=25, % Number of samples for plotting
    ]
    % Hyperbolic paraboloid z = x^2 - y^2
    \addplot3[surf,mesh/ordering=y varies] 
    ({x},{y},{x^2 - y^2});
  \end{axis}
\end{tikzpicture}
\end{document}

```

Copy `tikz-cd` code from https://q.uiver.app/ and press `ALT+E` then `quiver`:

```latexsvg
\documentclass{standalone}
\usepackage{tikz-cd}\usepackage{amsfonts}\usepackage{amsmath}\usepackage{quiver}\usepackage{mathrsfs}

\begin{document}
\tikzcdset{scale cd/.style={every label/.append style={scale=#1},cells={nodes={scale=#1}}}}
% \begin{tikzcd}[scale cd=0.8]

% https://q.uiver.app/#q=WzAsMixbMCwwLCJBIl0sWzAsMSwiQiJdLFswLDFdXQ==
\begin{tikzcd}
	A \\
	B
	\arrow[from=1-1, to=2-1]
\end{tikzcd}

\end{document}
```

