# hse_hw3_chromhmm
Bioinformatics 4 semester 3 homework

[Ссылка на колаб-ноубук](https://colab.research.google.com/drive/18vpMaF8UTjqc32R0d-hbZWOuU_sxG8D0?usp=sharing)

## Список гистоновых меток и имен файлов

В предыдущем домашнем задании мной была выбрана клеточная линия *IMR-90*. Однако для данной клеточной линии на сайте UCSC нет гистоновых меток, поэтому в данном задании возьмем клеточную линию *Dnd41* и исходя из этого выберем 10 гистоновых меток. Ниже будут перечисленны выбранные гистоновые метки и названия соответствующих файлов:  

Гистоновая метка   | Название файла 
------------------ | --------------------------------------------
H2AZ               | wgEncodeBroadHistoneDnd41H2azAlnRep2.bam
H3k27ac            | wgEncodeBroadHistoneDnd41H3k27acAlnRep2.bam
H3K27me3           | wgEncodeBroadHistoneDnd41H3k27me3AlnRep2.bam
H3K36me3           | wgEncodeBroadHistoneDnd41H3k36me3AlnRep2.bam
H3K4me1            | wgEncodeBroadHistoneDnd41H3k04me1AlnRep2.bam
H3K4me3            | wgEncodeBroadHistoneDnd41H3k04me3AlnRep2.bam
H3K79me2           | wgEncodeBroadHistoneDnd41H3k79me2AlnRep2.bam
H3K9ac             | wgEncodeBroadHistoneDnd41H3k09acAlnRep2.bam
H3K9me3            | wgEncodeBroadHistoneDnd41H3k09me3AlnRep2.bam
H4K20me1           | wgEncodeBroadHistoneDnd41H4k20me1AlnRep2.bam
Control            | wgEncodeBroadHistoneDnd41ControlStdAlnRep2.bam

## Содержание *cellmarkfiletable*

Ниже представленно содержимое файла *cellmarkfiletable.txt*, также он может быть найден в папке *data*:

<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/img/cellmaker_img.jpg width=500/>  

## Выдача ChromHMM
Ниже будут приаедены фотографии из HTML-файла, полученного от *ChromHMM*. Полная выдача находится в папке *data*.  

<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/data/ChromHMM_output/emissions_10.png width=300/>  
<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/data/ChromHMM_output/transitions_10.png width=300/>  
<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/data/ChromHMM_output/Dnd41_10_overlap.png width=300/>  
<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/data/ChromHMM_output/Dnd41_10_RefSeqTSS_neighborhood.png width=300/>  
<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/data/ChromHMM_output/Dnd41_10_RefSeqTES_neighborhood.png width=300/>  

## Эпигенетические типы

Далее будет представлена таблица, иллюстрирующая связь между состоянием и эпигенетическим типом. Также будет описаны наблюдения, касаемые рассматриваемых гистоновых меток. После таблици будут представлены скриншоты, демонстрирующие описанные связи.

Состояние | Тип                | Свойства 
--------- | ------------------ | --------------------------------------------
1         | Promoter           | *Активный промотор*, имеет сигнал на *H3K4me1*, *H2AZ*, *H3K4me3*, *H3K9ac*, *H3k27ac* и *H3K79me2*; Имеет большое количество CpG островков. 
2         | Heterochromatin    | *Межгенное пространство* (или *слабый энхансер*), имеет сигнал на *H3K4me1*, *H3k27ac*, *H2K9ac*, *H3K4me2*, *H2AZ*; ассоциирован с ядерной ламиной, но слабо.
3         | Enhancer           | *Энхансер*, сигнал на *H3K4me1*, *H3k27ac*, *H2K9ac*, *H3K4me2*, *H2AZ*; ассоциирован с ядерной ламиной, но слабо.
4         | Transcribed gene   | *Транскрибируемый участок в конце активного гена*, имеет сигнал на *H3K4me1*, *H3k27ac*, *H2K9ac*, *H3K4me2*, *H2AZ*, *H3K79me2*, *H4K20me1*; ассоциирован с TES, экзоном, активным геном и немного TSS.
5         | Transcribed gene   | *Транскрибируемый участок в активном гене*, имеет сигнал на *H3K79me2* и *H4K20me1*; ассоциирован с активным геном.
6         | Transcribed gene   | *Транскрибируемый участок в активном гене*, имеет сигнал на *H3K27me3*, *H3K79me2* и *H4K20me1*; ассоциирован с TES, экзоном и активным геном.
7         | Exon               | *Экзон в активном гене*, имеет сигнал на *H3K36me3*; ассоциирован с TES, экзоном и активным геном.
8         | Heterochromatin    | *Репрессированный гетерохроматин*, имеет сигнал на *H3K9me3*, *H3K79me2* и *H4K20me1*; ассоциирован с ядерной ламиной.
9         | Heterochromatin    | *Репрессированный гетерохроматин*, не имеет сигнала на метках, ассоциирован с ядерной ламиной.
10        | Heterochromatin    | *Репрессированный гетерохроматин*, имеет сигнал на *H3K79me3* и *H3K36me3*; ассоциирован с ядерной ламиной.


<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/img/epigen_1.jpg width=500/>  
<img src=https://github.com/TheMostKnown/hse_hw3_chromhmm/blob/main/img/epigen_2.jpg width=500/>  

## Бонусная часть

Код бонусной части представлен в колаб-ноутбуке. Реузьтат представлен на скриншоте ниже:

![image](https://user-images.githubusercontent.com/65551462/160953765-77f5bde7-958b-4ffe-b3dd-97cbef665cf1.png)  

