# Serial Connectivity to Your Device

In Lab 2 and Lab 3, you need to connect to your device using a _serial connection_.  Today, most times this is achieved through a USB2 or USB3 port on your computer.  If you have USB-C only, you will need to provide a converter.

Not all programs that enable serial connections are created equal.  The applications and command differ between Windows and Mac OS. **Choose one of the following based on your workstation's operating system**.

* [Serial Connectivity for Mac OSX](#serial-connectivity-for-mac-osx)
* [Serial Connectivity for Microsoft Windows](#serial-connectivity-for-microsoft-windows)

# Serial Connectivity for Mac OSX

* Recommended free app: `screen`
* Recommended non-free app: `Serial` [see in Apple store](https://apps.apple.com/us/app/serial/id877615577)

To find the device name, open `Terminal` and issue the following command.

```bash
ls /dev/tty.usb*
```

The output will be similar to the following:

```bash
/dev/tty.usbmodem14324102
```

Substitute your device name in commands below or use /dev/tty.usb and tab for name completion.

Using screen (built in.. no additional install needed)

```bash
screen /dev/tty.usbmodem1411102 115200
```

Use `ctrl-a` then `k` to kill the session

It is assumed that if you have Serial then you know how to use it.

## Other serial programs

Other serial programs include

* minicom
* picocom

To install, use Homebrew.

brew install minicom
brew install picocom

To connect using `minicom`, issue the following command:

```bash
minicom -b 115200 -D /dev/tty.usbmodem14324102
```
Enter, ctrl-a q to quit

To connect using `picocom`, issue the following command:

```bash
picocom -b 115200 /dev/tty.usbmodem14324102
```
Enter `ctrl-a q` to quit


Chrome Serial Monitor app
Free. install from: https://chrome.google.com/webstore/detail/serial-monitor/ohncdkkhephpakbbecnkclhjkmbjnmlo?hl=en

Use Arduino built in monitor

# Serial Connectivity for Microsoft Windows

For this workshop, we are using TeraTerm to connect to the device over serial.  If you have another preferred application, please go ahead and use it if you desire but facilitators in the workshop may not be able to assist.

## Connecting with TeraTerm

1. Open the program **TeraTerm** you installed in Lab 1.  You will see a dialog box similar to the following.

   ![tt1](workshop-images/2_tt_1.PNG)

2. Click the **Serial** radio button, and select the COM port labeled **Curiosity Virtual COM Port** and then click **OK**.

   ![tt2](workshop-images/2_tt_2.PNG)

3. On the menu, click **Setup** and then **Serial port...**.
4. For Speed, select 115200 and then click **New setting**.  (older TeraTerm versions will ask you to click **OK**)

   ![tt3](workshop-images/2_tt_3.png)

5. You should see output similar to the following after hitting the device reset button.

   ![tt4](workshop-images/2_tt_4.PNG)
