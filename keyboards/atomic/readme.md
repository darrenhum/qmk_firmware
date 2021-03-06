Atomic keyboard firmware
======================
DIY/Assembled ortholinear 60% keyboard by [Ortholinear Keyboards](http://ortholinearkeyboards.com).

## Quantum MK Firmware

For the full Quantum feature list, see [the parent readme.md](/readme.md).

## Building

Download or clone the whole firmware and navigate to the keyboards/atomic folder. Once your dev env is setup, you'll be able to type `make` to generate your .hex - you can then use `make dfu` to program your PCB once you hit the reset button. 

Depending on which keymap you would like to use, you will have to compile slightly differently.

### Default
To build with the default keymap, simply run `make default`.

### Other Keymaps
Several version of keymap are available in advance but you are recommended to define your favorite layout yourself. To define your own keymap create a file in the keymaps folder named `<name>.c` and see keymap document (you can find in top readme.md) and existent keymap files.

To build the firmware binary hex file with a keymap just do `make` with a keymap like this:

```
$ make [default|jack|<name>]
```
Keymaps follow the format **__\<name\>.c__** and are stored in the `keymaps` folder.

## Notes
 - To build: run `make atomic-<keymap folder name>` at qmk_firmware root dir
 - To flash: run `qmk flasher` on macbookpro, select new hex file, push reset on keyboard, flash
 - To get tap dance to work, create a new Makefile and have `TAP_DANCE_ENABLE = yes' 
   - Make sure it is in the same directory as the custom keymap.c 
