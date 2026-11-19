# South Building COLMAP 稠密点云素材

本仓库用于保存 South Building 后续三角网格重建所需的稠密点云素材。

## 文件

`fused.ply` 通过 GitHub Release 发布，不直接写入 Git 历史。

- 格式：二进制 PLY 稠密点云
- 顶点数：3,609,743
- 文件大小：97,463,296 字节
- SHA-256：`c2c08da5e7bf58cfc519667fb32d4862f50a41f3d23d651f2630ae6e66653ae2`
- 包含属性：坐标、法向量、RGB 颜色

## 数据来源

- 原始场景：COLMAP 官方 South Building 数据集
- 稠密结果来源：公开数据集 `alexmkwizu/colmap-testing-dataset`
- 上游说明：该结果由 COLMAP 4.0.4 CUDA 版本在 NVIDIA T4 上生成

此文件不是 COLMAP 官方压缩包自带的三角网格。项目会在服务器上以它为输入运行 `poisson_mesher`，生成 `meshed-poisson.ply`。

## 服务器生成三角网格

```bash
colmap poisson_mesher \
  --input_path fused.ply \
  --output_path meshed-poisson.ply
```

生成完毕后，`meshed-poisson.ply` 才是包含顶点和三角面的网格模型。

## 来源链接

- COLMAP 数据集页面：https://colmap.github.io/datasets.html
- 稠密结果仓库：https://huggingface.co/datasets/alexmkwizu/colmap-testing-dataset
