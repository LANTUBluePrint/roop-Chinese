
使用一段视频，将其中的面部替换为你选择的面部。你只需要一张所需面部的图像，不需要数据集或训练。(目前测试结果一般)

就是这样，这就是这个软件。你可以观看一些[演示](https://drive.google.com/drive/folders/1KHv8n_rd3Lcr2v7jBq1yPSTWM554Gq8e?usp=sharing).

![demo-gif](demo.gif)

## 如何安装？

有两种安装方式：基本安装和使用 GPU 加速的安装。

基本安装： 这种方式更有可能在你的计算机上运行，但速度会非常慢。你可以按照基本安装的指令进行操作。 [查看](https://github.com/s0md3v/roop/wiki/1.-Installation).

- **GPU:** 如果你有一块好的 GPU，并且准备解决可能遇到的任何软件问题，你可以启用 GPU 加速，速度会快很多。要做到这一点，首先按照上述的基本安装指令进行操作，然后按照针对 GPU 的特定指令进行操作。 [查看](https://github.com/s0md3v/roop/wiki/2.-GPU-Acceleration).

特别注明：我在使用GPU执行时，我的AMD 5950x和RTX 3080ti均达到了100%占用，并且发生蓝屏。暂时未在RTX3090上测试。暂不清楚是什么问题导致的。

## 如何运行
> Note: 第一次运行会下载大约300mb的的模型包，如果提示缺乏taskname，就要下载inswapper_128.onnx，并保存到根目录，不要保存在模型生成的文件夹下，不然会出现同样的问题。

## windows下
打开命令行输入<python run.py>即可运行
如果想要通过GPU执行则输入<python run.py --gpu>


![gui-demo](gui-demo.png)

选择一个面部图像（带有所需面部的图像）和目标图像/视频（希望替换面部的图像/视频），然后点击 Start。打开文件浏览器，导航到你选择的输出目录。你将会找到一个名为 <video_title> （默认情况下是output.mp4）的视频文件，其中你可以实时看到帧被交换的过程。一旦处理完成，它将创建输出文件。就是这样。
  
不要轻易点击FPS选择，除非你知道会发生什么。
  
Additional command line arguments are given below:

```
options:
  -h, --help            show this help message and exit
  -f SOURCE_IMG,      --face SOURCE_IMG
                        use this face
  -t TARGET_PATH,     --target TARGET_PATH
                        replace this face
  -o OUTPUT_FILE,     --output OUTPUT_FILE
                        save output to this file
  --gpu                 use gpu
  --keep-fps            maintain original fps
  --keep-frames         keep frames directory
  --max-memory MAX_MEMORY
                        set max memory
  --max-cores CORES_COUNT
                        set max cpu cores
```

Looking for a CLI mode? Using the -f/--face argument will make the program in cli mode.

## Future plans
- [ ] Improve the quality of faces in results
- [ ] Replace a selective face throughout the video
- [ ] Support for replacing multiple faces

## Disclaimer
Deepfake software already exist. This is just an experiment to make the existing techniques better. Users are expected to use this to learn about AI and not use it for illicit or unethical purposes. Users must get consent from the concerned people before using their face and must not hide the fact that it is a deepfake when posting content online. I am not responsible for any malicious activity done through this software, this is a purely educational project aimed at exploring AI.

## Credits
- [ffmpeg](https://ffmpeg.org/): for making video related operations easy
- [deepinsight](https://github.com/deepinsight): for their [insightface](https://github.com/deepinsight/insightface) project which provided a well-made library and models.
- and all developers behind libraries used in this project.
