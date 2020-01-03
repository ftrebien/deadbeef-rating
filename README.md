# DeaDBeeF Song Rating plugin

A plugin enabling commands to rate tracks by writing to the `%rating%` metadata tag. The commands are accessible from the context menu or by binding them to hotkeys. 

Big thanks to [Alexey Yakovenko](https://github.com/Alexey-Yakovenko) for the [DeaDBeeF](http://deadbeef.sourceforge.net/) music player.

# Building & Installing
1. Clone this repository
2. Download `deadbeef.h`, for example from the [DeaDBeeF source code](http://deadbeef.sourceforge.net/download.html)
3. Run `sh build.sh [path to dir with deadbeef.h]`
4. Run `sh easyinstall.sh` to install the plugin to ~/.local/lib/deadbeef, or copy `rating.so` yourself to your DeaDBeeF plugin directory

When DeaDBeeF is installed using one of the `.deb` packages, the path to `deadbeef.h` is `/opt/deadbeef/include/deadbeef/` and the plugin directory is `/opt/deadbeef/lib/deadbeef/`.

# Uninstalling
Run `sh easyuninstall.sh` to remove the plugin from ~/.local/lib/deadbeef, or remove `rating.so` yourself from your DeaDBeeF plugin directory.

# Using
In order to show the rating in the playlist, add a new custom column with the following format:

`$if($strcmp(%rating%,$add(0,%rating%)),$select($add(1,$div($min(100,$max(0,%rating%)),10)),0,1,2,3,4,5,6,7,8,9,10),%rating%)`

You can replace the numbers with your rating indicators of choice, such as `★`, `☆` and `⯪`.

# License

    DeaDBeeF rating plugin
    Copyright (C) 2016  Christian Hernvall

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
