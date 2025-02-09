# Fan Being Loud with no Substantial Load

This issue started happening around 12/14/2024. The symptoms:
- you boot up
- start up two terminal windows and chrome
- do not do anything special
- some cpus are at 80% load and the fan goes brrr.

Solution:
- turns out there was something wrong with `swaylock`
- notes online suggest that it can be connected with multimonitor setup and
  `swaylock` screenshot wallpaper feature
- a quick fix is to kill swaylock (why is it even running after system unlocked
  in the first place?)

The solution above is not sufficient as it requires repeated actions
there are two possible alternatives:
- change swaylock config not to do screenshots
- change the lock script to not use screenshot if two monitors are detected

Option 2 above requires some scripting effort but can be the final solution

[Back to home](./README.md)
