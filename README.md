<p align="center">
  <a href="https://example.com/">
    <img src="https://github.com/Almanza-Conejo/imagesRepo/blob/main/almanza.png" alt="Almanza-Conejo" width=300 height=70>
  </a>
  <p align="center">
    <br>
    M.E. Almanza-Conejo</h2>
    <br>
    <a href="https://www.linkedin.com/in/oalmanzaconejo/" rel="nofollow noreferrer">
    <img src="https://i.stack.imgur.com/gVE0j.png" alt="linkedin"> LinkedIn
    </a> &nbsp; 
    <a href="https://www.researchgate.net/profile/Oscar-Almanza-Conejo" rel="nofollow noreferrer">
    <img src="https://user-images.githubusercontent.com/54937357/126514422-ba0e7de1-cbc2-4186-94d9-39e8a22c1c78.png" width="14" height="14" alt="ResearchGate"> ResearchGate
    </a> &nbsp;
    <a href="https://medium.com/@almanzaConejo" rel="nofollow noreferrer">
    <img src="https://raw.githubusercontent.com/Medium/medium-logos/master/03_Symbol/01_Black/PNG/RGB/Medium-Symbol-Black-RGB%401x.png" width="17" height="17" alt="linkedin"> Medium
  </a>
  </p>
</p>

# TikZ_axisTemplate

This is a repo that includes a template for plotting functions. The $\LaTeX$ template is:

``` js
\documentclass[border = 2mm]{standalone}
\usepackage[utf8]{inputenc}
\usepackage{amsmath,siunitx}
\usepackage{amssymb}
\usepackage{amsbsy}

% -- color
\usepackage[dvipsnames]{xcolor}
    %  --  define new colors (Actual color palett)
    \definecolor{gamboge}{rgb}{0.89, 0.61, 0.06}	
    \definecolor{aqua}{rgb}{0.0, 1.0, 1.0}	
    \definecolor{coralred}{rgb}{1.0, 0.25, 0.25}
    \definecolor{darkchampagne}{rgb}{0.76, 0.7, 0.5}	
    \definecolor{darktan}{rgb}{0.57, 0.51, 0.32}	
    \definecolor{ferrarired}{rgb}{1.0, 0.11, 0.0}
    \definecolor{flamingopink}{rgb}{0.99, 0.56, 0.67}
    \definecolor{gold}{rgb}{1.0, 0.84, 0.0}
    \definecolor{lavenderblue}{rgb}{0.8, 0.8, 1.0}
    \definecolor{lightgreen}{rgb}{0.56, 0.93, 0.56}
    \definecolor{mediumchampagne}{rgb}{0.95, 0.9, 0.67}
    \definecolor{orangepeel}{rgb}{1.0, 0.62, 0.0}
    \definecolor{palemagenta}{rgb}{0.98, 0.52, 0.9}
    \definecolor{raspberry}{rgb}{0.89, 0.04, 0.36}
    \definecolor{skyblue}{rgb}{0.53, 0.81, 0.92}

\usepackage{tikz}
\usetikzlibrary{math,plotmarks,arrows.meta,fit}
\usepackage{pgfplots}
\pgfplotsset{compat=1.12}
\newcommand{\pointer}[1]{\node[red] at #1 {$\times$};}

%  --  data filename
\newcommand{\fileName}{AMIGOS_quaternion_HVHA.txt}

%  --  to avoid lines into the legend box
\tikzset{
    clip even odd rule/.code={\pgfseteorule}, % Credit to Andrew Stacey 
    invclip/.style={
        clip,insert path=
            [clip even odd rule]{
                [reset cm](-\maxdimen,-\maxdimen)rectangle(\maxdimen,\maxdimen)
            }
    }
}

\begin{document}
\begin{tikzpicture}
    \tikzmath{
        %  --  initial and end time for the ROI into the plot
        \iniTime = 0.55;
        \endTime = 0.65;
    }
    \begin{axis}[
        name = eegSignals,
        %   -- dimentions
        height = 8cm, width = 14cm,
        %   --  limits
        xmin = 0, xmax = 1,
        ymin = 0, ymax = 1,
        % divisiones
        % xtick distance = 2,
        % ytick distance = 2,
        % subdivisiones
        minor x tick num = 1,
        minor y tick num = 1,
        %   --  labels
        title = {\centering
                $\boldsymbol{\mathfrak{Re}}, \boldsymbol{\mathfrak{Im}}$, 
                and $\boldsymbol{\mathfrak{Abs}}$ normalized magnitude for
                $qp \left(\forall\left\{q,p\right\} \in \mathbb{H}\right)$
                quaternion product for HVHA class\\},
        title style = {text width=10cm, font=\normalsize},
        xlabel = Time (s), ylabel = Normalized magnitude,
        ylabel style = {rotate = 0, xshift = 1mm},
        %   --  grid
        grid = both,
        minor grid style = {opacity = 0.15},
        %   --  legend
        legend style = {
            name = legendEEG,
            legend pos = outer north east,
            legend cell align = left,
            legend columns = 2,
            font = \scriptsize,
        },
    ]
    % %   --  add plot
        % \addplot[
        %     % inset options here
        % ]   table [
        %     % inset table options here
        % ]   {
        %     % inset data file name here
        % };
    \end{axis}
```
