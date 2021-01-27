---
Title: macOS Terminal Proxy Setup
Format: post
Tags:
	- macOS
	- proxy
---

# macOS Terminal Proxy Setup

In order to speed up utilities used in Terminal, such as 'Homebrew' and 'Macports', we need to make the Terminal go through proxy. This is a note illustrating how to set up proxy setting in macOS terminal.

## Written into ~/.bashrc or ~/.zshrc

1. Using http or https proxy
	``` bash
	export http_proxy="http://proxyAddress:listening port"
	export https_proxy="http://proxyAddress:listening port"
	```

2. Using socks5 proxy

   ``` bash
   export http_proxy="socks5://proxyAddress:listening port"
   export https_proxy="socks5://proxyAddress:listening port"
   ```

3. Or just set *ALL_PROXY* using one protocol 

   ``` zsh
   export ALL_PORXY="socks5://proxyAddress:listening port"
   # or
   export ALL_PROXY="http://proxyAddress:listening port"
   ```

This is a permanent way to make your terminal use proxy all the time.

## Using alias to set up proxy config

When u want terminal to use proxy:

```bash
alias setproxy="export ALL_PROXY=socks5://proxyAddress:listening port"
alias unsetproxy='unset ALL_PROXY'
```

This method only applied to current terminal session, after u close it, it will no longer take effect until you *setproxy* again.