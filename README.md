#  KDDI/Docomo Optimus G (LGL21/L01E) oreo Kernel for crDroid 8.0 / aex-8.1


2020/03/17 

dmesgのエラーメッセージ解消

drivers/staging/prima/            ... WLANドライバをmakoに入れ替え
drivers/video/backlight/lm3533.c  ... 明るさのMAX値チェックを挿入
kernel/timer/alarmtimer.c         ... suspendエラーを解消
drivers/leds/leds-pm8xxx.c        ... ledドライバのエラーを解消
arch/arm/mach-msm/qdsp6v2/audio_amrwbplus.c ... DEBUG_FSなしのコンパイルエラー修正

defconfig の見直し referenced v500 8.1 kernel

-CONFIG_PERSISTENT_TRACER=y
+# CONFIG_PERSISTENT_TRACER is not set

... これをすると DEBUG_FSが無効になり、コンパイルエラーが多発する

-# CONFIG_ANDROID_RAM_CONSOLE is not set
+CONFIG_ANDROID_RAM_CONSOLE=y

-CONFIG_BATTERY_TEMP_CONTROL=y
+# CONFIG_BATTERY_TEMP_CONTROL is not set

-CONFIG_DEVMEM=y
+# CONFIG_DEVMEM is not set

-CONFIG_DEVKMEM=y
+# CONFIG_DEVKMEM is not set

-# CONFIG_DEFAULT_CUBIC is not set
+CONFIG_DEFAULT_CUBIC=y

-CONFIG_DEFAULT_WESTWOOD=y
+# CONFIG_DEFAULT_WESTWOOD is not set

-CONFIG_DEFAULT_TCP_CONG="westwood"
+CONFIG_DEFAULT_TCP_CONG="cubic"

-CONFIG_FUNCTION_TRACER=y
+# CONFIG_FUNCTION_TRACER is not set

-CONFIG_EXT2_FS=y
+# CONFIG_EXT2_FS is not set

-CONFIG_EXT2_FS_XATTR=y
# CONFIG_EXT2_FS_XATTR is not set

-CONFIG_EXT3_FS=y
+# CONFIG_EXT3_FS is not set


