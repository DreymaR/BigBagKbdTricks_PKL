DreymaR's Big Bag Of Keyboard Tricks - EPKL
===========================================

### [EPiKaL PortableKeyboardLayout][CmkPKL] for Windows, with layouts

![EPKL help image, for the Colemak-CAWS layout](./Layouts/Colemak/Cmk-eD_ISO_CurlAWideSym/Cmk-ISO-CAWS_s0_EPKL.png)

[Θώθ][ThothW] – What Is This?
-----------------------------
* This is the **Big Bag Of Tricks**, obviously! That is, my many layout mods and tweaks and bells and whistles. 
* It's mostly centered around the brilliant Colemak keyboard layout, with my own `[eD]` AltGr layers and dead keys,...
* ...**ergonomic mods** both for **Colemak**, the **Tarmak** learning layouts and **other layouts**,...
* ...and the incredibly useful **Extend** layers which work with any layout.
* This GitHub repository is home to the **EPiKaL PKL** layout program, with several improvements over the old PKL.
* Most of my Big Bag "tricks" are implemented for EPKL, as layouts and other files.
* Some non-EPKL BigBag stuff can be found in the Other folder.
* Info about DreymaR's Big Bag of keyboard trickery is mainly found on the Colemak forum:
    - The [**Big Bag main topic**][CmkBBT] with better explanations and links.
    - Daughter topics for implementations, including the [Big Bag for EPKL/Windows][CmkPKL] one.
  
These Aren't The Guides You're Looking For?
-------------------------------------------
EPKL can be complex and confusing for the newbie. So we're very happy to present to you:
**[EPKL For Dummies][EPKL4D]**, by master [TorbenGB](https://github.com/torbengb). Help me, Obi-Torben, you're my only hope!
If you find my info below and on the Big Bag pages too daunting and massive, do try it out.  ( のvの) c[_]  
  
Getting EPKL up and running
---------------------------
* Download a full copy of this repository or just its executable resources.
    - Under **[Release][GitRel] Assets**, there's a .ZIP file with the files needed to run EPKL. Unzip and run!
    - For the newest updated Git **commit** with source code, instead **[Download ZIP][GitCom]** from the green `Code` button.
    - For releases, the `EPKL.exe` binary is included. For commits, you must run `Compile_EPKL.bat` to produce it.
    - Note that some virus protection programs overreact to Autohotkey (AHK) code, especially using keyboard hooks.
* **FAST LANE:** If you simply want "vanilla Colemak" on a US/ANSI keyboard, just run EPKL.exe and type!
    - If you insist on having the Caps key as Backspace instead of the superior and wonderful Extend key...
    - ...in the [Layouts Default file][LayDef] find the first `;QWCLK = BACK` etc line and remove that semicolon.
* Run EPKL.exe inside its main folder in any way you like! Check its tray menu in the bottom right-hand corner.
* To choose a layout variant, select the **Layouts/Settings...** menu option. The EPKL Settings User Interface pops up.
* Choose a layout with your keyboard type, variant/locale and Curl/Angle/Wide etc preferences.
    - There are two main layout types: VK which only moves your keys, and eD which maps each shift state.
    - There are several premade Locale variants, if you need to type in other languages. Check out which variants exist.
    - There are several ergonomic variants, which you can read about in the Big Bag: Curl(DH), Angle, Wide, Sym etc.
* To use the chosen layout(s) and settings, select the Refresh EPKL menu option.
* By default, help images show up when modifiers are pressed. Change the `img_HideStates` setting from `0` to `-` to always show images.
* This image shows the EPKL tray menu. Right-click the `Co` icon in the lower right corner of your screen, if necessary via the 'Show hidden icons' caret.
  
    ![EPKL tray menu](./Other/Docs/EPKL_Tray-Menu.png)
  
More Know-How
-------------
* If you want to choose layouts manually, copy the Override_Example file to `EPKL_Layouts_Override.ini`.
    - There can be both [Layouts_Default][LayDef] and [Layouts_Override][LayOvr] files. Override entries take precedence.
* In your Layouts_Override file, activate the layout(s) you want by editing and/or uncommenting (remove initial semicolon).
    - There are KbdType (@K) and other abbreviations, but you could also type the path to a layout folder out in full.
    - The format is: `layout = ‹layout folder›:‹menu entry›,‹2nd layout folder›:‹2nd menu entry›` etc.
* The `EPKL_Layouts` .ini files hold layout choices. [EPKL_Settings][PklIni] holds general program settings.
* The `layout.ini` files hold layout settings and mappings. They often point to and augment a `BaseLayout` file.
* There's a "LayStack" for layout info priority. Mappings/settings at higher levels take precedence:
    - The [EPKL_Layouts_Default][LayDef] holds default and common settings/mappings
    - The [EPKL_Layouts_Override][LayOvr], if present, can hold overriding layout choices etc
    - The `BaseLayout` .ini file usually found under each layout type may define most of the layout
    - The `layout.ini` file in the chosen Layout folder gets the last word about remaps etc
    - Beyond this, specialized files may hold settings, info, Extend or DeadKey mappings etc. See below.
* In theory, you could put all the info needed for a whole layout into any one of the layout stack files.
  
**Tweakable parameters:**
The layouts and setup files may take a little tweaking to get what you want. There are several parameters:
* Colemak vs QWERTY vs what-have-you, obviously. Choose your main layout wisely!
    - This repo by default contains Colemak(-DH) and Tarmak layouts, but also QWERTY and Dvorak.
* Full/VK mappings: I've provided my own Colemak[eD] as well as 'VirtualKey' versions
    - The _VK_ layouts just move the keys of your installed OS layout around, without other changes
    - The _[eD]_ layouts have their own Shift/AltGr state mappings specified.
    - Actually, you may mix mapping types freely in any layout.
* ISO (European/World) vs ANSI (US) vs other keyboard types
    - ISO boards have a `VK_102` key between `Z` and `LShift`.
    - In ISO OS layouts, `OEM_` virtual key codes differ from ANSI ones. The boards send the same scan codes though.
    - Brazilian ABNT boards are like ISO, but have two more keys. These can be remapped by their scan codes.
    - JIS (Japanese) etc are not supported so far. Sorry. Gomen-nasai. ごめんなさい.    ᏊᵕꈊᵕᏊ
* Curl(DH), Angle and/or Wide ergonomic mods, moving some keys to more comfortable positions
    - Angle/Wide affect the "hard" key positions in the layout.ini file, usually both for Layout and Extend
    - Curl(DH) is Colemak/Tarmak/Dvorak specific and for the most part should not affect Extend
    - The Curl(DH) mod does insert D between C and V though. There's a remap to let Extend+V still be Paste
* Extend mappings, using for instance CapsLock as a modifier for nav/edit/multimedia/etc keys. It's awesome!!!
    - The Extend modifier may even double as a Tap-or-Mod key so that when you tap it, something else happens.
    - The most advanced way of using this may be the Mother-of-DeadKeys which allows really fancy "tap dances"!
    - Holding down Shift and/or AltGr while first holding or while tapping the Ext key affects which Ext layer you get.
* In EPKL_Layouts you can use shorthand (@#) for KbdType/CurlMod/ErgoMod etc, or set the layout folder path directly.
    - For Extend set an Extend file and a working Extend modifier. The latter needs to be mapped to a key.
    - My _eD_Extend mappings file is in the Files folder. Look inside it to learn more.
* In the layout folder(s) you've chosen, you may edit the layout.ini files further if required. See below.
    - Mod remaps, help image specifications, Extend key, key mappings etc can be set in the LayStack .ini files.
    - Many layouts use a BaseLayout. Most mappings may be there, so the top layout.ini only has to change a few keys.
* To learn more about remaps, see the [_eD_Remap.ini][MapIni] file. They can even turn Colemak into QWERTY (oh no...!).
* There's a file for named literals/PowerStrings. These are useable by layouts, Extend and dead keys.
* Also, a Dead Key file. DKs are mapped as @###. Pressing the key then a release glyph may produce something new!
    - There are help images for DKs, these can be very useful as they show what releases are in different shift states.
    - I haven't made images for all variants though, so there may be minor discrepancies.
* Layout folders aren't premade for every variant, board and mod combo, as there are so many of them. See below.
* The Layout/Settings dialog can change layout, key mappings and a selection of settings. Here's a mapping example:
  
    ![EPKL settings dialog](./Other/Docs/EPKL_Settings-UI.png)
  
**Hotkeys found in the EPKL_Settings file:**
* Ctrl+Shift+1 – Display/hide the help image
* Ctrl+Shift+2 – Switch between the layouts specified in the Layouts file(s)
* Ctrl+Shift+3 – Suspend EPKL; hit again to re-activate. It may also be Ctrl+Shift+`.
* Ctrl+Shift+4 – Exit EPKL
* Ctrl+Shift+5 – Refresh EPKL, if it gets stuck or something
* Ctrl+Shift+6 – Show the Layouts/Settings... dialog
* Ctrl+Shift+7 – Zoom the help image in/out, to see it better or get it out of the way
* Ctrl+Shift+8 – Toggle help image transparency
* Ctrl+Shift+9 – Move the help image between positions, as by mouseover
* Ctrl+Shift+0 – Show info about the active window; useful for setting suspending apps
  
**Short EPKL Glossary**
* **Extend** is a layer switch, by default the CapsLock key, giving easy access to navigation and NumPad etc layers
* **Multi-Extend** means you'll get another Extend layer if you hold down, say, RShift and/or RAlt when pressing Extend
    - After selecting an Extend layer this way, keep only the Extend key pressed down to maintain it
* A sticky modifier or **OSM** (One-Shot Mod) is when you can tap a mod and then another key shortly thereafter
    - There's a setting in the Settings file for how quickly the OSM times out, in milliseconds
* **ToM** (Tap-or-Mod) is a dual-role key, working as a mod when held down and a normal key when tapped
* **DK** is a dead key. You tap it then another key, there's no timer. Most of my DKs are on `{AltGr+‹symbol›}`.
    - DK sequence: You can tap several DKs to get new symbols (example: `{AltGr+=,=}` gives `≡`; `AltGr+{/,=}` then `=` gives `≢`)
    - DK chaining: One DK can release to another. This is not implemented in EPKL yet
    - **MoDK** (Mother-of-DKs) is a ToM key (here, on **tap-Extend**) that leads to lots of cool DKs
* The **LayStack** is a stack of files that may hold layout definitions: Layouts_Default, Layouts_Override, BaseLayout and Layout.
* **PowerStrings** are shortcuts to text strings. These may be multiline, and may contain AutoHotKey syntax.
    - As an Example, try Extend+End in a text editor. It should produce an editable 'Yours truly' message footer.
* **Remaps** are cycles of keys swapping places. This allows you turn one layout definition into another.
    - These can be in the LayStack files for quick layout tweaks, or in a dedicated [Remap file][MapIni].
  
**Techy tips for EPKL:**
* EPKL is Viper approved! One of the fastest typists in the world has tested it and found it responsive enough.
    - If you type above around 150 Words Per Minute, some pace smoothing may occur. This shouldn't be a problem, mostly.
* EPKL, being portable, doesn't need an install with admin rights to work. You must still be allowed to run programs.  
* I usually put a shortcut to EPKL.exe in my [Start Menu "Startup" folder][StrtUp] so it starts on logon, per user.
* EPKL can also easily be used with the [PortableApps.com][PrtApp] menu by putting its folder in a `C:\PortableApps` folder.
    - If the PortableApps menu is run on logon it can start up EPKL for you too.
* Look in the various .ini files under Files and Layouts if you're interested! Much is explained there.
* See my examples in the Extend file for some advanced mappings! These may be used in layouts and dead keys too.
* EPKL uses both .ini and source files that may be UTF-8 Unicode encoded.
* EPKL allows end-of-line comments (whitespace-semicolon) in .ini files, the old PKL only allowed them in layout entries.
* Running EPKL with other (AutoHotkey) key mapping scripts may get confusing if there is so-called _hook competition_.
  
Key mappings
------------
Most of my layouts have a base layout defined; their layout section may then change some keys. You can add key definitions following this pattern.
  
Here are some full shiftstate mappings with a legend:
```
; SC  = VK      CS    S0    S1    S2    S6    S7    ; comments
QW_O  = Y       1     y     Y     --    ›     »     ; SC018: QW oO
QW_P  = vc_SC   0     ;     :     --    @0a8  …     ; SC019: QW pP - dk_umlaut (ANS/ISO_1/3)
```
Where:
* SC & VK: [Scan code ("hard code")][SCMSDN] & Virtual Key Code [("key name")][VKCAHK]; also see my [Key Code Table][KeyTab].
    - For SC, you could use an AHK key name instead. For VK you need the Windows VK names (or KLM codes).
    - Instead of the technical SC or VK you may use my more intuitive KLM codes. See the [Remap file][MapIni].
    - _Example:_ The above SC are for the `O` and `P` keys; these are mapped to their Colemak equivalents `Y` and `;`.
    - The `OEM_#` VK names are ISO/ANSI keyboard type specific. For these, it's much better to use KLM vc_## codes.
    - _Example:_ The KLM code `vc_SC` is the semicolon key, which is VK `OEM_1` for ANSI but `OEM_3` for ISO keyboards.
    - If the VK entry is VK/ModName, that key is Tap-or-Mod. If tapped it's the VKey, if held down it's the modifier.
    - The VK code may be an AHK key name. For modifiers you may use only the first letters, so LSh -> LShift etc.
* CS: Cap state. Default 0; +1 if S1 is the capitalized version of S0 (that is, CapsLock acts as Shift for it); +4 for S6/S7.
    - _Example:_ For the `Y` key above, CS = 1 because `Y` is a capital `y`. For `OEM_1`, CS = 0 because `:` isn't a capital `;`.
* S#: Modifier states for the key. S0/S1:Unmodified/+Shift, S2:Ctrl (rarely used), S6/S7:AltGr/+Shift.
    - _Example:_ Shift+AltGr+`y` sends the `»` glyph. AltGr+`;` has the special entry `@0a8` (umlaut deadkey).
* Special prefix-entry syntax (can be used for layouts, Extend and dead key entries; two possibilities for each prefix):
    - → | %‹entry› : Send a literal string/ligature by the SendInput {Raw}‹entry› method (default)
    - § | $‹entry› : Send a literal string/ligature by the SendMessage ‹entry› method
    - α | *‹entry› : Send ‹entry› directly, allowing AHK syntax (!+^# are modifiers, {} key names)
    - β | =‹entry› : Send {Blind}‹entry›, keeping the current modifier state
    - « | ~‹entry› : Send the 4-digit hex Unicode point U+<entry>
    - Ð | @‹entry› : Send the current layout's dead key named ‹entry›
    - ¶ | &‹entry› : Send the current layout's powerstring named ‹entry›; some are abbreviations like &Esc, &Tab...
  
Here are some VirtualKey/VKey and Modifier/Mod mappings. Any layout may contain all types of mappings.
```
QW_J    = N         VKey            ; QW jJ  -> nN, a simple VK remapping
RWin    = BACK      VirtualKey      ; RWin   -> Backspace
RShift  = LShift    Modifier        ; RShift -> LShift, so it works with LShift hotkeys
SC149   = NEXT      VKey            ; PgUp   -> PgDn, using ScanCode and VK name (the old way)
QWPGU   = vcPGD     VKey            ; PgUp   -> PgDn, this time with my more intuitive KLM codes
```
Entries are any-whitespace delimited.
  
Advanced Extending
------------------
Here are some sample Extend key mappings:
```
QWCLK   = Extend    Modifier        ; Caps   -> The Extend modifier (see the Big Bag)
QWCLK   = BACK/Ext  VirtualKey      ; Caps   -> Tap-or-Mod: Backspace if tapped, Extend if held
QWCLK   = BACK/Ext  0   @ex0 @ex1 *#. @ex6 @ex7 ; Mother-of-DeadKeys (MoDK) on tap, Extend on hold
```
* These mappings merit explanation. Extend is a most marvelous beast, so don't be daunted now! ฅ(=ʘᆽʘ=)ฅ
* The above Extend modifier mappings may be in any LayStack .ini file, such as [Layouts_Default][LayDef]
* Holding designated modifiers, RShift and/or RAlt by default (specified in the [Settings][PklIni]), chooses Extend layers.
    - So, e.g., holding the Ext1 mod (RAlt) then the Ext key (Caps) activates the Extend2 layer (NumPad).
* After selecting your Extend layer, you hold down only the Extend key (Caps by default) and start using Extend!
* Extend layers (like Ext3/Ext4) can be set as one-shot so they fall back to another layer after each use.
    - This lets you for instance release a string then keep editing. But dead keys are better for that, see below.
* Setting the Extend key as a Tap-or-Mod (ToM) key as above lets you tap it for, e.g., Backspace or hold for Extend.
* Mother-of-DeadKeys (MoDK) is the most powerful option. Tapping Extend activates a dead key depending on shift state!
    - Tapping Ext alone or with Shift/AltGr activates the dead keys "ex0/1/6/7". See the DeadKeys.ini file!
    - In my default example, Ext-tap alone lets you activate symbols and commands easily.
    - Shift+Ext-tap activates a kaomoji DK, similar to Ext3 but you don't have to hold down the Ext key! d( ^◇^)b
    - Another advantage of DK layers over Extend layers is that you can make entries for any release char.
    - So, e.g., Ext3 has one kitty kaomoji (=^･ω･^=)丿 but dk_Ext_Kaomoji has one for k and one for K. (=ΦωΦ=)ʃ
    - "Tap-dance" {Shift,Ext,<key>} quickly using Sticky Shift, for a kaomoji. Wait before <key> for another.
    - Holding Ctrl then tapping Ext sends Win+Period, opening the Emoji picker.
    - AltGr+Ext-tap holds some commands to avoid hand contortion. Example: {AltGr+Ext,T} for Task Manager.
  
Layout variant tutorial
-----------------------
You can make your own version of, say, a locale layout with a certain (non-)ergonomic variant:
* Determine which keyboard type (ISO/ANS), ergo mod and if applicable, existing locale you want to start from.
* Determine whether you want to just move keys around by VirtualKey mappings or map all their shift states like Colemak-eD does.
* Copy/Paste a promising layout folder and rename the result to what you want.
    - In this example we'll make a German (De) Colemak[eD] with only the ISO-Angle mod instead of the provided CurlAngleWide.
    - Thus, copy `Cmk-eD-De_ISO_CurlAWide` in the [Colemak](./Layouts/Colemak) folder and rename the copy to `Cmk-eD-De_ISO_Angle`.
    - Instead of 'De' you could choose any locale tag you like such as 'MeinDe' to set it apart.
* In that folder's layout.ini file, edit the remap fields to represent the new settings.
    - Here, change `mapSC_layout = Cmk-CAW_@K` to `mapSC_layout = Angle_@K` (`@K` is shorthand for ISO/ANS).
    - Some Extend layers like the main one use "hard" or positional remaps, which observe most ergo mods but not letter placements.
    - Here, `mapSC_extend = Angle_@K` too since Angle is a "hard" ergo mod. If using Curl-DH, you can move Ctrl+V by adding 'V-B,' in front.
* Change any key mappings you want to tweak.
    - The keys are mapped by their native Scan Codes (SC), so, e.g., SC02C is the QWERTY/Colemak Z key even if it's moved around later.
    - See the next section to learn more about key mapping syntax.
    - The mappings in the De layout are okay as they are, but let's say we want to swap V and Ö (OEM_102) for the sake of example.
    - In the `[layout]` section of layout.ini are the keys that are changed from the BaseLayout. OEM_102 is there, state 0/1 mapped to ö/Ö.
    - To find the V key, see the `baseLayout = Colemak\BaseLayout_Cmk-eD` line and open that file. There's the V key, SC02f.
    - Now, copy the V and OEM_102 keys to your layout.ini `[layout]` section so they'll override the baseLayout, and swap their SC### codes.
    - Alternatively, you could just edit the mappings for the affected shift states of the two keys. Use any white space between entries.
* Now, if your `EPKL_Layouts` .ini Type/Locale/Kbd/Curl/Ergo/Other settings are right you should get the variant you wanted.
    - Here, set LayType/LayVari/KbdType/CurlMod/ErgoMod/OthrMod to eD/De/ISO/--/Angle/-- respectively (or use 'MeinDe' if you went with that).
    - If you prefer to use another existing layout line in the file, comment out the `layout = ` line with `;` and activate another.
    - You can also write the `layout = LayoutFolder:DisplayedName` entry directly instead, using the folder path starting from `Layouts\`.
* After making layout changes, refresh EPKL with the Ctrl+Shift+5 hotkey. If that doesn't work, quit and restart EPKL.
* To get relevant help images without generating them with Inkscape:
    - Check around in the eD layout folders. Maybe there's something that works for you there despite a few minor differences?
    - Here, you might either keep the current De_ISO_CurlAWide settings to see the German special signs without making new images, or...
    - ...edit the image settings, replacing AWide/CAWide/CAngle with 'Angle' to get normal ISO_Angle images without German letters, or...
    - ...make new help images in an image editor by copying and combining from the ones you need. I use Gimp for such tasks.
* If you do want to generate a set of help images from your layout you must get Inkscape and run the EPKL Help Image Generator (HIG).
    - To see the "Create help images..." menu option, advancedMode must be on in [EPKL_Settings][PklIni].
    - The HIG will make images for the currently active layout.
    - You can download Inkscape for instance from PortableApps.com, and point to it in the [ImgGen_Settings](./Files/ImgGenerator/EPKL_ImgGen_Settings.ini) file.
    - By default, the HIG looks for Inkscape in `C:\PortableApps\InkscapePortable\InkscapePortable.exe`, so you could just put it there.
    - I recommend making state images only at first, since a full set of about 80 dead key images takes a _long_ time!
  
  
KNOWN ISSUES:
-------------
* ISO VK layouts may not send the right OEM_# key VK codes for several ISO locales. Known affected locales: UK, De, Fr, Be...
  
  
DONE/TODO:
----------
For more info about past and future EPKL history, see the **[EPKL Advanced README][EPKLRM]** in the Source folder.
  
  
Credits/sources
---------------
#### ~ The original [PKL][PKLGit] written by [Farkas Máté in 2008][PKLSFo] using [AutoHotkey][PKLAHK]
#### ~ [EPKL][CmkPKL], formerly PKL[edition DreymaR] by DreymaR, 2017-
#### ~ Big thanks to the AutoHotkey people, Vortex(vVv), the Colemak Forum crowd and all other contributors.
  
_Finally, to all of you: Best of luck using EPKL!_
_Øystein "DreymaR" Gadmar, 2020_

[PKLGit]: https://github.com/Portable-Keyboard-Layout/Portable-Keyboard-Layout/ (Old PKL on GitHub)
[PKLSFo]: https://sourceforge.net/projects/pkl/ (Old PKL on SourceForge)
[PKLAHK]: https://autohotkey.com/board/topic/25991-portable-keyboard-layout/ (Old PKL on the AutoHotkey forums)
[AHKHom]: https://autohotkey.com/ (AutoHotkey main page)
[CmkBBT]: https://forum.colemak.com/topic/2315-dreymars-big-bag-of-keyboard-tricks-main-topic/ (BigBagOfKbdTrix on the Colemak forums)
[CmkPKL]: https://forum.colemak.com/topic/1467-dreymars-big-bag-of-keyboard-tricks-pklwindows-edition/ (BigBag-PKL on the Colemak forums)
[StrtUp]: https://support.microsoft.com/en-us/help/4558286/windows-10-add-an-app-to-run-automatically-at-startup (Windows Startup folder)
[PrtApp]: https://portableapps.com/ (PortableApps.com)
[SCMSDN]: https://msdn.microsoft.com/en-us/library/aa299374(v=vs.60).aspx (Scan code list at MSDN)
[VKCAHK]: https://autohotkey.com/docs/KeyList.htm (Virtual key list in the AHK docs)
[GitRel]: https://github.com/DreymaR/BigBagKbdTrixPKL/releases/latest (Latest EPKL release)
[GitCom]: https://github.com/DreymaR/BigBagKbdTrixPKL/archive/master.zip (Latest EPKL commit download)
[EPKLRM]: https://github.com/DreymaR/BigBagKbdTrixPKL/tree/master/Source (EPKL advanced README)
[EPKL4D]: https://docs.google.com/document/d/1G0chfgAwdf8cF-uoPEUw0CWwKXW9-uuQiNLbYlnYurs (EPKL For Dummies, by Torben G.B.)
[ThothW]: https://en.wikipedia.org/wiki/Thoth (Thoth: Egyptian god of wisdom and writing)
[KeyTab]: ./Other/KeyCodeTable.txt (KeyCodeTable.txt)
[LayOvr]: ./EPKL_Layouts_Override_Example.ini (EPKL_Layouts_Override example file)
[LayDef]: ./EPKL_Layouts_Default.ini (EPKL_Layouts_Default file)
[PklIni]: ./EPKL_Settings_Default.ini (EPKL Settings file)
[MapIni]: ./Files/_eD_Remap.ini (EPKL Remap file)
