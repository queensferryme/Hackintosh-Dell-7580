# Hackintosh-Dell-7580

For general installation instructions, please refer to [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/). This project could not be possible without the help of [ppjjhh/Hackintosh-Dell-Inspiron-7580](https://github.com/ppjjhh/Hackintosh-Dell-Inspiron-7580), which unfortunately is not longer maintained.

## Notes

### Fix headphone audio distortion

If you experience audio distortion when plugging in your headphone, please

1. Download `Utils/hda-verb` and move it to `/usr/local/bin`;
2. Download the `Utils/Launch.app` and move it to your Application folder in the Finder (or anywhere else you like). Then open the *Users & Groups* pane of System Preferences, click the *Login Items* tab and add *Launch.app* to the list.

Every time you log in from now on, the application will be automatically executed. What this app really does under the hood is to run two simple lines of shell commands (source https://www.elitemacx86.com/threads/fix-audio-distortion-when-using-headphones-on-laptops.185/) that will fix the problem:

```bash
/usr/local/bin/hda-verb 0x19 SET_PIN_WIDGET_CONTROL 0x25
/usr/local/bin/hda-verb 0x21 SET_UNSOLICITED_ENABLE 0x83
```



