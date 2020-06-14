Spacemacs
==========


internal archive
  command: ``org-toggle-archive-tag (, s a)``


emacs cannot toggle input method
  - export LC_CTYPE=zh_CN.UTF-8


emacs follow mode
  - https://stackoverflow.com/questions/970292/emacs-multiple-columns-one-buffer
  - just ``follow mode`` with more than one window


shortcuts
  - X: delete backward
  - ): forward sentence
  - (: backward sentence
  - g (h/j/k/l): move backward/down/up/forward
  - narrow to xxx: , s n/N  / C-x n b / C-x n e


scroll
  - ctrl f/b: scroll page down/up
  - ctrl d/u: scroll half page down/up
  - space N: scroll transient state
  - space N f: scroll down one page
  - space N b: scroll up one page
  - space N d: scroll down half page
  - space N u: scroll up half page


dired mode
  - ``^``: go-up-directory


copy path
  - ``space f y y``: file
  - ``space f y d``: directory


internal link
  - ``<<code>>``: anchor
  - ``[[code]]``: jump to anchor. this is a link


eval lisp
  - ``M-:``: Read a single Emacs Lisp expression in the minibuffer, evaluate it, and print the value in the echo area. ``eval-expression``
  - ``c-x c-e``: Evaluate the Emacs Lisp expression before point, and print the value in the echo area. ``eval-last-sexp``


fringe-mode
  - ``(fringe-mode 4)``: make both fringes 4 pixels wide
  - ``(fringe-mode '(4 0)``: make the left fringe 4 pixels wide and the right disapper
  - ``(fringe-mode nil)``: restore the default size


treemacs workplace
  - concept: a workplace can have one or more projects. workplace belongs to treemacs
  - ``treemacs-edit-workspace``: define your workplace and its associated projects
  - ``treemacs-finish-edit``: submit workplaces edit
  - ``treemacs-switch-workspace``: switch workspace
  - treemacs buffer shortcuts

    - ``?`` : show all shortcuts
    - ``c f``: create file
    - ``c d``: create directory


bookmark
  - ``C-x r m``: bookmark-set
  - ``C-x r b``: bookmark-jump
  - ``C-x r l``: bookmark-list
  - ``M-x bookmark-delete``: delete bookmark by name


window dedication: ``space w t``


bind key
  - `spacemacs-how-to-define-a-new-key-binding-with-a-leading-spc <https://stackoverflow.com/questions/46777840/spacemacs-how-to-define-a-new-key-binding-with-a-leading-spc>`_
  - A more complete answer, is to first declare a prefix, and then set leader keys. Using "o" as a prefix is a good idea, as it is guaranteed to be available for customization. Other prefixes might be used by different layers.

  ::

    (spacemacs/declare-prefix "o" "customize")
    (spacemacs/set-leader-keys "os" 'treemacs-switch-workspace)

    ;; org-ids
    (spacemacs/declare-prefix "od" "id")
    (spacemacs/set-leader-keys "odc" 'org-id-copy)
    (spacemacs/set-leader-keys "odu" 'org-id-update-id-locations)

error: org-preserve-local-variables
  - https://www.cnblogs.com/jiftle/p/10317493.html
  - method: 

  ::

     cd ~/.emacs.d/elpa
     find org*/*.elc print0 | xargs -0 rm
     (in spacemacs) spacemacs/recompile-elpa


evil-move-beyond-eol: move cursor beyound eol

end of file
