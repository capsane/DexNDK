# DexNDK
Bypass the c++ hook put in Audio framework using Dexposed
1、Dexposed AudioRecord.java类中的startRecording()函数，Android系统中这部分源码已经修改为do nothing, 无法使用该函数正常录音。
但是hook()之后，执行了startRecording()中的native_start()函数的调用，使得录音可以使用。

2、目的：通过libmedia.so直接录音，即越过java层。
不知道能否覆盖掉app空间里的原libmedia.so库，或者接触到AudioSystem.cpp中的startInput()函数，这个函数就是AuDroid中的Hook所在位置。
