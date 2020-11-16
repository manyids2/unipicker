# unipicker - fork

## Want to add options for history, most used, shortcuts

A CLI utility for searching unicode characeters by description and optionally
copying them to clipboard.

## Usage

<!-- BEGIN-EVAL ./unipicker --help | sed -e '1i ```sh' -e '$a ```' -->
```sh
Select unicode character by description

Usage: unipicker [--command cmd] [--copy-command cmd ] [--copy] [--list]

Arguments:
  --command       Overrides default select command
  --copy-command  Override copy to clipboard command, implies --copy
  --copy          Copy to clipboard
  --list          Only list the symbols, do not select or copy

Variables:

  UNIPICKER_SELECT_COMMAND  Command to use for selecting (= fzf)
  UNIPICKER_COPY_COMMAND    Command to use for copying (= pbcopy)
  UNIPICKER_SYMBOLS_FILE    Location of symbols (= /usr/local/share/unipicker/symbols)
```
<!-- END-EVAL -->

## Configuration

You can configure both the selector command and the copy command. There are two
main configuration files which are sourced by unipicker:

- `/etc/unipickerrc`
- `${HOME}/.unipickerrc`

The default settings can be seen in the `unipickerrc` file. The default copy
command will be determined based on the OS, but it can be overridden.

The command line arguments can be used to override the variables set.

## Examples

Using `rofi` instead of `fzf`:

```bash
unipicker --command "rofi -dmenu"
```

Using a different clipboard command

```bash
unipicker --copy-command pbcopy
```

## License

[MIT](LICENSE)
