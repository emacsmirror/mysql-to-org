[![License GPL 3][badge-license]](http://www.gnu.org/licenses/gpl-3.0.txt)

## mysql-to-org-mode for emacs
Minor mode for emacs to output the results of mysql queries to org tables, with auto completion of table and column names and parameter replacement.

<p align="center">
<img src="https://raw.github.com/mallt/mysql-to-org-mode/master/mysql-to-org-mode.gif" alt="mysql-to-org-mode screencast"/>
</p>

## Installation
mysql-to-org is available as a MELPA package: <kbd>M-x</kbd> `package-install` <kbd>[RET]</kbd> `mysql-to-org` <kbd>[RET]</kbd>

## Customization
The mysql command and the mysql user can be changed through the variables `mysql-to-org-mysql-command` variable (defaults to `"mysql"`) and `mysql-to-org-mysql-user` (defaults to `"root"`).

## Usage
1. Activate the minor mode by pressing <kbd>M-x</kbd> `mysql-to-org-mode` or adding the mode as a hook to another mode, f.ex. `(add-hook 'php-mode-hook 'mysql-to-org-mode`).
2. On first activiation of the mode, you will be asked to enter a password to connect to mysql.
3. When the mode is active, the following commands are available:
  * <kbd>C-c C-m e</kbd> (`mysql-to-org-eval`): evaluate the mysql query inside the active region or current line.
  * <kbd>C-c C-m p</kbd> (`mysql-to-org-eval-string-at-point`): evaluate the string at point.
  * <kbd>C-c C-m s</kbd> (`mysql-to-org-scratch`): open a scratch buffer to evaluate mysql queries.
  * <kbd>C-c C-m 1</kbd> (`mysql-to-org-only-show-output-window`): only show the output window with the query results.
  * <kbd>C-c C-m r</kbd> (`mysql-to-org-reload-completion-candidates`): reload the completion candidates (f.ex. after changing the database schema).
4. If a query contains parameters, you will be asked to supply values for these parameters in the minibuffer to evaluate the query. The regexp to find parameters can be customized with the `mysql-to-org-parameter-regexp` variable.
5. All table names and column names are available for auto completion using the completion-at-point-functions.
6. Query results are available as org tables.


[badge-license]: https://img.shields.io/badge/license-GPL_3-green.svg
