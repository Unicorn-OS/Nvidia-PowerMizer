Using this information, we can use the -a option to set the value of GpuPowerMizerMode to 1 and verify it has been changed using the -q option:
```
$ nvidia-settings -a "[gpu:0]/GpuPowerMizerMode=1"

  Attribute 'GPUPowerMizerMode' (rastating-PC:1[gpu:0]) assigned value 1.

$ nvidia-settings -q GpuPowerMizerMode
```
