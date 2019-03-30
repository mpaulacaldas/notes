# LaTeX

## Bind PDFs

```tex
% Found here: https://gist.github.com/ppanyukov/1035536
% Careful, hyperlinks are not preserved!

\documentclass[a4paper]{article}
\usepackage{pdfpages}
\begin{document}
\includepdf[pages=-, scale=1]{doc01.pdf}
\includepdf[pages=-, scale=1]{doc02.pdf}
\end{document}
```
