---
title: "getConfigFilePath"
date: 2024-11-17
---

函数原型: ``Ogre::String getConfigFilePath(Ogre::String filename) const``

### Ogre如何找一个ConfigFile呢？
- 从getWritablePath找
- 从一组配置的目录(`mConfigPaths`)里找

### mConfigPaths包含哪些目录呢
- 环境变量``OGRE_CONFIG_DIR``
- 可执行程序所在目录 (PC平台)
- 平台特殊的一些目录
	- Linux的/etc/OGRE/, share目录等
	- Mac的bundle、Contents/Resources等
	- iOS ...

### resources.cfg
基于OgreBites的程序（如`SampleBrowser`）在启动后首先需要找配置``resources.cfg``, 若找不到必会报错。常常是因为配置路径问题。