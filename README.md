# brcmfmac_sdio-firmware
The following wireless/bluetooth modules are currently supported:

* AP6212 Khadas_VIM _basic_
* AP6255 WeTek_Hub v2, Khadas_VIM _pro_
* AP6330 WeTek_Play_2, Cubox-i2/4
* AP6335 WeTek_Hub v1
* BCM4329 Cubox-i2/4

Use of `hciattach` and `brcm_patchram_plus` are deprecated and firmware loading can be triggered by including `compatible = "brcm,bcm43438-bt";` nodes in device-tree. For more information refer to [Linux Kernel Documentation](https://github.com/torvalds/linux/blob/master/Documentation/devicetree/bindings/net/broadcom-bluetooth.txt).

There are several known examples of SDIO modules sharing device ID's so it may be necessary to patch the [firmware mapping table](https://github.com/torvalds/linux/blob/master/drivers/bluetooth/btbcm.c) to ensure the correct firmware file is loaded. If you find new mappings in the wild please upstream them!
