# Shisakune Demo DiffSinger

## Introduction
Shisakune Demo (also known as: 试作音デモ, 试作音Demo, 席黛墨) DiffSinger is a high-quality AI singing voice synthesizing model based on DiffSinger. This model uses OpenUtau as renderer.

About DiffSinger：

https://github.com/openvpi/DiffSinger

About OpenUtau：

https://www.openutau.com/

https://github.com/stakira/OpenUtau

## User Manual

#### Installation

1.  Before use, please ensure that the lastest NSF-HiFiGAN vocoder for DiffSinger is already installed in OpenUtau. About this vocoder: https://github.com/openvpi/vocoders
2.  Download the .zip files in the Release page of this repository.
3.  Drag the .zip file into the main UI window of OpenUtau, and finish installation according to prompts.

#### Track Setup

1.  In OpenUtau's multitrack view, select the installed Shisakune Demo DiffSinger model as the active singer.
2.  Select DIFFS as the active phonemizer. Shisakune Demo DiffSinger uses a custom dictionary that comes with the model package, which is only supported by DIFFS.
3.  Select DiffSinger as the active engine.

Click on the selected track to create a new part. Double-click on the part on the selected track to open the piano roll interface.

#### Tuning
The way to use DiffSinger model in OpenUtau is similar to using UTAU voicebank in OpenUtau. For detailed guide, please refer to [OpenUtau Wiki](https://github.com/stakira/OpenUtau/wiki).

##### Expressions
Expression (parameters) panel is located at the bottom of the piano roll window. Switch active expressions and edit expression settings in the lower left corner. Between the piano roll window and the expressions panel is the phoneme panel, where you can drag to edit honeme length, start position, and edit phoneme names.

Shisakune Demo DiffSinger 3.0 and later versions support the following option parameters:
|Name|Abbrv.|Description|Options|Default|
|---|---|---|---|---|
|voice color|CLR|Switch to a different voice color on a per-phoneme basis|Smooth、Solid、Symphonic|Smooth|	

Shisakune Demo DiffSinger 3.0 and later versions support the following curve parameters：
|Name|Abbrv.|Description|Range|Default|
|---|---|---|---|---|
|dynamics(curve)|DYN|Volume control. The range corresponds to -24dB~12dB.|-240~120|0|
|velocity(curve)|VELC|Velocity control.|0~200|100|
|pitch deviation(curve)|PIT|Pitch deviation. Can be drawn directly in the piano roll window using Pitch Tool|-1200~1200|0|
|gender(curve)|GENC|Gender parameter control.|-100~100|0|
|breathiness(curve)|BREC|Breathiness control.|-100~100|0|
|tension(curve)|TENC|Tension. Not compatible with VOIC in the same model package. Please refer to the model file name.|-100~100|0|
|voicing(curve)|VOIC|Voicing. Not compatible with TENC in the same model package. Please refer to the model file name.|0~200(The default maximum range is 100, you can click on the gear in the lower left corner to set custom range)|100|
|voice color smooth|CL01|Smooth (default) voice color control. Use in tandem with CLR.|0-100|0|
|voice color solid|CL02|Solid voice color control. Use in tandem with CLR.|0-100|0|
|voice color symphonic|CL03|Symphonic (operatic) voice color control. Use in tandem with CLR.|0-100|0|

##### Automatic Pitch
Shisakune Demo DiffSinger 3.0 and later versions support automatic pitch. Select the notes to be rendered, then, in the Batch Edits menu, select Notes->Load rendered pitch to render automatic pitch.
> DiffSinger's automatic pitch rendering is based on a per sentence basis. Sentences are note segments with continuously connected phonemes. If you only select some notes in a sentence for automatic pitch rendering, the pitch of the entire sentence will be re-rendered.

#### Multilingual Synthesis
In Shisakune Demo DiffSinger 3.1 and later versions, the Native versions can synthesize Mandarin Chinese and English, while the Multi versions can synthesize Mandarin Chinese, English, Japanese and French. Please refer to the model file name for the applicable languages.

The default language is Mandarin Chinese.

Recommended lyrics input method:
- Chinese: Pinyin (recommended), Chinese characters
- English: English spelling. Note: When English and Pinyin spelling conflict, Pinyin takes precedence. Use EN+English spelling to call out English phonemes. (Example: sing, ENsong)
> In versions 3.1 and later, some English words support multiple pronunciations, which can be called up through the (1) suffix. (Example: record(1))
- Japanese (not supported in some versions): Hiragana
- French (not supported in some versions): FR+French spelling (Example: FRchanter)

Phonemes of all languages ​​coexist in a fusion dictionary, which can be directly accessed by entering phonemes in "[]". (Example: [s IH NG])

##### Phoneme Guide
Mandarin Chinese
|	Phoneme label	|	Language	|	Pinyin	|
|	---	|	---	|	---	|
|	E	|	zh	|	Vowel part of "ye"|
|	En	|	zh	|	Vowel part of "yan"|
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

English (GenAm)
|	Phoneme label	|	Language	|	IPA	|
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

Japanese
|	Phoneme label	|	Language	|	Romaji	|
|	---	|	---	|	---	|
|	A	|	ja	|	a	|
|	I	|	ja	|	i	|
|	U	|	ja	|	u	|
|	E1	|	ja	|	e	|
|	O	|	ja	|	o	|
|	I.	|	ja	|	i (devoiced)	|
|	U.	|	ja	|	u (devoiced)	|
|	b1	|	ja	|	b	|
|	d1	|	ja	|	d	|
|	G	|	ja	|	g	|
|	HH	|	en/ja	|	h	|
|	J	|	ja	|	j	|
|	K	|	ja	|	k	|
|	m	|	zh/en/ja/fr	|	m	|
|	n	|	zh/ja	|	n (consonant)    |
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
|	nn	|	ja	|	n (moraic)	|
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

French
|	Phoneme label	|	Language	|	IPA	|
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
-  [Millefeuille French DiffSinger Language Support](https://github.com/imsupposedto/Millefeuille-DiffSinger-French)
-  [NebulaMeadow](https://x.com/NebulaMeadow)

The use of the above databases has been authorized by the corresponding rights holders.
