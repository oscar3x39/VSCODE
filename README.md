### phpstorm
```
Tools > Create Command-Line-Launcher
/usr/local/bin/phpstorm
```

### vim color
```
mkdir -p ~/.vim/colors/
git clone https://github.com/flazz/vim-colorschemes
mv ~/vim-colorschemes/colors/molokai.vim ~/.vim/colors/
```
vim ~/.vimrc
```
syntax on
colo molokai
set nu
```

### spotlight
`disable`

### Input keyboard 
`cmd+space`

### Alfred
`ctrl+space`
`install chatgpt workflow`

### hammerspoon
```
---------------------
-- Config for https://www.hammerspoon.org/
-- Based on https://gist.github.com/philc/ed70ae4e60062c2d494fae97d5da43ce
-- see above for more advanced config including multiple display support
---------------------
-- make animations fast
hs.window.animationDuration = 0.1

---------------------
-- Window positioning
---------------------

function moveTopHalf()
  local win = hs.window.focusedWindow()
  local f = win:frame()
  local screen = win:screen()
  local max = screen:frame()
  f.x = max.x
  f.y = max.y
  f.w = max.w
  f.h = max.h / 2
  win:setFrame(f)
end

function moveBottomHalf()
  local win = hs.window.focusedWindow()
  local f = win:frame()
  local screen = win:screen()
  local max = screen:frame()
  f.x = max.x
  f.y = max.y + (max.h / 2)
  f.w = max.w
  f.h = max.h / 2
  win:setFrame(f)
end

function moveLeftHalf()
  local win = hs.window.focusedWindow()
  local f = win:frame()
  local screen = win:screen()
  local max = screen:frame()
  f.x = max.x
  f.y = max.y
  f.w = max.w / 2
  f.h = max.h
  win:setFrame(f)
end

function moveRightHalf()
  local win = hs.window.focusedWindow()
  local f = win:frame()
  local screen = win:screen()
  local max = screen:frame()
  f.x = max.x + (max.w / 2)
  f.y = max.y
  f.w = max.w / 2
  f.h = max.h
  win:setFrame(f)
end

function maximize()
  local win = hs.window.focusedWindow()
  local f = win:frame()
  local screen = win:screen()
  local max = screen:frame()
  f.x = max.x
  f.y = max.y
  f.w = max.w
  f.h = max.h
  win:setFrame(f)
end

hs.hotkey.bind({"cmd", "ctrl"}, "left", function() moveLeftHalf() end)
hs.hotkey.bind({"cmd", "ctrl"}, "right", function() moveRightHalf() end)
hs.hotkey.bind({"cmd", "ctrl"}, "up", maximize)
```
