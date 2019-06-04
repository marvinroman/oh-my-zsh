# gpg
Helpful GPG Aliases 

## Install
To use it, add gpg to the plugins array of your zshrc file:
```
plugins=(... gpg)
```

## Aliases
Alias | Command | Use | Description
--- | --- | --- | ---
`gpglk` | `gpg --list-secret-key --keyid-format LONG` | `gpglk [email]` | Prints out secret key in long format