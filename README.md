# amr-utils
A python package of common operations for AMRs


I wrote amr-utils to store operations that I often need when doing research with AMRs. 
### Features:
- Load multiple AMRs from a text file
- iterate through nodes, edges, or named entities
- output AMRs to useful formats: html (AMR string) or latex (AMR graph)
- associates a unique id to each node or edge (can be used for styling a particular element in a webpage or web app)
- use a Rule-Based Aligner to align AMR nodes and edges with words in a sentence.

### Requirements
Python 3.6 or higher

### Input
Input should contain AMR strings separated by a blank line. Lines starting with `#` will be ignored.

# Latex
Amr-utils allows you to read AMRs from a text file and output them as latex diagrams, such as the following.
![latex example](https://github.com/ablodge/amr-utils/blob/master/latex_ex.PNG)

### Colors
The default coloring assigns a different color to each node in a given row. To change a color by hand, just rewrite `\node[red]` as `\node[purple]`, etc.

### Instructions
Run as follows:

`python amr_latex.py [input file] > [output file]`

Add these lines to your latex file:

```
\usepackage{tikz}
\usetikzlibrary{shapes}
```


# HTML
Amr-utils allows you to read AMRs from a text file and output them as html. You can look in `style.css` for an example of styling. 
![html example](https://github.com/ablodge/amr-utils/blob/master/html_ex.png)
### Instructions
Run as follows:

`python amr_html.py [input file] > [output file]`

# Rule-Based Alignment
Aligns AMR nodes and edges to words in its reference sentence. The aligner handles named-entity alignment, alignment of frames, and relations. A single alignment looks like:

`broaden-01 :ARG0 :ARG1 ~ broadened` (readible)

`b b_ARG0_i b_ARG1_r ~ 1` (machine-readible)

### Instructions
Run as follows:

`python alignment.py [amr file] [sentence file] > [output file]`
