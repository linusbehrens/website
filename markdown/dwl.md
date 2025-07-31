---
title: dwl, ultra minimal tiling window manager
author: "Linus Behrens"
date: 2025-06-16T14:00:00+02:00
tags: ['tech', 'wm', 'suckless']
header: "/header/linux.jpg"
---

My first rather serious linux system should be built on a Thinkpad x61s in 2023. 
Due to a lack in performence I thought about installing only the most minimal software on it.

So I came to see the famouse Thinkpad Arch combination. (I know and knew that it was not the most minimal os possible, but I was convinced)
When trying to find the most minimal and fast window manager found the perfect fit: `dwm`.

`dwm` became my wm that just worked.

---

However as I continued to gain understanding of how Xorg works and as I understood the bloat in `X`, I found it hard to swich.
On YouTube I came across `dwl` a project about translating `dwl` to work with `wlroots`.

Even though being familiar with the rather difficult to install `dwm`, I wasn't able to even compile `dwl`. Now I understand and give you - the reader - a path to follow.

```bash
sudo dnf install \
  libinput libinput-devel \
  wayland wayland-devel \
  wlroots wlroots-devel \
  xkbcommon xkbcommon-devel \
  wayland-protocols \
  pkgconf-pkg-config
```

```bash
git clone https://codeberg.org/dwl/dwl.git
cd dwl
git checkout v0.7
make
sudo make install
```

```bash
sudo dnf install \
  libinput libinput-devel \
  wayland wayland-devel \
  wlroots wlroots-devel \
  xkbcommon xkbcommon-devel \
  wayland-protocols-devel \
  pkgconf-pkg-config \
  meson ninja-build \
  gcc
```
```bash
git clone https://github.com/waycrate/wmenu.git
cd wmenu
meson setup build
ninja -C build
sudo ninja -C build install
```

---

Edits to `sources/dwl/config.h`:

```c
static const char *termcmd[] = { "ghostty", NULL };
```

```c
static const MonitorRule monrules[] = {
    /* macbook m1 14" */
    { "eDP-1",    0.5f,  1,      2,    &layouts[0], WL_OUTPUT_TRANSFORM_NORMAL,   -1,  -1 },
};
```

```c
static const struct xkb_rule_names xkb_rules = {
    /* default:
    .options = NULL,
    */
    .layout = "de",
    .variant = "latin1",
};
```



