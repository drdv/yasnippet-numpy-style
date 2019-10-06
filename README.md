yasnippet-numpy-style
=====================

Minor tweaks of the code in
[yasnippet-numpy-style](https://github.com/marubu/yasnippet-numpy-style).

- One way of getting the snippets automatically when installing `elpy` (there
  might be a better way: probably something using `:ensure-system-package`):

```
(use-package elpy
  :ensure t
  :after python
  :config
  ;; ... possibly many other configurations ...
  (let ((dir (concat (file-name-directory
		      (locate-library "elpy"))
		     "snippets/python-mode/"))
	(github-raw "https://raw.githubusercontent.com/drdv/yasnippet-numpy-style/master/"))
    (if (not (file-exists-p (concat dir "param_")))
	(dolist (snippet '("def_" "param_"))
	  (shell-command (concat "wget -P " dir " " github-raw snippet))))))
```
