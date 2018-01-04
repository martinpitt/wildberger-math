These are my notes and additional files for various mathematical YouTube online courses of
[Norman Wildberger](https://www.youtube.com/channel/UCXl0Zbk8_rvjyLwAR-Xh9pQ).

Most of them are written in MarkDown with math formulas written in LaTeX. The
documents can be rendered with [pandoc](http://pandoc.org/), which is packaged
in all major Linux distributions. For example:

```sh
pandoc -t latex -o algcalc.pdf algcalc.md
```

I use [vim](http://www.vim.org/) for editing, and this `~/.vimrc` snippet to
make this more comfortable:

```
"-- pandoc Markdown+LaTeX -------------------------------------------

function s:MDSettings()
    inoremap <buffer> <Leader>n \note[item]{}<Esc>i
    noremap <buffer> <Leader>b :! pandoc -t beamer % -o %<.pdf<CR><CR>
    noremap <buffer> <Leader>l :! pandoc -t latex % -o %<.pdf<CR>
    noremap <buffer> <Leader>v :! evince %<.pdf 2>&1 >/dev/null &<CR><CR>

    " adjust syntax highlighting for LaTeX parts
    "   inline formulas:
    syntax region Statement oneline matchgroup=Delimiter start="\$" end="\$"
    "   environments:
    syntax region Statement matchgroup=Delimiter start="\\begin{.*}" end="\\end{.*}" contains=Statement
    "   commands:
    syntax region Statement matchgroup=Delimiter start="{" end="}" contains=Statement
endfunction

autocmd BufRead,BufNewFile *.md setfiletype markdown
autocmd FileType markdown :call <SID>MDSettings()
```
