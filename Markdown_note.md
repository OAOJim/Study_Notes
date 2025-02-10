<div align="center">



# Markdown note
</div>

:orange_circle:[1. Format](#1-format)\
:orange_circle:[2. Link](#2-link)\
:orange_circle:[3. Mathematical Expressions](#3-mathematical-expressions)





<div align="center">

## 
### I highly recommand use VScode with [Markdown Preview Github Styling](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles) extension package.
##
## 1. Format
To center text in Markdown:
```html
<center> text need to be centered </center>
```
Center the whole file:
```html
<dev align ="center"> text need to be centered </center>
```
##
## 2. Link
### Link to a URL 
[This is the link to the Github URL of this file](https://github.com/OAOJim/Study_Notes/blob/main/Markdown_note.md)

```MD
[This is the link to the Github URL of this file](https://github.com/OAOJim/Study_Notes/blob/main/Markdown_note.md)
```
##
### Link to a file

[This is the link to this file](./Markdown_note.md)

```MD
[This is the link to this file]((./Markdown_note.md))
```
Note: Both works for GitHub. I recommand link to file.
##
### Link to a location 

Label a location with this code
<div id="here1"></div>

```MD
<div id="here1"></div>
```
And use same way to link to the location\
[Back to here](#here1)

```md
[Back to here](#here1)
```
##
### Link to a title
[Back to the top](#markdown-note)

```md
[Back to the top](#markdown-note)
```



##
## 3. Mathematical Expressions
Use \$ Mathematical expressions in LaTex \$ to get mathematical expressions.

Use `` ```math `` and `` ``` ``
for more fancy features
##
### Matrix
```math          
\begin{matrix}
a & b & c \\
c & d & e \\
f & g & h \\
\end{matrix}
```
```latex
\begin{matrix}
a & b & c \\
c & d & e \\
f & g & h \\
\end{matrix}
```

```math 
\begin{bmatrix}
a & b & c \\
c & d & e \\
f & g & h \\
\end{bmatrix}
```

```latex
\begin{bmatrix}
a & b & c \\
c & d & e \\
f & g & h \\
\end{bmatrix}
```
##
### Cases
```math 
\begin{align}
\begin{cases}
a = b + c \\
b = a + c \\
c = a + b \\
\end{cases}
\end{align}
```

```latex
\begin{align}
\begin{cases}
a = b + c \\
b = a + c \\
c = a + b \\
\end{cases}
\end{align}
```
##
### Label an equation
```math 
\tag{1.1}
\begin{align}
A = B + C 
\end{align}
```

```latex
\tag{1.1}
\begin{align}
A = B + C 
\end{align}
```





