#Vim Notes

##Contents
[TOC]

###Command Structure
`[range]` `[command]`

###Move
- - -
&larr;`h` &darr;`j` `k`&uarr; `l`&rarr;

`0` `gm` `$` : beginning, middle, end of line
`^` : first character of line

&larr;`b` `w`&rarr; : beginning of word
///&larr;`B` `W`&rarr; : beginning of word (whitespaced)

&larr;`ge` `e`&rarr; : end of word
&larr;`gE` `E`&rarr; : end of word (whitespaced)

&uarr;`U`, `D`&darr; : move half screen `U`p, `D`own
&uarr;`B`, `F`&darr; : move screen `B`ackward, `F`orward

`gg`, `G` : start, end of file
`nG` : set cursor to the first char of the line
`H`, `M`, `L` : move `H`ome, `M`iddle, `L`ast line of screen
`zt`, `zz`, `zb` : make current line as `t`op, middle, `b`ottom of screen

`%` : closure pair/matching brace
``.` : previous change

`O`, `I` : older, newer :jump
`{`, `}` : next, previous empty line
`(`, `)` : next, previous sentence
`:`*n* : line number *n*

###Edit
- - -
`i`, `a` : `i`nsert before, `a`ppend after cursor
`I`, `A` : `I`nsert before, `A`ppend after line

`o`, `O` : new line bel`o`w, ab`O`ve

`r`*x* : `r`eplace character on cursor with *x*
`R` : type over/replace
`J` : join this, next line
`~` : change character case

`u` : undo
`ctrl + r` : redo
`U` : undo current line changes

`ctrl + n` : dropdown word completion
/// `XL` : complete line
`:changes` : show changes

`cc` : `c`hange line (stay at the current line)
`ct"` : `c`hange content of double quote (etc)
`ci"` : `c`hange `i`nside of `""` (exclude)
`ca"` : `c`hange `a`round of `""` (include)

`c/` : `c`hange from cursor until the searched word


###Cut/Delete
- - -
&larr;`X`, `x`&rarr; : before, next character
`D` : to en`D` of line

`dd` : `d`elete current line (every delete is a cut) and move to the next line
`dj` : `d`elete current line and the line after (2 lines)

`:`10,20`d` : line *10* through *20*
`:`'x,'y`d` : between mark *x* and *y*

`d/` : `d`elete from cursor until the searched word

###Copy
- - -
`y` : `y`ank/copy
`yy` : `y`ank current line
`yj` : `y`ank current line and the line after (2 lines)
`:`10,20`y` : yank line *10* through *20*
///`y`*n* : `y`ank *n* lines

*[visual]*`y` : copy selection
`y/` : `y`ank from cursor until the searched word

###Paste
- - -
&larr;`P` `p`&rarr; : `P`aste before, after

###Indentation
- - -
`ctrl + t` : indent current line (insert mode)
`ctrl + d` : deindent current line (insert mode)
`n>>` : indent n number of lines
`n<<` : de-indent n number of lines
`=` : normalise current line to default indentation
`=5j` : normalise 5 line(j=below) to default indentation
`=5j` : normalise 5 line(k=above) to default indentation
`gg`, `=G` : got to the first line, then normalise the indentation of the whole file

###Folding
- - -
`zf5j` : fold 5 lines below (f=fold)
`zf5k` : fold 5 lines above (f=fold)
`zo` : open folded lines
`zc` : close open folded lines
`zd` : delete fold marker
`zf%` : create fold based on matching brackets
`zi` : invert all fold in the current file
`zC` : close every single fold from inner to outer
`zO` : open every single fold from outer to inner

###Macros
- - -
register is like a clipboard manager
`q` : start & stop macro recording
`qa` : write the recording on `a` slot
`:reg` : list registers
`@`*a* : execute *a*

###Bookmarks
- - -
`m`*[a-z]* : mark here as *[a-z]*
`''` : go back to previous mark/switch between two marks

###Files
- - -

###Search & Replace
- - -

`/` : search after the cursor
`?` : search before the cursor
`f` : search character

`:s` : `s`ubstitute/replace
`:s%/foo/bar/gci` : `s`ubstitute pattern(`foo`) with replacement(`bar`) in every line(`%`) and every occurence(`g`lobal), `c`onfirm each, `i`nsensitive case


###Visual Mode
- - -
`v` : enter visual mode
`V` : visual block mode (select by line)
`gv` : reselect previously selected area
`ggVG` : select all
`o` : to change the select direction upwards

###Buffers
- - -
`:ls` : list all buffers
`:bn` : go to the next file in buffers
`^`, `:bp`, `:b#` : go to the previous file in buffers
`:bf` : go to the first file in the buffers
`:bl` : go to the last file in the buffers
`:b12` : go to buffer inside slot 12
`:bd` : delete current buffer
`:bd12` : delete buffer inside slot 12

###Views
- - -
`:vs` : open current file in split window
`:sp` : open new split inside the current split
`ctrl + w` `l` : go to the left split (faster to use smart arrow)
`ctrl + w` `r` : go to the right split (faster to use smart arrow)
`ctrl + w` `L` : move current split to the right
`ctrl + w` `H` : move current split to the left
`ctrl + w` `J` : move current split to the down
`ctrl + w` `K` : move current split to the up
`ctrl + w` n`+` : increase the height of current split
`ctrl + w` n`-` : decrease the height of current split
`ctrl + w` n`>` : increase the width of current split
`ctrl + w` n`<` : decrease the width of current split
`ctrl + w` `=` : resize all split to the default
`:sbn` : open the buffer(n) in the new split
`:vert sbn` : open the buffer(n) in the new vertical split

###Tabs
- - -
`:tabs` : list all available tabs
`:tabe` : edit/open file in new tab
`gt` : go to the next tab
`gT` : go to the previous tab

###Options
- - -
`:colorschemes` : check the current color schemes
`:colo (tab)` : switch to other color schemes that are available

###Misc
- - -
///`ze` & `zs` : ???

###NERDTree
- - -
`ctrl + n`	 : toggle nerdtree
`I` : toggle hidden file display
`m` : open menu
- `a` : add a childnode
- `m` : move current node
- `d` : delete current node
- `c` : copy current node
- `M` : rename current node

###Ruby-Vim
- - -

###Rails-Vim
- - -