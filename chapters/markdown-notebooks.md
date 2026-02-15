---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Notebooks with MyST Markdown

Jupyter Book also lets you write text-based notebooks using MyST Markdown.
See [the Notebooks with MyST Markdown documentation](https://jupyterbook.org/file-types/myst-notebooks.html) for more detailed instructions.
This page shows off a notebook written in MyST Markdown.

## An example cell

With MyST Markdown, you can define code cells with a directive like so:

```{code-cell}
print(2 + 2)
```

When your book is built, the contents of any `{code-cell}` blocks will be
executed with your default Jupyter kernel, and their outputs will be displayed
in-line with the rest of your content.

```{seealso}
Jupyter Book uses [Jupytext](https://jupytext.readthedocs.io/en/latest/) to convert text-based files to notebooks, and can support [many other text-based notebook files](https://jupyterbook.org/file-types/jupytext.html).
```

## Create a notebook with MyST Markdown

MyST Markdown notebooks are defined by two things:

1. YAML metadata that is needed to understand if / how it should convert text files to notebooks (including information about the kernel needed).
   See the YAML at the top of this page for example.
2. The presence of `{code-cell}` directives, which will be executed with your book.

That's all that is needed to get started!

## Quickly add YAML metadata for MyST Notebooks

If you have a markdown file and you'd like to quickly add YAML metadata to it, so that Jupyter Book will treat it as a MyST Markdown Notebook, run the following command:

```
jupyter-book myst init path/to/markdownfile.md
```

## Block Directives

```{note}
This is a note admonition. Use it to highlight important information!
```

```{warning}
This is a warning. Use it to alert users about potential issues.
```

```{tip}
Pro tip: MyST directives make your content more engaging and organized!
```

## Code Blocks and Syntax Highlighting 

### Basic Code Blocks

```python
def hello_world():
    """A simple Python function."""
    print("Hello, Jupyter Book!")
    return "Welcome to the tutorial!"

# Call the function
result = hello_world()
```

### Code with Line Numbers

```{code-block} python
:linenos:
:emphasize-lines: 2, 4

import numpy as np
import matplotlib.pyplot as plt

# Generate sample data
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Create plot
plt.figure(figsize=(10, 6))
plt.plot(x, y, 'b-', linewidth=2)
plt.title('Sine Wave Example')
plt.xlabel('X values')
plt.ylabel('Y values')
plt.grid(True)
plt.show()
```

### Multiple Language Examples

**JavaScript:**
```javascript
function createChart(data) {
    const ctx = document.getElementById('myChart').getContext('2d');
    return new Chart(ctx, {
        type: 'line',
        data: data,
        options: {
            responsive: true,
            title: {
                display: true,
                text: 'Sample Chart'
            }
        }
    });
}
```

**SQL:**
```sql
SELECT 
    student_id,
    student_name,
    AVG(grade) as average_grade
FROM students s
JOIN grades g ON s.id = g.student_id
WHERE semester = '2024-Fall'
GROUP BY student_id, student_name
HAVING AVG(grade) > 85
ORDER BY average_grade DESC;
```

## Mathematical Expressions 
### Inline Math
The quadratic formula is {math}`x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}`.

### Block Math Equations
:ref:Equations

```{math}
:label: quadratic-formula

x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
```

```{math}
:label: euler-identity

e^{i\pi} + 1 = 0
```

### Complex Mathematical Expressions

```{math}
\begin{align}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} &= \frac{4\pi}{c}\vec{\mathbf{j}} \\
\nabla \cdot \vec{\mathbf{E}} &= 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} &= \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} &= 0
\end{align}
```

## Admonitions and Callouts 
```{attention}
Pay attention to this important information!
```

```{caution}
Be careful when implementing this approach.
```

```{danger}
This operation can be dangerous if not done correctly.
```

```{error}
This shows an error message format.
```

```{hint}
Here's a helpful hint for better understanding.
```

```{important}
This information is crucial for success.
```

```{note}
Additional notes and context go here.
```

```{seealso}
See also: Related topics and references.
```

```{tip}
Useful tips and best practices.
```

```{warning}
Warning about potential issues.
```

### Custom Admonitions

```{admonition} Custom Title
:class: dropdown

This is a custom admonition with a dropdown feature.
You can click to expand/collapse this content.
```

## Cross-References and Links 

### Internal References
- Reference to equation: {eq}`quadratic-formula`

### External Links
- [Jupyter Book Documentation](https://jupyterbook.org/)
- [MyST Parser](https://myst-parser.readthedocs.io/)


## Images and Media 
### Basic Image Inclusion

```{figure} logo.png
:alt: Alternative text
:width: 500px
:align: center

Caption for your image goes here.
```

### Images with Custom Sizing

```{image} logo.png
:alt: Description
:class: shadow
:width: 300px
:height: 200px
```




