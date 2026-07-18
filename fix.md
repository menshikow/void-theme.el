 Rename void-theme.el → void-themes.el in both ~/dev/void-theme.el/ and ~/.dotfiles/ (the dotfiles copy can stay as a reference; the MELPA files are in ~/dev/void-theme.el/)
- Change summary line to "Dark and light monochrome color themes"
- Change (provide 'void-theme) → (provide 'void-themes)
- Update all references (README, init.el if needed)
2. Fix dark-void-theme.el (both repos):
- L1: ;;; dark-void-theme.el --- Dark void colorscheme
- Add ;;; Code: after ;;; Commentary:
- L36: (deftheme dark-void "Dark monochrome theme for Emacs.")
- End: move ))) to same line as preceding face
3. Fix light-void-theme.el (both repos):
- Same edits as dark-void, mirrored
4. Update README.md in ~/dev/void-theme.el/:
- Instructions: (require 'void-themes) then (load-theme 'dark-void t) etc.
5. Update ~/.dotfiles/emacs/init.el:
- If it references void-theme (as a require), update to void-themes
6. Verify:
- emacs --batch -f batch-byte-compile on all 3 files
- package-lint on all 3 files
- checkdoc on all 3 files
