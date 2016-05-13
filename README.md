# AndroidProxySetter
通过adb 设置wifi代理的Android App
**不需要事先root**

使用第第三库<https://github.com/shouldit/android-proxy/tree/master/android-proxy-library>

# 用法

编译后安装此App到你的Android设备或Android模拟器上, 然后按下面操作

在终端上执行以下命令并带上相应的参数：

```
	adb shell am start -n tk.elevenk.proxysetter/.MainActivity
```

参数:

```
	-e host <host>					# The host ip or address for the proxy
	-e port <port>					# The port for the proxy
	-e ssid <ssid>					# The SSID of the wifi network to set proxy on
									  (optional, will apply on the first one if empty)
	-e key <shared key>				# The password/key for the wifi network
	-e bypass <bypass string>		# The bypass string to use for proxy settings
	-e reset-wifi <boolean>			# Whether or not to reset the wifi settings. This flag will tell
										the tool to forget all connected networks, make a new
										network config with the SSID and key given, and then
										attempt to connect to the wifi network. If no key is given,
										the wifi network is assumed to be unprotected/open
	-e clear <boolean>				# A flag that will clear the proxy settings for the given SSID
```

**注意：
如果只是为了设置代理，host和ssid是必需的。
加上`reset-wifi`参数，会"忘记"所有的连接。**
