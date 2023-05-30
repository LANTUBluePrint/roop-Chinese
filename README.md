
使用一段视频，将其中的面部替换为你选择的面部。你只需要一张所需面部的图像，不需要数据集或训练。

就是这样，这就是这个软件。你可以观看一些[演示](https://drive.google.com/drive/folders/1KHv8n_rd3Lcr2v7jBq1yPSTWM554Gq8e?usp=sharing).

![demo-gif](demo.gif)

## 如何安装？

有两种安装方式：基本安装和使用 GPU 加速的安装。

基本安装： 这种方式更有可能在你的计算机上运行，但速度会非常慢。你可以按照基本安装的指令进行操作。 [查看](https://github.com/s0md3v/roop/wiki/1.-Installation).

- **GPU:** 如果你有一块好的 GPU，并且准备解决可能遇到的任何软件问题，你可以启用 GPU 加速，速度会快很多。要做到这一点，首先按照上述的基本安装指令进行操作，然后按照针对 GPU 的特定指令进行操作。 [查看](https://github.com/s0md3v/roop/wiki/2.-GPU-Acceleration).

## 如何运行
> Note: 第一次运行会下载大约300mb的的模型包，如果提示缺乏taskname，就要下载inswapper_128.onnx，并保存到根目录，不要保存在模型生成的文件夹下
打开命令行输入<python run.py>
Executing `python run.py` command will launch this window:
![gui-demo](gui-demo.png)

Choose a face (image with desired face) and the target image/video (image/video in which you want to replace the face) and click on `Start`. Open file explorer and navigate to the directory you select your output to be in. You will find a directory named `<video_title>` where you can see the frames being swapped in realtime. Once the processing is done, it will create the output file. That's it.

Don't touch the FPS checkbox unless you know what you are doing.

Additional command line arguments are given below:

```
options:
  -h, --help            show this help message and exit
  -f SOURCE_IMG, --face SOURCE_IMG
                        use this face
  -t TARGET_PATH, --target TARGET_PATH
                        replace this face
  -o OUTPUT_FILE, --output OUTPUT_FILE
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
