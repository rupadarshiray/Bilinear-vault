# Guide to markdown and beyond

Obsidian understands standard markdown syntaxes, including: **bold**, *italic*, ~~strikethrough~~, ==highlight== and many more:

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6


## Links
Links use a set of square brackets (`[]`) for describing the link text, followed by regular parentheses (`()`) containing the URL.

[Rick and Morty](https://www.imdb.com/title/tt2861424/).

## Lists
Press supports ordered (numbered) and unordered (bulleted) lists. Unordered lists use asterisks, pluses, and hyphens — interchangeably — as list markers:

- National Treasure
+ Ghost Rider
* Face/Off

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
```python
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
    xlabel={$x$},
    ylabel={$y$},
    zlabel={$z$},
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
