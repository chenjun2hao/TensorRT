## 0.更新日志
1. **2021.03.24：** 添加scatterND插件，并测试通过


## 1. 编译
只能先编译插件库安装插件库，再编译解析库
1. 编译插件库与安装
```bash
mkdir build && cd build
cmake .. -DTRT_LIB_DIR=/home/darknet/CM/profile/TensorRT-7.2.2.3/lib -DTRT_OUT_DIR=`pwd`/out -DGPU_ARCHS=86 -DBUILD_PLUGINS=ON -DBUILD_PARSERS=OFF -DBUILD_SAMPLES=OFF
make -j4
```
编译完成之后在`build/out`就有插件的动态库了`libnvinfer_plugin.so`
然后安装，该命令会替换`/home/darknet/CM/profile/TensorRT-7.2.2.3/lib`路径下原有的插件动态库
`make install`

2. 编译解析库

解析库是用于模型转换的：onnx2trt
```bash
mkdir build && cd build
cmake .. -DTRT_LIB_DIR=/home/darknet/CM/profile/TensorRT-7.2.2.3/lib -DTRT_OUT_DIR=`pwd`/out -DGPU_ARCHS=86 -DBUILD_PLUGINS=OFF -DBUILD_PARSERS=ON -DBUILD_SAMPLES=OFF
make -j4
```
完成之后会得到`build/parsers/onnx/onnx2trt`


## 2. 插件库的使用
...

注意:
- gpu_archs=86,是30x系列显卡的计算能力