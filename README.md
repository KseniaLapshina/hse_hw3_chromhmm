# hse_hw3_chromhmm

Клеточная линия в задании ChIP-seq: GM23338

Среди доступных на https://genome.ucsc.edu/ENCODE/dataMatrix/encodeChipMatrixHuman.html клеточных линий GM23338 нет, поэтому для работы выбрана линия GM12878.

Клеточная линия: GM12878

Гистоновые метки:

| Histone modification | tableName | File |
| - | - | - |
| H2AZ | wgEncodeBroadHistoneGm12878H2az | wgEncodeBroadHistoneGm12878H2azStdAlnRep1.bam |
| H3K27ac | wgEncodeBroadHistoneGm12878H3k27ac | wgEncodeBroadHistoneGm12878H3k27acStdAlnRep1.bam |
| H3K27me3 | wgEncodeBroadHistoneGm12878H3k27me3 | wgEncodeBroadHistoneGm12878H3k27me3StdAlnRep1.bam |
| H3K36me3 | wgEncodeBroadHistoneGm12878H3k36me3 | wgEncodeBroadHistoneGm12878H3k36me3StdAlnRep1.bam |
| H3K4me1 | wgEncodeBroadHistoneGm12878H3k04me1 | wgEncodeBroadHistoneGm12878H3k04me1StdAlnRep1V2.bam |
| H3K4me2 | wgEncodeBroadHistoneGm12878H3k4me2 | wgEncodeBroadHistoneGm12878H3k4me2StdAlnRep1.bam |
| H3K4me3 | wgEncodeBroadHistoneGm12878H3k04me3 | wgEncodeBroadHistoneGm12878H3k04me3StdAlnRep2V2.bam |
| H3K79me2 | wgEncodeBroadHistoneGm12878H3k79me2 | wgEncodeBroadHistoneGm12878H3k79me2StdAlnRep1.bam |
| H3K9ac | wgEncodeBroadHistoneGm12878H3k9ac | wgEncodeBroadHistoneGm12878H3k9acStdAlnRep1.bam |
| H3K9me3 | wgEncodeBroadHistoneGm12878H3k9me3 | wgEncodeBroadHistoneGm12878H3k9me3StdAlnRep1.bam |
| H4K20me1 | wgEncodeBroadHistoneGm12878H4k20me1 | wgEncodeBroadHistoneGm12878H4k20me1StdAlnRep1.bam |

Контроль:
| Control | tableName | File |
| - | - | - |
| Control | wgEncodeBroadHistoneGm12878Control | wgEncodeBroadHistoneGm12878ControlStdAlnRep1.bam |

## ChromHMM
Вручную создан текстовый файл cellmarkfiletable.txt, в котором указаны тип клеток, гистоновые метки, а также соответствующие .bam файлы для эксперимента и контроля. Файл загружен в папку data.

Запустили ChromHMM.

https://colab.research.google.com/drive/1V4Mug6eBHqznC5aqzryAyFwoze8w9Bqv?usp=sharing

Файлы (20 файлов), выданные ChromHMM, загружены в папку data.

Emission Parameters | Transition Parameters | Fold Enrichment GM12878_10
-|-|-
![](data/emissions_10.png) | ![](data/transitions_10.png) | ![](data/GM12878_10_overlap.png)

## UCSC Genome Browser
Настроен Custom Track с dense.bed файлом из выдачи ChromHMM (трек дополнен CpG островками, так как они отражены на графике ChromHMM).

chr10:89,281-204,480
![image](https://user-images.githubusercontent.com/114621114/229536590-15d95157-401d-4d70-b74f-3ce3a59e236a.png)
chr10:198,721-313,920
![image](https://user-images.githubusercontent.com/114621114/229537254-5695305b-5b93-4a04-94f6-16e14fdc417f.png)
chr10:308,161-423,360
![image](https://user-images.githubusercontent.com/114621114/229539712-0bd2e9e8-8588-48d4-8d0b-ebab280e9726.png)
chr10:417,601-532,800
![image](https://user-images.githubusercontent.com/114621114/229540650-f7febf0c-506d-4e16-817b-1fa7204947b8.png)
chr10:527,041-642,240
![image](https://user-images.githubusercontent.com/114621114/229541106-5c77d666-0b85-40a7-9150-a4acc7f183a1.png)

## Эпигенетические типы

| Тип | Эпигенетические метки | Типичное расположение | Название эпигенетического типа |
| - | - | - | - |
| 1 | H3K36me3 (dim) | RefSeq Gene, RefSeq Exon, RefSeq TES | Transcriptional elongation |
| 2 | H3K79me2, H3K4me1 (dim) | RefSeq Gene | Transcriptional transition/elongation |
| 3 | H3K79me2, H3K4me1, H3K4me3, H3K4me2, H3K27ac | RefSeq Gene, RefSeq TES | Strong Enhancer |
| 4 | H3K27ac, H3K4me3, H3K9ac, H3K79me2, H3K4me2, H2AZ, H3K4me1 | CpG Island, RefSeq Gene, RefSeq Exon, RefSeq TSS, RefSeq TSS2kb, RefSeq TES | Active Promoter |
| 5 | H3K27ac, H3K4me1, H3K4me3, H3K4me2, H2AZ, H3K9ac | RefSeq TES | Strong Enhancer |
| 6 | H3K4me3, H3K4me2, H3K4me1, H2AZ | CpG Island, RefSeq Exon, RefSeq TSS, RefSeq TSS2kb, RefSeq TES | Weak Promoter/Enhancer |
| 7 | H3K4me1, H2AZ (dim) | lamin ilands | Weak Enhancer |
| 8 | H3K4me1, H3K27ac, H3K4me3 (dim), H3K36me3 (dim), H3K79me2 (dim) | RefSeq Gene, RefSeq Exon, RefSeq TES | Transcriptional transition |
| 9 | - | lamin ilands | Heterochromatin |
| 10 | H3K27me3 (dim) | lamin ilands | Heterochromatin |

## Бонусная часть задания
https://colab.research.google.com/drive/1V4Mug6eBHqznC5aqzryAyFwoze8w9Bqv?usp=sharing

Новый файл GM12878_10_dense_new.bed приложен в формате архива в папке data.

https://genome.ucsc.edu/cgi-bin/hgTracks?db=hg19&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr10%3A273601%2D388800&hgsid=1600518621_EHa5pm5uAQ6JNO5QxN4h5jETkuj8

(надеюсь, ссылка будет работать, но скрины прилагаю)

![image](https://user-images.githubusercontent.com/114621114/229638638-b871793f-cbfa-4319-928b-8b8d6f877c3a.png)
![image](https://user-images.githubusercontent.com/114621114/229638758-522ebb22-55f4-496c-8687-73010ff10d09.png)
![image](https://user-images.githubusercontent.com/114621114/229638858-cc24ba47-9fab-461c-a5d1-d1c981e14dfb.png)
