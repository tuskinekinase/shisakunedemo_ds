# Shisakune Demo DiffSinger

English | [中文](https://github.com/tuskinekinase/shisakunedemo_ds/blob/main/README_zh.md)

## Introduction
Shisakune Demo (also known as: 试作音デモ, 试作音Demo, 席黛墨) DiffSinger is a high-quality AI singing voice synthesizing model based on DiffSinger. This model uses OpenUtau as renderer.

About DiffSinger：

https://github.com/openvpi/DiffSinger

About OpenUtau：

https://www.openutau.com/

https://github.com/openutau/OpenUtau

## User Manual

#### Installation

1.  Before use, please ensure that the lastest NSF-HiFiGAN vocoder for DiffSinger is already installed in OpenUtau. About this vocoder: https://github.com/openvpi/vocoders
2.  Download the .zip files in the Release page of this repository.
3.  Drag the .zip file into the main UI window of OpenUtau, and finish installation according to prompts.

#### Track Setup

1.  In OpenUtau's multitrack view, select the installed Shisakune Demo DiffSinger model as the active singer.
2.  Select one of the following as the active phonemizer:
	1. DIFFS ZH (Mandarin Chinese)
	2. DIFFS EN (English)
	3. DIFFS JA (Japanese)
	4. DIFFS (a mixed dictionary that contains Mandarin Chinese, English and Japanese. Supports Pinyin, English and hiragana input.)
3.  Select DiffSinger as the active engine.

Click on the selected track to create a new part. Double-click on the part on the selected track to open the piano roll interface.

#### Tuning
The way to use DiffSinger model in OpenUtau is similar to using UTAU voicebank in OpenUtau. For detailed guide, please refer to [OpenUtau Wiki](https://github.com/stakira/OpenUtau/wiki).

##### Expressions
Expression (parameters) panel is located at the bottom of the piano roll window. Switch active expressions and edit expression settings in the lower left corner. Between the piano roll window and the expressions panel is the phoneme panel, where you can drag to edit honeme length, start position, and edit phoneme names.

Shisakune Demo DiffSinger 4.5 and later versions support the following option parameters:
|Name|Abbrv.|Description|Options|Default|
|---|---|---|---|---|
|voice color|CLR|Switch to a different voice color on a per-phoneme basis|Smooth, Solid, Symphonic|Smooth|	

Shisakune Demo DiffSinger 4.5 and later versions support the following curve parameters：
|Name|Abbrv.|Description|Range|Default|
|---|---|---|---|---|
|dynamics(curve)|DYN|Volume control. The range corresponds to -24dB~12dB.|-240~120|0|
|velocity(curve)|VELC|Velocity control.|0~200|100|
|pitch deviation(curve)|PIT|Pitch deviation. Can be drawn directly in the piano roll window using Pitch Tool|-1200~1200|0|
|gender(curve)|GENC|Gender parameter control.|-100~100|0|
|breathiness(curve)|BREC|Breathiness control.|-100~100|0|
|tension(curve)|TENC|Tension.|-100~100|0|
|voicing(curve)|VOIC|Voicing.|0~200(The default maximum range is 100, you can click on the gear in the lower left corner to set custom range)|100|
|voice color smooth|CL01|Smooth (default) voice color control. Use in tandem with CLR.|0-100|0|
|voice color solid|CL02|Solid voice color control. Use in tandem with CLR.|0-100|0|
|voice color symphonic|CL03|Symphonic (operatic) voice color control. Use in tandem with CLR.|0-100|0|

##### Automatic Pitch
Shisakune Demo DiffSinger 4.5 and later versions support automatic pitch. Select the notes to be rendered, then, in the Batch Edits menu, select Notes->Load rendered pitch to render automatic pitch.
> DiffSinger's automatic pitch rendering is based on a per sentence basis. Sentences are note segments with continuously connected phonemes. If you only select some notes in a sentence for automatic pitch rendering, the pitch of the entire sentence will be re-rendered.

#### Multilingual Synthesis
Shisakune Demo DiffSinger 4.5 and later versions support the synthesis of Mandarin Chinese, English and Japanese. You can either use the DIFFS ZH/DIFFS EN/DIFFS JA phonemizers from OpenUtau v0.1.565 and later, or our built-in DIFFS mixed phonemizer to synthesize all three languages in the same track.

Recommended lyrics input method:
- Chinese (DIFFS ZH): Pinyin (recommended), Chinese characters
- English (DIFFS EN): English spelling. Note: When English and Pinyin spelling conflict, Pinyin takes precedence. Use EN+English spelling to call out English phonemes. (Example: sing, ENsong)
> some English words support multiple pronunciations, which can be called up through the (1) suffix. (Example: record(1))
- Japanese (DIFFS JA): Hiragana, Romaji
- Mixed (DIFFS): Words from all three phonemizers in the same fusion dictionary. 
	- When using the DIFFS mixed phonemizer, only hiragana input is supported for Japanese. When English and Pinyin spelling conflict, Pinyin takes precedence. Use EN prefix to call out English phonemes for words in conflict with Pinyin spelling. (Example: sing, ENsong)
>In the DIFFS mized phonemizer, phonemes of all languages ​​coexist in a fusion dictionary, which can be directly accessed by entering phonemes in "[]". (Example: [en/s en/ih en/ng])

##### DIFFS Phoneme Guide
Mandarin Chinese (ZH)
|	Phoneme label	|	Pinyin	|
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

English (EN)
|	Phoneme label	|	IPA	|
|	---	|	---	|
|	en/\_r	|	(t)r, (d)r	|
|	en/aa	|	ɑ	|
|	en/ae	|	æ	|
|	en/ah	|	ʌ	|
|	en/ao	|	ɔ	|
|	en/aw	|	aʊ	|
|	en/ax	|	ə	|
|	en/ay	|	aɪ	|
|	en/b	|	b	|
|	en/ch	|	tʃ, t(r)	|
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
|	en/jh	|	dʒ, d(r)	|
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

Japanese (JA)
|	Phoneme label	|	Romaji	|
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
|	ja/I	|	i (devoiced)	|
|	ja/i	|	i	|
|	ja/j	|	j	|
|	ja/k	|	k	|
|	ja/ky	|	ky	|
|	ja/m	|	m	|
|	ja/my	|	my	|
|	ja/N	|	n (moraic)	|
|	ja/n	|	n (consonant)	|
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
|	ja/U	|	u (devoiced)	|
|	ja/u	|	u	|
|	ja/v	|	v	|
|	ja/w	|	w	|
|	ja/y	|	y	|
|	ja/z	|	z	|

Special symbols:
- SP (Space)
- AP (Aspiration)
- CL (Japanese sokuon stop)

## Contribution

Voice Provider: UG (SnowbootP, tuskinekinase)

Data processing: Hisaka ([hrukalive](https://github.com/hrukalive))

Data labeling: UG, Hisaka

Training: Hisaka

Character design: UG

Splash art: UG

The following public and private databases were used as augment data during the development of this model:
-  [Natsume Yuuri](https://ksdcm1ng.wixsite.com/njksofficial)
-  [NebulaMeadow](https://x.com/NebulaMeadow)

The use of the above databases has been authorized by the corresponding rights holders.
