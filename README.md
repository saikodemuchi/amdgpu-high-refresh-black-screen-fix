# amdgpu-high-refresh-black-screen-fix

EN: This fix may help with AMD GPU screen blanking or black screen problems on Linux when using high refresh rates like 120>hz.

Installation: Place the `amdgpu-clocks.conf` file from the repository in `/etc/tmpfiles.d/` and reboot the computer. Or create the file manually:

Create the tmpfiles config:

```bash
sudo nano /etc/tmpfiles.d/amdgpu-clocks.conf
```

Add these lines:

```conf
w /sys/class/drm/card1/device/power_dpm_force_performance_level - - - - manual
w /sys/class/drm/card1/device/pp_dpm_mclk - - - - 3
```

Then reboot your system:

```bash
sudo reboot
```

> Note: `card1` may be different on your system.


RU: Этот фикс может помочь, если на Linux с AMD видеокартой тухнет экран или появляется чёрный экран при высокой герцовке, например больше 120hz.

Установка: Разместите файл с репозитори `amdgpu-clocks.conf` по пути `/etc/tmpfiles.d/` и перезагрузите компьютер для работы. Или вручную создайте файл:


Создайте конфиг файл tmpfiles:

```bash
sudo nano /etc/tmpfiles.d/amdgpu-clocks.conf
```

И добавьте это:

```conf
w /sys/class/drm/card1/device/power_dpm_force_performance_level - - - - manual
w /sys/class/drm/card1/device/pp_dpm_mclk - - - - 3
```

После чего перезагрузите компьютер.

```bash
sudo reboot
```

> Предупреждение: `card1` может отличаться на вашей системе.
