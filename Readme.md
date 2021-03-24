## 0.更新日志
1. **2021.03.24：** 添加scatterND插件，并测试通过


## 1. 编译
- 不编译example
`cmake .. -DTRT_LIB_DIR=/home/darknet/CM/profile/TensorRT-7.2.2.3/lib -DTRT_OUT_DIR=`pwd`/out -DGPU_ARCHS=86 -DBUILD_SAMPLES=OFF`

- 编译example
`cmake .. -DTRT_LIB_DIR=/home/darknet/CM/profile/TensorRT-7.2.2.3/lib -DTRT_OUT_DIR=`pwd`/out -DGPU_ARCHS=86 -DBUILD_SAMPLES=ON`

注意:
- gpu_archs=86,是30x系列显卡的计算能力