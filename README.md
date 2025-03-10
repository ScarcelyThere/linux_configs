# linux_configs
Linux kernel configs for computers I have known and used

For now, I'll name the configs after the DMI strings of the PCs they're meant for.
I'll try to document each one separately.

I've been using btrfs and bcachefs, so those are the only typical on-disk
filesystems I've included in these kernels. FAT and ISO9660 are included as modules
due to their popularity. You will likely want to change some of the configuration
before you build a kernel for yourself. At minimum, add your preferred filesystem
(or at minimum, EXT4.) Rolling your own kernel is likely better than these
configurations.

## T102HA.config
This is for an Asus Transformer Mini (model T102H) and is very experimental. There's
a lot enabled that probably doesn't need to be, but we're going to see what drivers
bind to what devices and go from there. We've still got more enabled than likely
needs to be, but it's becoming functional.

## Presario_CQ57.config
This is for a Compaq (now HP) Presario CQ57 laptop, powered by AMD's E-300 APU. Note
this kernel was only tested with Alpine Linux. There are a few unclaimed devices
reported by `lshw`, but most everything should work.

### Note:
The Presario CQ57 carries an AMD Bobcat processor core as part of its E-300 APU, so
I am using a patch to add specific support for that CPU in the build. The specific
patch is [here](https://github.com/graysky2/kernel_compiler_patch.git).

## Configs that are no longer updated

## hp_X0H86UA.config
This is for a hp Notebook 15-ay041wm touch laptop with product number X0H86UA#ABA. It
has a Skylake Intel Core i3 processor with a GT2 graphics chip (HD Graphics 520.)
I no longer own this computer, so there will be no further changes to this config.
No webcam support was built here, either.

## Satellite_C55-B.config
This is for a Toshiba Satellite C55-B5201 laptop. It's powered by a Bay Trail notebook
Celeron processor and carries Intel HD Graphics (which are driven by the kernel's i915
driver.) I no longer own this computer, so there will be no further changes to this
config. A few built-in devices weren't included here.
