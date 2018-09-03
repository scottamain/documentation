## vcgencmd 

`vcgencmd` is a command line utility that can get various pieces of information from the Videocore4 GPU on the Raspberry Pi. Much of the information available is only of use to internal Raspberry Pi developers, but there are number of very useful options available to end users that will be described here.

To get a list of all the command that vcgencmd supports, type `vcgencmd commands`.

### version

Reports the date and version of firmware running on the VC4. 

### measure_clock [clock]

This returns the current frequency of the specified clock. The options are:

| clock | Description |
|=======|============ |
| arm   | ARM cores |
| core  | VC4 scaler cores |
| H264  | H264 block |
| isp   | Image system Pipeline |
| v3d   | 3D block |
| uart  | UART |
| pwm   | PWM block (analogue audio output) | 
| emmc  | SD card interface |
| pixel | Pixel valve |
| vec | Analogue video encoder |
| hdmi | HDMI |
| dpi | Display Peripheral Interface |

e.g. `vcgencmd measure_clock arm`

### measure_volts [block]

Displays the current voltages used by the specific block.

| block | Description |
|=======|=============|
| core | VC4 core voltage |
| sdram_c | |
| sdram_i | |
| sdram_p | |

### measure_temp

Returns the current temperature of the SoC. 

### otp_dump

Displays the content of the One Time Programmable (OTP) memory, which is part of the SoC. These are 32 bit values, indexed from 8 to 64. See the [OTP bits page](../../../hardware/raspberrypi/otpbits.md) for more details.

### get_mem

Reports on the amount of memory allocated to the ARM cores `vcgencmd get_mem arm` and the VC4 `vcgencmd get_mem gpu`.

### codec_enabled [type]

Reports whether the specified CODEC type is enabled. Possible options for type are **H264, MPG2, WVC1, MPG4, MJPG, WMV9**.

### get_config [type]

This returns all the configuration items of the specified type that have been set in config.txt or by default. Possible values for type are **int, str**

### get_lcd_info

Displays the resolution and colour depth of any attached LCD display.

### mem_oom

Displays statistics on any Out of memory events occuring in the VC4 memory space.

### mem_reloc_stats

Displays statistics from the relocatable memory allocator on the VC4.

### get_camera

Reports whether the camera is support, and if so whether it is detected.






