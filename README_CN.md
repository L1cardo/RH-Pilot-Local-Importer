#
<p align="center">
<h1 align="center">RotorHazard 飞手及分组导入器</h1>
<h3 align="center">该插件可以让您在 RotorHazard 中通过本地文件导入飞手及分组<br>
  <a href="./README.md">[🇺🇸English]</a><br>
</h3>

<p align="center">
  <a href="https://github.com/L1cardo/RH-Pilot-Local-Importer/actions/workflows/rhfest.yml">
    <img src="https://github.com/L1cardo/RH-Pilot-Local-Importer/actions/workflows/rhfest.yml/badge.svg" alt="RHFest">
  </a>
</p>

## 特点

- 从本地文件导入飞手
- 自动创建一个赛程
- 根据导入的数据生成分组
- 将飞手分配到对应的分组

## 安装

- ### 手动

1. 克隆该仓库或下载源代码
2. 把 `pilot_local_importer` 文件夹放到 RotorHazard 插件目录中 `~/RotorHazard/src/server/plugins`
3. 安装依赖 `pip install openpyxl`
3. 重启 RotorHazard 服务器

- ### 命令行

```bash
cd ~
sudo rm -r RotorHazard/src/server/plugins/pilot_local_importer
wget https://github.com/l1cardo/RH-Pilot-Local-Importer/releases/latest/download/pilot_local_importer.zip
unzip pilot_local_importer.zip -d pilot_local_importer
cp -r pilot_local_importer RotorHazard/src/server/plugins/
rm -r pilot_local_importer
rm pilot_local_importer.zip
pip install openpyxl
sudo systemctl restart rotorhazard.service
```

## 使用方法

1. 手动创建一个 Excel 文件并 **严格** 遵守以下格式，或者在 "数据管理-导出器" 中选择 "模板-导入飞手及分组-Licardo":

![](/asset/sheet_cn.png)

- `赛程名称`: 可以改为任何你想要的赛程名称，但是不能与已存在的赛程同名

- `分组`: 分组名称, 拥有相同分组名称的飞手会被分配到相同分组

- `姓名`: 飞手名称

- `呼号`: 飞手呼号 **必须** 唯一

- `团队`: 飞手所归属的团队，**只** 支持 `A`-`Z` 的单字母，**必须** 为大写

- `频率`: RotorHazard不能通过插件设定频率, 这一项仅仅为了方便查看

- `颜色`: 支持以下的颜色名称和任何 Hex 颜色码, `蓝, 橙, 绿, 红, 黄, 紫, 青, 灰, 任何 Hex 颜色码 #7f679`

2. 找到格式页面下的 "数据管理" 模块

3. 在导入器中选择 `Import Pilots and Heats`, 然后选择你的 Excel 文件

4. 点击 "导入" 按钮进行导入

## 许可证

[MIT](LICENSE)
