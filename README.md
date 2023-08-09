# Use adstex instead!

***I recommend using [adstex](https://github.com/yymao/adstex#adstex) instead of aux2adsbib. This was a fun project for me to write, but adstex is a much more capable utility. Projects that used aux2adsbib should be able to switch to adstex without any modifications.***

# aux2adsbib

aux2adsbib is a small program that parses a LaTeX .aux file and automatically generates a bibTeX library by querying NASA/ADS.

## Usage

In your LaTeX source (say `ms.tex`), cite references using their [ADS](https://ui.adsabs.harvard.edu/) code, e.g.,

```
\cite{2022SoPh..297...22D}
```
and specify `ms.bib` as your bibliography,
```
\bibliography{ms}
```
Then, compile your LaTeX source as you normally would to produce an .aux file. LaTeX will complain about undefined citations. Next, run `aux2adsbib`:
```
aux2adsbib ms.tex
```
`aux2adsbib` will parse the `ms.aux` file for references, look up those codes in ADS, and generate the `ms.bib` file. Finally, run BibTeX and LaTeX again as normal.
