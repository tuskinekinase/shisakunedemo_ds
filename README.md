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

1.  Before installation, please ensure that the lastest NSF-HiFiGAN vocoder for DiffSinger is already installed in OpenUtau. About this vocoder: https://github.com/openvpi/vocoders
2.  Download the .zip files in the Release page of this repository.
3.  Drag the .zip file into the main UI window of OpenUtau, and finish installation according to prompts.

#### Track Setup

1.  In OpenUtau's track view, select the installed Shisakune Demo DiffSinger model as the active singer.
2.  Select DIFFS as the active phonemizer. Shisakune Demo DiffSinger uses a custom dictionary that comes with the model package, which is only supported by DIFFS.
3.  Select DiffSinger as the active engine.

#### Tuning


#### Phoneme Guide


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
