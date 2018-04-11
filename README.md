# Colemak for Czech language

Colemak layout modified so Czech letters are accessible more easily.

Available for Linux distros only, I had the layout also For Windows, but it's gone now because I uninstalled Windows.

I placed Czech letters with diacritics to AltGr layer, as close to their corresponding letters without diacritics (original letters). I moved some characters to make space for Czech letters. I replaced Englich quotation marks with Czech quotation marks. I also added some characters to reduce total amount of tildes and made it a bit easier to type non-breaking space.

## Important changes

* `ý` is under `y` on AltGr layer.

* All letters with caron are under their original letters except `ď`, `Ď`, `ť`, `Ť`, `ň`, `Ň` and `ě`, `Ě`. `ě` and `Ě` are under `n`, which is next to `e`.

* English quotation marks are replaced by Czech quotation marks. English right quotation mark is under `;`, so it's under English left quotation mark (Czech right quotation mark).

* I added some characters that sometimes come in handy, namely `…`, `〈` and `〉`, also to reduce total number of tildes.

* To AltGr + Space, I assigned non-breaking space.

## Layout:

    `~~~  1!¡¹  2@º²  3#ª³  4$¢£  5%€¥  6^ħĦ  7&ðÐ  8*þÞ  9(„‚  0)“‘  -_–—  =+×÷
    
          qQäÄ  wWåÅ  fFãÃ  pPæÆ  gGœŒ  jJđĐ  lLůŮ  uUúÚ  yYýÝ  ;:”’  [{«‹  ]}»›
    
          aAáÁ  rRřŘ  sSšŠ  tT´`  dD¨˝  hHˇ~  nNěĚ  eEéÉ  iIíÍ  oOóÓ  '"õÕ  \|…~
    
    -_–—  zZžŽ  xX^~  cCčČ  vVøØ  bB˘~  kK°~  mM¯˛  ,<¸〈  .>˙〉  /?¿~

## Instalation

This is how to install the layout on my system (Arch in 2017), so you may have to search for the xkb directory somwhere else in `/usr` or `/etc`.

1. As root, to `/usr/share/X11/xkb/rules/xorg.lst`, under line `! variant`, add  
      ``` colemak cz: Czech (Colemak, Czech letters)```.
       
2.  As root, add content of [cs_colemak](cs_colemak) at the end of `/usr/share/X11/xkb/symbols/cz`.

3. Restart X.Org.
