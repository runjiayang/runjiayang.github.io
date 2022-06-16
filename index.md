## Welcome to GitHub Pages

<table border="0">
  <tr>
    <td width="75%">
      <h1>杨润甲</h1>
      <p><b>硕士研究生</b></p>
      <p><b>北京大学 数学科学学院学院 图像处理与重建（显微光学成像）</b></p>
      <p><b>邮箱：runjiayang@stu.pku.edu.cn</b></p>
      <p><b>TEL：13312065231</b></p>
    </td>
    <td width="20%">
      <img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/Photo.jpg?" width="100%">      
    </td>
  </tr>
</table>

## 教育经历
**北京大学**                  2020.09-至今

数学科学学院 应用数学 图像处理与重建（显微光学成像） 硕士研究生

专业课程： 数字信号处理、图像处理、模式识别、机器学习、统计与数据分析、算法分析与设计、系统与控制中的线性代数、 Python大数据分析原理与应用、自适应光学的数学理论及其应用等。

**天津大学**                   2016.09 – 2020.07

电子科学与技术（光电子技术）

专业课程： 几何光学、物理光学、信息光学、激光原理、非线性光学、光电子技术、光通信技术与原理、固体半导体物理、信号与系统、模拟电路、数字电路等

## 项目经历详述

<1> 共聚焦点扫描显微镜的光路设计、搭建、硬件控制与超分辨重建算法         

该项目为硕士研究生毕业课题，作为项目负责人，本人完成了该项目的光路设计，元件选型，光路搭建，系统标定，硬件控制与最终的超分辨算法重建，该项目的硬件和算法均由本人完成。

荧光显微镜具有特异性强，对比度高的特点。共聚焦显微镜(Confocal)是生命科学领域最广泛使用的荧光显微镜，其有着极大的产业化应用前景。 然而，对于Confocal而言，其只能达到光学衍射极限级别的分辨能力，为了进一步提高点扫描显微镜的分辨本领，我们使用了Image Scanning Mircoscopy技术，将Confocal的PMT更换为面阵相机，利用超分辨算法进一步提升分辨率。

- 光学、机械方面

本人完成了点扫描系统的光路设计，光学元件选型。由于光路复杂，需用Solidworks对光路中各部件的空间位置进行了建模仿真，防止出现空间干涉情况，并设计机械结构转接件来安装部分光机元件。
<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/systempath.png?raw=true" width="606%">  
</div>

<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/system_simulation.png?raw=true" width="60%">  
</div>

<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/system_image.jpg?raw=true" width="60%">  
</div>

- 超分辨重建算法方面
<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/Image%20Scanning%20Microscopy.png?raw=true" width="60%">  
</div>
如上图所示，通过将传统Confocal的点探测器（PMT）更换为面阵探测器，就可以使传统Confocal采集到的2D数据增维到4D数据，本课题中，超分辨重建算法要做的就是：**如何将获取到的4D数据按照某种最合适的规则重构出超分辨的2D数据**。

  - 正问题模型的建立
为了得到最合理的重分配方法，需要对成像正问题数学模型有清晰的了解
<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/math_problem.png?raw=true" width="60%">  
</div>
其正问题模型可以用如下公式表示

$$
PSF_{eff}(\mathbf{r,\delta_{shift}}) = PSF_{ex}(\mathbf{r})PSF_{det}(\mathbf{r-\delta_{shift}})
$$

  - 重建算法

目前我们的重建算法是基于以下两种规则来作为最优的重分配的方法：

a) 基于极大似然估计的Reassignment方法

b) 基于多视角解卷积的光子重分配方法

  - 重建结果展示

<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/ISM_result.png?raw=true" width="60%">  
</div>

(a), (b)Argo-SIM resolution pattern. The spacing between the lines increases gradually from 0 to 390 nm, with a step of 30 nm 前者为Confocal模式拍摄，后者为ISM模式拍摄，采样间隔：194.5nm (c)Confocal与ISM的对比 (d) (e) (f)为200nm的荧光微珠，激发波长为488nm，采样间隔135.5nm (g) 图中黄色线处的能量分布，图中数据的拍摄物镜为：Nikon CFI Plan Apochromat Lambda D 40X NA 0.95, Air，所有的图像仅使用了Pixel Reassignment，但没有进行解卷积

- 电控方面
系统中需要高速可控的时序控制，为此本人自学了STM32单片机，自制了一台可编程控制的信号发生器，用于系统的测试与成像。
<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/STM32.png?raw=true" width="60%">  
</div>

<2> 集成式片状光激发照明和全自动光片自动对准装置

作为项目负责人，完成集成式片状光激发照明的光学设计，原理性验证，并与国内知名显微物镜加工厂商对接需求，优化方案。同时，完成全自动对准装置的算法设计，位移台参数选型等工作。该项目正在审核的发明专利2篇，实用新型专利1篇（本人均为第2发明人），目前还有两篇发明专利待交局。

<3> 大视场落射均匀荧光激发成像系统
此项目为机器视觉尺度项目。作为项目负责人，完成大视场落射荧光激发成像系统的搭建，在光路中引入平顶光整形器，将高斯光束整形为平顶光束，提升激发光的照明均匀度。在后期完成了放大率标定等参数标定，目前该系统已用于菌落探针预筛选。
<div align=center>
<img src="https://github.com/runjiayang/runjiayang.github.io/blob/main/Images/machine_vis.png?raw=true" width="60%">  
</div>

<4> 基于正弦西门子星的MTF测量算法
本科毕业设计课题，本课题实现了基于正弦西门子星(Siemens Star)的光学系统MTF的测量算法，并提出“特征识别法”和“方差判断法”两种矫正西门子星中心的方法。此外，本课题还完成了基于刀口法和分辨率板的MTF测量。本课题的一部分工作发表在SPIE的会议论文期刊（ EI核心）。


You can use the [editor on GitHub](https://github.com/runjiayang/runjiayang.github.io/edit/main/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/runjiayang/runjiayang.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
