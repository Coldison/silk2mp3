## 中文说明

本转码器由kn007完成，README.md 也由此人完成， 博客在最下方。 为了个人使用的方便，做了些修改。

解码silk v3音频文件（类似微信的amr和aud文件、QQ的slk文件）并转换为其它格式（如MP3）。
支持批量转换。

<a href="https://github.com/kn007/silk-v3-decoder/blob/master/LICENSE"><img src="https://img.shields.io/badge/license-MIT-green.svg?style=flat"></a>

```
silk-v3-decoder            (解码silk v3音频文件)
  |
  |---  silk               (Skype Silk源码)
  |
  |---  windows            (可用于Windows平台的应用程序)
  |
  |---  LICENSE            (软件使用范围许可)
  |
  |---  README.md          (说明)
  |
  |---  converter.sh       (转换脚本)
  |
  |---  converter_beta.sh  (转换脚本(测试版))
```

## 依赖组件

* gcc
* ffmpeg

由于mp3解码器需要版权，在Ubuntu16.04下可以
```
sudo apt-get install ubuntu-restricted-extras
```

## gcc安装
只要是最新的应该就可以

## Ubuntu16.04下ffmpeg安装

主要参考 （http://blog.csdn.net/abcsunl/article/details/70145078）
其中可以跳过libx265的安装，因为在安装中使用到hg命令，这是一种类似于git的版本控制系统，需要安装mercurial- TortoiseHG。而做TortoiseHG的貌似已经解散。而libx265是一种视频编码方案。因此可以不用安装
如果想要安装，参见（https://xwsoul.com/posts/23）

在最后安装ffmpeg时，删掉--enable-libx265即可。

执行
```
source ~/.profile
```
即可全局使用。

## centos6.8下ffmpeg安装

参考https://www.2cto.com/kf/201708/672842.html
这个没有试过。


## 如何使用

```
sh converter.sh silk_v3_file/input_folder output_format/output_folder flag(format)
```
比如转换一个文件，使用：
```
sh converter.sh 33921FF3774A773BB193B6FD4AD7C33E.slk mp3
```
注意：其中`33921FF3774A773BB193B6FD4AD7C33E.slk`是要转换的文件，而`mp3`是最终转换后输出的格式。

如果你需要批量转换，比如转换某个目录，那么使用：
```
sh converter.sh input ouput mp3
```
注意：其中`input`是要转换的目录，而`output`是最终转换后音频输出的目录，最后的`mp3`参数是最终转换后输出的格式。

如果需要从指定路径转码到指定路径，加上绝对路径即可。


## 其他说明

如果你需要对音频文件进行silk v3编码，源码也已经提供，并且对微信、QQ进行了兼容，详见参数。

## 关于作者

[kn007的个人博客](https://kn007.net) 
