# Personal Keyboard Setup

## Why?

There're two things bother me for a while.

The first thing is that it always hurt my little finger to press a Ctrl key on a laptop. When I got a HHKB, I found that layout which put Ctrl on the position of CapsLock on a tranditional keyboard, is great. But there're trade off. I have to press `Fn + Tab` to switch CapsLock on HHKB and there's only one Ctrl. The shortcut like `Ctrl + A` is pretty hard to press with one hand(My little finger still feel painful if I do this). So I want two Ctrl on each side, One at the position of CapsLock and another at the position of Enter. And both keys will act like the origin key if I press them alone.

The second, I use Dvorak Programmer layout which is awesome for programming, I can type most symbols without hold shift, It makes my little finger feels better again! Because in the scence we use symbols more frequently than numbers. However when we have to type a long number, like 20180520100020, I have to hold shift for a long period, there's no numpad on my laptop. In the old days, some laptops have a numpad when you hold `Fn` and this feature can rarely be found in the recent models. So I want a numpad, the trigger key is `Tab`, pretty easy to hold.

## Intro
This script gives me:

+ Hold CapsLock as Control, send CapsLock when press alone.
+ Hold Enter as Control, send Enter when press alone.
+ Hold Tab to enable numpad(GCRHTNMWV and space), send Tab when press alone.

## Usage
Use this script in `~/.xinitrc`.
```shell
xmodmap -e "clear lock"

xmodmap -e "keycode 66 = Hyper_L"
xmodmap -e "remove mod4 = Hyper_L"
xmodmap -e "add control = Hyper_L"
xmodmap -e "keycode 166 = Caps_Lock"
xcape -t 1000 -e "Hyper_L=Caps_Lock"

xmodmap -e "keycode 36 = Hyper_R"
xmodmap -e "add control = Hyper_R"
xmodmap -e "keycode 167 = Return"
xcape -e "Hyper_R=Return"

xmodmap -e "keycode 168 = Tab"
xmodmap -e "keycode 23 = Mode_switch"
xcape -e "Mode_switch=Tab"

xmodmap -e "keycode 58 = m M 1 1"
xmodmap -e "keycode 59 = w W 2 2"
xmodmap -e "keycode 60 = v V 3 3"
xmodmap -e "keycode 44 = h H 4 4"
xmodmap -e "keycode 45 = t T 5 5"
xmodmap -e "keycode 46 = n N 6 6"
xmodmap -e "keycode 30 = g G 7 7"
xmodmap -e "keycode 31 = c C 8 8"
xmodmap -e "keycode 32 = r R 9 9"
xmodmap -e "keycode 65 = space NoSymbol 0 0"
```

That's it!
