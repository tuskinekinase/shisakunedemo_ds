# 试作音Demo DiffSinger

## 介绍
试作音Demo（席黛墨）DiffSinger是基于DiffSinger歌声合成技术的高质量多音色AI歌声合成模型。可配合OpenUtau使用。

关于DiffSinger：

https://github.com/openvpi/DiffSinger

关于OpenUtau：

https://www.openutau.com/

https://github.com/stakira/OpenUtau

## 使用手册
#### 安装

1.  使用前，请确保OpenUtau已安装DiffSinger专用的NSF-HiFiGAN声码器。详情请参见：https://github.com/openvpi/vocoders
2.  下载包含本歌声合成模型及相关文件的.zip格式压缩包。
3.  将压缩包拖入OpenUtau主界面，并按照窗口提示完成安装。

#### 轨道设置

1.  在多轨道视图中，将选定轨道的歌手设为已安装的试作音Demo（Shisakune Demo）DiffSinger模型。
2.  将音素器（Phonemizer）设定为DIFFS。试作音Demo DiffSinger使用自带的融合字典，必须使用DIFFS作为音素器，否则将无法正确识别音素。
3.  将引擎（Engine）设定为DiffSinger。

单击选定轨道创建新的片段。双击选定轨道上的片段，打开钢琴卷轴界面。

#### 调声
在OpenUtau中使用DiffSinger音源的方式与使用UTAU音源的方式类似，具体使用方法请参见[OpenUtau维基](http://opensynth.miraheze.org/wiki/OpenUTAU)。

##### 参数
参数在钢琴卷轴窗口底部编辑。左下角切换参数。钢琴卷轴窗口与参数窗口之间为音素窗口，可直接拖动音素长度、起始位置，也可编辑音素。

试作音Demo DiffSinger 3.0以后版本支持以下选项参数：
|名称|缩写|说明|选项|默认值|
|---|---|---|---|---|
|voice color|CLR|音素级调用不同音色。|Smooth、Solid、Symphonic|Smooth|	

试作音Demo DiffSinger 3.0以后版本支持以下曲线参数：
|名称|缩写|说明|范围|默认值|
|---|---|---|---|---|
|dynamics(curve)|DYN|音量控制曲线。范围对应-24dB~12dB|-240~120|0|
|velocity(curve)|VELC|速度曲线。|0~200|100|
|pitch deviation(curve)|PIT|音高偏移曲线。可以在钢琴窗中通过音高工具直接绘制|-1200~1200|0|
|gender(curve)|GENC|性别参数曲线。|-100~100|0|
|breathiness(curve)|BREC|气声。|-100~100|0|
|tension(curve)|TENC|张力。不与voicing同时适用，请参看模型文件名选用。|-100~100|0|
|voicing(curve)|VOIC|发声共鸣度。不与tension同时适用，请参看模型文件名选用。|0~200（默认范围最大值为100，可点击左下角齿轮设置范围）|100|
|voice color smooth|CL01|Smooth（柔和，默认）音色的控制曲线。与CLR搭配使用。|0-100|0|
|voice color solid|CL02|Solid（强力）音色的控制曲线。与CLR搭配使用。|0-100|0|
|voice color symphonic|CL03|Symphonic（美声）音色的控制曲线。与CLR搭配使用。|0-100|0|

##### 自动音高
试作音Demo DiffSinger 3.0以后版本支持自动音高功能。选中需要渲染的音符，在菜单栏Batch Edits（批量编辑）选项中选择Notes->Load rendered pitch选项，进行自动音高推理。
> DiffSinger的自动音高渲染以音素彼此相连的句子为单位。仅选中句子中的部分音符进行自动音高渲染，整个句子的音高线都会被重新渲染。

#### 多语种合成
试作音Demo DiffSinger3.1以后版本中，Native版能够合成汉语普通话与英语，而Multi版能够合成汉语普通话、英语、日语与法语，请参看模型文件名进行选用。

默认语言为汉语普通话。

推荐的歌词输入方法：
- 汉语：汉语拼音（推荐），汉字
- 英语：英文拼写。注：当英语与汉语拼音拼写冲突时，以汉语拼音为优先。使用EN+英语拼写以调出英语音素。（例：sing，ENsong）
> 3.1以后版本中，部分英语词汇支持多个发音，可通过(1)后缀调取。（例：record(1)）
- 日语（部分版本不支持）：平假名
- 法语（部分版本不支持）：FR+法文拼写（例：FRchanter）

所有语种的音素共存于一个融合字典中，可通过“[]”中输入音素的方式直接调取。（例：[s IH NG]）

##### 音素列表
汉语普通话
|	音素符号	|	适用语言	|	汉语拼音	|
|	---	|	---	|	---	|
|	E	|	zh	|	ye的元音部分	|
|	En	|	zh	|	yan的元音部分	|
|	a	|	zh	|	a	|
|	ai	|	zh	|	ai	|
|	an	|	zh	|	an	|
|	ang	|	zh	|	ang	|
|	ao	|	zh	|	ao	|
|	e	|	zh	|	e	|
|	ei	|	zh	|	ei	|
|	en	|	zh	|	en	|
|	eng	|	zh	|	eng	|
|	er	|	zh	|	er	|
|	i	|	zh	|	i	|
|	i0	|	zh	|	i0	|
|	ia	|	zh	|	ia	|
|	ian	|	zh	|	ian	|
|	iang	|	zh	|	iang	|
|	iao	|	zh	|	iao	|
|	ie	|	zh	|	ie	|
|	in	|	in	|	in	|
|	ing	|	zh	|	ing	|
|	iong	|	zh	|	iong	|
|	ir	|	zh	|	ir	|
|	iu	|	zh	|	iu	|
|	o	|	zh	|	o	|
|	ong	|	zh	|	ong	|
|	ou	|	zh	|	ou	|
|	u	|	zh	|	u	|
|	ua	|	zh	|	ua	|
|	uai	|	zh	|	uai	|
|	uan	|	zh	|	uan	|
|	uang	|	zh	|	uang	|
|	ui	|	zh	|	ui	|
|	un	|	zh	|	un	|
|	uo	|	zh	|	uo	|
|	v	|	zh	|	ü	|
|	van	|	zh	|	üan	|
|	ve	|	zh	|	üe	|
|	vn	|	zh	|	ün	|
|	b	|	zh	|	b	|
|	c	|	zh	|	c	|
|	ch	|	zh	|	ch	|
|	d	|	zh	|	d	|
|	f	|	zh/ja/en/fr	|	f	|
|	g	|	zh	|	g	|
|	h	|	zh	|	h	|
|	j	|	zh	|	j	|
|	k	|	zh	|	k	|
|	l	|	zh	|	l	|
|	m	|	zh/ja/en/fr	|	m	|
|	n	|	zh	|	n	|
|	p	|	zh	|	p	|
|	q	|	zh	|	q	|
|	r	|	zh	|	r	|
|	s	|	zh/ja/en/fr	|	s	|
|	sh	|	zh	|	sh	|
|	t	|	zh	|	t	|
|	w	|	zh	|	w	|
|	x	|	zh	|	x	|
|	y	|	zh	|	y	|
|	z	|	zh	|	z	|
|	zh	|	zh	|	zh	|

英语（美式）
|	音素符号	|	适用语言	|	IPA音标	|
|	---	|	---	|	---	|
|	AA	|	en	|	ɑ	|
|	AE	|	en	|	æ	|
|	AH	|	en	|	ʌ	|
|	AO	|	en	|	ɔ	|
|	AW	|	en	|	aʊ	|
|	AX	|	en	|	ɚ	|
|	AY	|	en	|	aɪ	|
|	EH	|	en	|	ɛ	|
|	ER	|	en	|	ər	|
|	EY	|	en	|	eɪ	|
|	IH	|	en	|	ɪ	|
|	IY	|	en	|	i	|
|	OW	|	en	|	oʊ	|
|	OY	|	en	|	ɔɪ	|
|	UH	|	en	|	ʊ	|
|	UW	|	en	|	u	|
|	B	|	en	|	b	|
|	CH	|	en	|	tʃ	|
|	D	|	en	|	d	|
|	DH	|	en	|	ð	|
|	DX	|	en	|	ɾ	|
|	DR	|	en	|	dr	|
|	f	|	zh/ja/en/fr	|	f	|
|	HH	|	en/ja	|	h	|
|	JH	|	en	|	dʒ	|
|	L	|	en	|	l	|
|	m	|	zh/ja/en/fr	|	m	|
|	N	|	en	|	n	|
|	NG	|	en	|	ŋ	|
|	P	|	en	|	p	|
|	R	|	en	|	r	|
|	SH	|	en	|	ʃ	|
|	T	|	en	|	t	|
|	TH	|	en	|	θ	|
|	TR	|	en	|	tr	|
|	W	|	en	|	w	|
|	Y	|	en	|	j	|
|	Z	|	en	|	z	|
|	ZH	|	en	|	ʒ	|

日语
|	音素符号	|	适用语言	|	罗马字	|
|	---	|	---	|	---	|
|	A	|	ja	|	a	|
|	I	|	ja	|	i	|
|	U	|	ja	|	u	|
|	E1	|	ja	|	e	|
|	O	|	ja	|	o	|
|	I.	|	ja	|	i（不发音）	|
|	U.	|	ja	|	u（不发音）	|
|	b1	|	ja	|	b	|
|	d1	|	ja	|	d	|
|	G	|	ja	|	g	|
|	HH	|	en/ja	|	h	|
|	J	|	ja	|	j	|
|	K	|	ja	|	k	|
|	m	|	zh/en/ja/fr	|	m	|
|	n	|	zh/ja	|	n（辅音用）	|
|	p1	|	ja	|	p	|
|	t1	|	ja	|	t	|
|	V	|	ja	|	v	|
|	y1	|	ja	|	y	|
|	z1	|	ja	|	z	|
|	ch1	|	ja	|	ch	|
|	F	|	ja	|	f	|
|	r1	|	ja	|	r	|
|	s	|	zh/en/ja/fr	|	s	|
|	sh1	|	ja	|	sh	|
|	ts	|	ja	|	ts	|
|	nn	|	ja	|	n（音节用）	|
|	ky	|	ja	|	ky	|
|	gy	|	ja	|	gy	|
|	ty	|	ja	|	ty	|
|	dy	|	ja	|	dy	|
|	hy	|	ja	|	hy	|
|	by	|	ja	|	by	|
|	my	|	ja	|	my	|
|	ny	|	ja	|	ny	|
|	py	|	ja	|	py	|
|	ry	|	ja	|	ry	|

法语
|	音素符号	|	适用语言	|	IPA音标	|
|	---	|	---	|	---	|
|	ah4	|	fr	|	a/ɑ	|
|	eh4	|	fr	|	e	|
|	ae4	|	fr	|	ɛ/ɛ:	|
|	ee	|	fr	|	ə/ø	|
|	oe	|	fr	|	œ	|
|	ih4	|	fr	|	i	|
|	oh	|	fr	|	o	|
|	oo	|	fr	|	ɔ	|
|	ou4	|	fr	|	u	|
|	uh4	|	fr	|	y	|
|	en4	|	fr	|	ɑ̃	|
|	in4	|	fr	|	ɛ̃/œ̃	|
|	un4	|	fr	|	œ̃	|
|	on4	|	fr	|	ɔ̃	|
|	uy	|	fr	|	ɥ	|
|	b4	|	fr	|	b	|
|	d4	|	fr	|	d	|
|	f	|	zh/en/fr	|	f	|
|	g4	|	fr	|	g	|
|	k4	|	fr	|	k	|
|	l4	|	fr	|	l	|
|	m	|	zh/en/ja/fr	|	m	|
|	n4	|	fr	|	n	|
|	p4	|	fr	|	p	|
|	r4	|	fr	|	ʁ	|
|	s	|	zh/en/ja/fr	|	s	|
|	t4	|	fr	|	t	|
|	v4	|	fr	|	v	|
|	j4	|	fr	|	ʒ	|
|	y4	|	fr	|	j	|
|	w4	|	fr	|	w	|
|	ng4	|	fr	|	ŋ	|
|	rx	|	fr	|	r	|

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
-  [Millefeuille French DiffSinger Language Support](https://github.com/imsupposedto/Millefeuille-DiffSinger-French)
-  [NebulaMeadow](https://x.com/NebulaMeadow)

对以上数据库的使用均已经过相应权利人的授权。

