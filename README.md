# rhel-rtk

* Using rhel 8.7 for current deployment.
Become a root user using `su -` or `sudo su`

1. Enable the Red Hat Enterprise Linux for Real Time repository:
```bash
subscription-manager repos --enable rhel-8-for-x86_64-rt-rpms
```

if this gives error, then find the correct repo:
Use the following command for checking:

```bash
subscription-manager repos --list
```

then find the one suitable one for you, like in my case it is `rhel-8-for-x86_64-rt-rpms`

![image](https://github.com/AdityaKoranga/rhel-rtk/assets/95766110/27cc27c4-d60f-4107-b639-1dbdf2f42d04)

2. Install the Red Hat Enterprise Linux for Real Time package group:

```bash
yum groupinstall RT
```

the output will be like this:

![image](https://github.com/AdityaKoranga/rhel-rtk/assets/95766110/a1003f77-fefa-4f40-b414-dec6faacb2cc)

Then click `yes` everytime if it says to install some packages or any other thing:

![image](https://github.com/AdityaKoranga/rhel-rtk/assets/95766110/8b0a4b92-b67b-43c6-9f0a-cf4d51f36d1a)

Things will be done and the output will be like this:

![image](https://github.com/AdityaKoranga/rhel-rtk/assets/95766110/90ec48fb-e01e-4da2-999c-c0a790c36cd4)

3. You can check the installation location and that the components have been installed successfully by using the rpm -ql command:

```bash
rpm -ql rt-setup
```
![image](https://github.com/AdityaKoranga/rhel-rtk/assets/95766110/f44bebba-9800-4526-bff4-93a49033d5ee)

4. Now just reboot the system:
Note: it will select real time by default or you just click on the `rt-kernel` option at the time of boot

5. Now check the kernel version:

```bash
uname -r
```

![image](https://github.com/AdityaKoranga/rhel-rtk/assets/95766110/57725246-970f-4cb8-9a44-8d2a0bd3f909)





