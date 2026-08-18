# 试作音Demo DiffSinger

[English](https://github.com/tuskinekinase/shisakunedemo_ds/blob/main/README.md) | 中文

## 介绍
试作音Demo（席黛墨）DiffSinger是基于DiffSinger歌声合成技术的高质量多音色AI歌声合成模型。可配合OpenUtau使用。

关于DiffSinger：

https://github.com/openvpi/DiffSinger

关于OpenUtau：

https://www.openutau.com/

https://github.com/openutau/OpenUtau

## 使用手册
#### 安装

1.  使用前，请确保OpenUtau已安装DiffSinger专用的NSF-HiFiGAN声码器。详情请参见：https://github.com/openvpi/vocoders
2.  下载包含本歌声合成模型及相关文件的.zip格式压缩包。
3.  将压缩包拖入OpenUtau主界面，并按照窗口提示完成安装。

#### 轨道设置

1.  在多轨道视图中，将选定轨道的歌手设为已安装的试作音Demo（Shisakune Demo）DiffSinger模型。
2.  将音素器（Phonemizer）设定为以下四种之一：
	1. DIFFS ZH（汉语）
	2. DIFFS EN（英语）
	3. DIFFS JA（日语）
	4. DIFFS（混合字典，可使用汉语拼音、英语、日语平假名输入）
3.  将引擎（Engine）设定为DiffSinger。

单击选定轨道创建新的片段。双击选定轨道上的片段，打开钢琴卷轴界面。

#### 调声
在OpenUtau中使用DiffSinger音源的方式与使用UTAU音源的方式类似，具体使用方法请参见[OpenUtau维基](http://opensynth.miraheze.org/wiki/OpenUTAU)。

##### 参数
参数在钢琴卷轴窗口底部编辑。左下角切换参数。钢琴卷轴窗口与参数窗口之间为音素窗口，可直接拖动音素长度、起始位置，也可编辑音素。

试作音Demo DiffSinger 4.5以后版本支持以下选项参数：
|名称|缩写|说明|选项|默认值|
|---|---|---|---|---|
|voice color|CLR|音素级调用不同音色。|Smooth、Solid、Symphonic|Smooth|	

试作音Demo DiffSinger 4.5以后版本支持以下曲线参数：
|名称|缩写|说明|范围|默认值|
|---|---|---|---|---|
|dynamics(curve)|DYN|音量控制曲线。范围对应-24dB~12dB|-240~120|0|
|velocity(curve)|VELC|速度曲线。|0~200|100|
|pitch deviation(curve)|PIT|音高偏移曲线。可以在钢琴窗中通过音高工具直接绘制|-1200~1200|0|
|gender(curve)|GENC|性别参数曲线。|-100~100|0|
|breathiness(curve)|BREC|气声。|-100~100|0|
|tension(curve)|TENC|张力。|-100~100|0|
|voicing(curve)|VOIC|发声共鸣度。|0~200（默认范围最大值为100，可点击左下角齿轮设置范围）|100|
|voice color smooth|CL01|Smooth（柔和，默认）音色的控制曲线。与CLR搭配使用。|0-100|0|
|voice color solid|CL02|Solid（强力）音色的控制曲线。与CLR搭配使用。|0-100|0|
|voice color symphonic|CL03|Symphonic（美声）音色的控制曲线。与CLR搭配使用。|0-100|0|

##### 自动音高
试作音Demo DiffSinger 4.5及以后版本支持自动音高功能。选中需要渲染的音符，在菜单栏Batch Edits（批量编辑）选项中选择Notes->Load rendered pitch选项，进行自动音高推理。
> DiffSinger的自动音高渲染以音素彼此相连的句子为单位。仅选中句子中的部分音符进行自动音高渲染，整个句子的音高线都会被重新渲染。

#### 多语种合成
试作音Demo DiffSinger 4.5及以后版本支持汉语、英语和日语三种语言合成。可使用OpenUtau v0.1.565以后版本的DIFFS ZH/DIFFS EN/DIFFS JA分语言音素字典，也可使用DIFFS混合字典，在同一音轨中混合输出三种语言。

推荐的歌词输入方法：
- 汉语（DIFFS ZH）：汉语拼音（推荐），汉字
- 英语（DIFFS EN）：英文拼写。
> 部分英语词汇支持多个发音，可通过(1)后缀调取。（例：record(1)）
- 日语（DIFFS JA）：平假名、罗马字
- 混合（DIFFS）：所有三个语种的单词共存于一个融合字典中。
	- 使用混合字典时，日语只支持平假名输入。当英语与汉语拼音拼写冲突时，以汉语拼音为优先。使用EN前缀以调出与汉语拼音拼写冲突的英语音素。（例：sing，ENsong）
>在混合字典中，所有音素都可通过“[]”中输入音素的方式直接调取。（例：[en/s en/ih en/ng]）

##### 音素列表
汉语普通话
|	音素符号	|	汉语拼音	|
|	---	|	---	|
|	zh/a	|	a	|	 
|	zh/ai	|	ai	|
|	zh/an	|	an	|
|	zh/ang	|	ang	|
|	zh/ao	|	ao	|
|	zh/b	|	b	|
|	zh/c	|	c	|
|	zh/ch	|	ch	|
|	zh/d	|	d	|
|	zh/e	|	e	|
|	zh/ei	|	ei	|
|	zh/en	|	en	|
|	zh/ueng	|	(w)eng	|
|	zh/eng	|	eng	|
|	zh/er	|	er	|
|	zh/f	|	f	|
|	zh/g	|	g	|
|	zh/h	|	h	|
|	zh/i	|	i	|
|	zh/i0	|	i0	|
|	zh/ia	|	ia	|
|	zh/ian	|	ian	|
|	zh/iang	|	iang	|
|	zh/iao	|	iao	|
|	zh/ie	|	ie	|
|	zh/in	|	in	|
|	zh/ing	|	ing	|
|	zh/io	|	(y)o	|
|	zh/iong	|	iong	|
|	zh/ir	|	(zh/ch/sh/r)i	|
|	zh/iu	|	iu	|
|	zh/j	|	j	|
|	zh/k	|	k	|
|	zh/l	|	l	|
|	zh/m	|	m	|
|	zh/n	|	n	|
|	zh/o	|	o	|
|	zh/ong	|	ong	|
|	zh/ou	|	ou	|
|	zh/p	|	p	|
|	zh/q	|	q	|
|	zh/r	|	r	|
|	zh/s	|	s	|
|	zh/sh	|	sh	|
|	zh/t	|	t	|
|	zh/u	|	u	|
|	zh/ua	|	ua	|
|	zh/uai	|	uai	|
|	zh/uan	|	uan	|
|	zh/uang	|	uang	|
|	zh/ui	|	ui	|
|	zh/un	|	un	|
|	zh/uo	|	uo	|
|	zh/v	|	ü	|
|	zh/van	|	üan	|
|	zh/ve	|	üe	|
|	zh/vn	|	ün	|
|	zh/w	|	w	|
|	zh/x	|	x	|
|	zh/y	|	y	|
|	zh/y0	|	y(ü)	|
|	zh/z	|	z	|
|	zh/zh	|	zh	|

英语（美式）
|	音素符号	|	IPA音标	|
|	---	|	---	|
|	en/\_r	|	(t)r，(d)r	|
|	en/aa	|	ɑ	|
|	en/ae	|	æ	|
|	en/ah	|	ʌ	|
|	en/ao	|	ɔ	|
|	en/aw	|	aʊ	|
|	en/ax	|	ə	|
|	en/ay	|	aɪ	|
|	en/b	|	b	|
|	en/ch	|	tʃ，t(r)	|
|	en/d	|	d	|
|	en/dh	|	ð	|
|	en/dx	|	ɾ	|
|	en/eh	|	ɛ	|
|	en/er	|	ɚ	|
|	en/ey	|	eɪ	|
|	en/f	|	f	|
|	en/g	|	g	|
|	en/hh	|	h	|
|	en/ih	|	ɪ	|
|	en/iy	|	i	|
|	en/jh	|	dʒ，d(r)	|
|	en/k	|	k	|
|	en/l	|	l	|
|	en/m	|	m	|
|	en/n	|	n	|
|	en/ng	|	ŋ	|
|	en/ow	|	oʊ	|
|	en/oy	|	ɔɪ	|
|	en/p	|	p	|
|	en/r	|	r	|
|	en/s	|	s	|
|	en/sh	|	ʃ	|
|	en/t	|	t	|
|	en/th	|	θ	|
|	en/uh	|	ʊ	|
|	en/uw	|	u	|
|	en/v	|	v	|
|	en/w	|	w	|
|	en/y	|	j	|
|	en/z	|	z	|
|	en/zh	|	ʒ	|

日语
|	音素符号	|	罗马字	|
|	---	|	---	|
|	ja/a	|	a	|
|	ja/b	|	b	|
|	ja/by	|	by	|
|	ja/ch	|	ch	|
|	ja/d	|	d	|
|	ja/dy	|	dy	|
|	ja/e	|	e	|
|	ja/f	|	f	|
|	ja/F	|	f (ɸ)	|
|	ja/g	|	g	|
|	ja/gy	|	gy	|
|	ja/h	|	h	|
|	ja/hy	|	hy	|
|	ja/I	|	i（不发音）	|
|	ja/i	|	i	|
|	ja/j	|	j	|
|	ja/k	|	k	|
|	ja/ky	|	ky	|
|	ja/m	|	m	|
|	ja/my	|	my	|
|	ja/N	|	n（音节用）	|
|	ja/n	|	n（辅音用）	|
|	ja/ny	|	ny	|
|	ja/o	|	o	|
|	ja/p	|	p	|
|	ja/py	|	py	|
|	ja/r	|	r	|
|	ja/ry	|	ry	|
|	ja/s	|	s	|
|	ja/sh	|	sh	|
|	ja/t	|	t	|
|	ja/ts	|	ts	|
|	ja/ty	|	ty	|
|	ja/U	|	u（不发音）	|
|	ja/u	|	u	|
|	ja/v	|	v	|
|	ja/w	|	w	|
|	ja/y	|	y	|
|	ja/z	|	z	|

特殊符号：
- SP（无声音，空白）
- AP（吸气音）
- CL（日语的促音间隙）

## 参与贡献

声源提供：幽寂

数据处理：久嘉

数据标注：幽寂、久嘉

模型训练：久嘉

角色设计：幽寂

立绘制作：幽寂

本声库在开发过程中使用了以下公开与非公开数据库作为增强数据：
-  [Natsume Yuuri](https://ksdcm1ng.wixsite.com/njksofficial)
-  [NebulaMeadow](https://x.com/NebulaMeadow)

对以上数据库的使用均已经过相应权利人的授权。
