# Colemak for Czech language

Colemak layout modified so Czech letters are accessible more easily.

Available for X keyboard extension and Windows. The Windows version does't have caps-lock working as a backspace

I placed Czech letters with diacritics to AltGr layer, as close to their corresponding letters without diacritics (original letters). I moved some characters to make space for Czech letters. I replaced Englich quotation marks with Czech quotation marks. I also added some characters to reduce total amount of tildes and made it a bit easier to type non-breaking space.

## Important changes

* `ý` is under `y` on AltGr layer.

* All letters with caron are under their original letters except `ď`, `Ď`, `ť`, `Ť`, `ň`, `Ň` and `ě`, `Ě`. `ě` and `Ě` are under `n`, which is next to `e`.

* English quotation marks are replaced by Czech quotation marks. English right quotation mark is under `;`, so it's under English left quotation mark (Czech right quotation mark).

* I added some characters that sometimes come in handy, namely `…`, `ſ`, `⟨` and `⟩`, and others, also to reduce total number of tildes.

* To AltGr + Space, I assigned non-breaking space.

## Layout:

    `~~~  1!¡¹  2@º²  3#ª³  4$¢£  5%€¥  6^ħĦ  7&ðÐ  8*þÞ  9(„‚  0)“‘  -_–—  =+×÷

          qQäÄ  wWåÅ  fFßẞ  pPæÆ  gGœŒ  jJđĐ  lLůŮ  uUúÚ  yYýÝ  ;:”’  [{«‹  ]}»›

          aAáÁ  rRřŘ  sSšŠ  tT´`  dD¨˝  hHˇ/  nNěĚ  eEéÉ  iIíÍ  oOóÓ  '"õÕ  \|…~

    -_–—  zZžŽ  xX^ſ  cCčČ  vVøØ  bB˘~  kK°~  mM¯˛  ,<¸⟨  .>˙⟩  /?¿~

## Instalation

### XKB

1. As root, to `/usr/share/X11/xkb/rules/xorg.lst`, under line `! variant`, add `  colemak         cz: Czech (Colemak, Czech letters)`.

2.  As root, add content of [cs_colemak](cs_colemak) at the end of `/usr/share/X11/xkb/symbols/cz`.

Additional steps are needed to integrate the layout into Gnome, I don't know which ones exactly. See my [comment on Reddit](https://www.reddit.com/r/gnome/comments/b5o6tx/add_custom_keyboard_layout_to_gnome/eju2mm6/?context=8&depth=9).

I recommend creating another symbols file and adding this layout there. I did this by copying `/usr/share/X11/xkb/symbols/cz` and deleting all other variants from the file. This way the layout won't be deleted when Xorg updates.

The layout is added as variant colemak of the keyboard layout, which symbols file it's in (cz if only steps 1 and 2 were folowed in this section).

#### Alternative

To mitigate the risk that this layout will be removed during an update of X.org, the layout can be installed separately from other Czech layouts. If the language code for the Czech Colemak is “czc”, then the line in `xorg.lst` then should be modified to having `czc` instead of `cz` and [cs_colemak](cs_colemak) should be copied to its own file `/usr/share/X11/xkb/symbols/czc` and the first line should have `default ` added to the beginning (`default partial alphanumeric_keys`).

### Windows

Compile [cs_colemak.klc](cs_colemak.klc) in Microsoft [Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339) and run `setup.exe` from the output files.

The layout is added as a Czech variant called Colemak opt. for Czech.
