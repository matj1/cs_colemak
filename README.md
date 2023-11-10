# Colemak for Czech language

Colemak layout modified so Czech letters are accessible more easily.

Available for XKB on Linux and for Windows. The Windows version is not updated because I don't have a Windows system where I could test it.

I placed Czech letters with diacritics to AltGr layer, as close to their corresponding letters without diacritics (original letters). I moved some characters to make space for Czech letters. I replaced Englich quotation marks with Czech quotation marks. I also added some characters to reduce total amount of tildes and made it a bit easier to type non-breaking space. I commented out the line mapping Caps Lock to Backspace because I don't use it, but everyone who wants to use it can uncomment it.

## Important changes

* `ý` is under `y` on AltGr layer.

* All letters with caron are under their original letters except `ď`, `Ď`, `ť`, `Ť`, `ň`, `Ň` and `ě`, `Ě`. `ě` and `Ě` are under `n`, which is next to `e`.

* English quotation marks are replaced by Czech quotation marks. English right quotation mark is under `;`, so it's under English left quotation mark (Czech right quotation mark).

* I added some characters that sometimes come in handy, namely `…`, `ſ`, `⟨` and `⟩`, and others, also to reduce total number of tildes.

* To AltGr + Space, I assigned non-breaking space.

## Layout:

    `~~~  1!¡¹  2@º²  3#ª³  4$¢£  5%€¥  6^ħĦ  7&ðÐ  8*þÞ  9(„‚  0)“‘  -_–—  =+×÷

          qQäÄ  wWåÅ  fFßẞ  pPæÆ  gGœŒ  jJđĐ  lLůŮ  uUúÚ  yYýÝ  ;:”’  [{«‹  ]}»›

          aAáÁ  rRřŘ  sSšŠ  tT´`  dD¨˝  hHˇ/  nNěĚ  eEéÉ  iIíÍ  oOóÓ  '"õÕ  \|…§

    -_–—  zZžŽ  xX^ſ  cCčČ  vVøØ  bB˘~  kK°~  mM¯˛  ,<¸⟨  .>˙⟩  /?¿~

## Installation

### XKB

I apologise for the mess. I was tweaking the installation over time, so the variants do not correspond exactly. The single-user installation is the newest and most robust method, the system-wide method comprises hacks.

#### Single-user

This is according to [Who-T – User-specific XKB configuration - putting it all together](http://who-t.blogspot.com/2020/09/user-specific-xkb-configuration-putting.html).

This method is recommended because the layout will not be removed by an update. Also, it works in GNOME.

If you do not have the directory `~/.config/xkb`, just copy [`xkb`](xkb) into `~/.config`. (If your `$XDG_CONFIG_HOME` is different than `~/.config`, adjust the instruction accordingly.)

If you have already had the directory `~/.config/xkb`, incorporate [`xkb`](xkb) to your local `xkb`.

#### System-wide

1. As root, to `/usr/share/X11/xkb/rules/xorg.lst`, under line `! variant`, add `  colemak         cz: Czech (Colemak, Czech letters)`.

2.  As root, add content of [cs_colemak](cs_colemak) at the end of `/usr/share/X11/xkb/symbols/cz`.

Additional steps are needed to integrate the layout into GNOME. Follow [this guide](https://blog.stigok.com/2020/10/27/from-x11-xmodmap-to-wayland-xkb-custom-keyboard-layout.html) to add the layout to Gnome. It works in Wayland too. If the link doesn't work, read [its snapshot on Wayback Machine](https://web.archive.org/web/20210717104133/https://blog.stigok.com/2020/10/27/from-x11-xmodmap-to-wayland-xkb-custom-keyboard-layout.html).

##### Alternative

To mitigate the risk that this layout will be removed during an update of X.org, the layout can be installed separately from other Czech layouts. If the language code for the Czech Colemak is “czc”, then the line in `xorg.lst` then should be modified to having `czc` instead of `cz` and [cs_colemak](cs_colemak) should be copied to its own file `/usr/share/X11/xkb/symbols/czc` and the first line should have `default ` added to the beginning (`default partial alphanumeric_keys`).

### Windows

Compile [cs_colemak.klc](cs_colemak.klc) in Microsoft [Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339) and run `setup.exe` from the output files.

The layout is added as a Czech variant called Colemak opt. for Czech.
