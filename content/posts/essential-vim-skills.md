---
author: "Milad"
title: "My Essential Vim Keybinds and Commands"
date: "2024-11-19"
description: "Run-down of my most used Vim (Neovim) skills"
FAtags: ["vim"]
FAcategories: [""]
FAseries: ["Themes Guide"]
aliases: ["migrate-from-jekyl"]
ShowToc: true
TocOpen: true
weight: 2
---


This blog post contains the most useful Vim keybinds. You'll also find the most useful Neovim command-mode tricks. All of this has been gathered from my personal experience tinkering with Vim.  
Note: this post skips over the very basic commands. 

<!--more-->
# Keybinds
### Store and Load Registers
Vim can store registers that contain blocks of text you have highlighted in visual mode. 


**Store Selected to Register:** ```"<character>y```  
**Paste from Register:** ```"<character>p```  
*(\<character> is a letter or number, used as a register)*

This can be useful for storing boilerplate code.


### Autofill
Vim can autofill in two ways:  

Searches the rest of the file for a word(s) that would complete  
**Complete Word:** ```CTRL-p```  

While in Insert-Mode, copy the above character  
**Copy Character:** ```CTRL-y```  


First method is highly useful. Second is kinda just for fun.


### Scroll
Scroll half a page using:  

**Scroll 1/2 Page Up:** ```CTRL-u```  
**Scroll 1/2 Page Down:** ```CTRL-d```  
### Marks
You can set marks in your code to jump to:

**Set Mark:** ```m<character>```  
**Jump to Mark:** ``` `<character>```  
*(\<character> is a letter or number, used as a register)*

### Line Jumps
You can jump using line numbers:

**Jump to Line:** ```<LineNum>G```  
*Example Usage:* ```95G```, jumps to line 95



### Quick Write and Quit
Rather than needing to type out the command ```:wq```and hitting enter, you can save some time with quick write-quit:  

**Write & Quit:** ```ZZ```  
*(make sure it's uppercase)*




# Commands
### Edit Different File
Going from one file to another without exiting Vim is crucial. 

**Edit File:** ```:edit <file>``` or just ```:e <file>```

### Shell & Terminal
While editing, you can seamlessly access your shell without exiting Vim.

You can run a command and view it's output with:  
**Run command:** ```:!<command>```  
*Example Usage:* ```:!echo Hello```

You can transform the entire text editor into a terminal with:  
**Switch to Terminal** ```:terminal``` or just ```:ter```  
 *(Neovim only)*


### Splitting
You can split your file many times in order to edit/view multiple files from the same window.


Split with another file, same file if no file is specified:  
**Split:** ```:split <file>```  
**Vertical Split:** ```:vsplit <file>```

Interact with split windows:  
**Jump to next window:** ```CTRL-w-w```  
**Jump in direction:** ```CTRL-w-(hjkl)```

**Vertically resize window:** ```CTRL-w-(+ or - )```  
**Horizontally resize window:** ```CTRL-w-(> or <)```


Splitting is especially useful with ```:terminal```

### Find and Replace (Substitute)
You can perform a find and replace using:  

**All-Lines Substitute:** ```:%s/<find>/<replace>```  
*Example Usage:* ```:%s/public int/private int```, swapping public integers to private integers


### Escape Re-bind
Pressing the escape key to exit insert mode is quite inefficient on my keyboard. You can rebind this to another key, or even a combination of keys.

**Escape Re-Map:** ```ionoremap jk <Esc>```  
Put this command in your Vim config file.

You can choose what you like, but many Vim users like to use 'j' and 'k' to exit insert mode. All you have to do is write "jk" quickly in insert mode.  


