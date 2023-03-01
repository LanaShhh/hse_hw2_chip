# hse_hw2_chip

## Содержание файлов и папок

- [fastqc_reports](https://github.com/LanaShhh/hse_hw2_chip/tree/main/fastqc_reports) - отчеты fastqc, в том чесле после подрезания

- [venn_results](https://github.com/LanaShhh/hse_hw2_chip/tree/main/venn_results) - файлы пересечения, сгенерированные intervene

- HW2.ipynb - код

## Отчет

### Отчеты fastqc

Реплики - ENCFF001FNT и ENCFF001FNS, контроль - ENCFF001HPI

**ENCFF001FNT**

До подрезания

![](https://github.com/LanaShhh/hse_hw2_chip/blob/main/fastqc_reports/FNT_before.png)

После подрезания

![](https://github.com/LanaShhh/hse_hw2_chip/blob/main/fastqc_reports/FNT_trimmed.png)

**ENCFF001FNS**

До подрезания

![](https://github.com/LanaShhh/hse_hw2_chip/blob/main/fastqc_reports/FNS_before.png)

После подрезания

![](https://github.com/LanaShhh/hse_hw2_chip/blob/main/fastqc_reports/FNS_trimmed.png)

**ENCFF001HPI**

До подрезания

![](https://github.com/LanaShhh/hse_hw2_chip/blob/main/fastqc_reports/HPI_before.png)

После подрезания

![](https://github.com/LanaShhh/hse_hw2_chip/blob/main/fastqc_reports/HPI_trimmed.png)

Как мы видим, чтения имеют плохое качество, поэтому реплики и контроль необходимо подрезать. После подрезания качество улучшилось, но незначительно.

### Статистика на основе работы bowtie

Данные были получены в jupyter-ноутбуке

ID          | Reads in file | Aligned exactly 1 time | Aligned >1 times | Aligned 0 times 
---         | ---           | ---                    | ---              |---               
ENCFF001FNS | 15120695      | 423259 (2.80%)         | 725464 (4.80%)   | 13971972 (92.40%)
ENCFF001FNT | 14505406      | 338395 (2.33%)         | 480171 (3.31%)   | 13686840 (94.36%)
ENCFF001HPI | 17195196      | 724864 (4.22%)         | 2432458 (14.15%) | 14037874 (81.64%)

Как мы видим, процент выравниваний получился низким, бОльшая часть не была выровнена. Это связано с тем, что мы выполняли выравнивание на одну хромосому, это лишь небольшая доля всего генома человека.

### Диаграммы пересечения 

Диаграммы пересечения представлены в папке venn_results. 

- [Intervene_venn1.pdf](https://github.com/LanaShhh/hse_hw2_chip/blob/main/venn_results/Intervene_venn1.pdf) - пересечение наших пиков FNS и ENCODE пиков

- [Intervene_venn2.pdf](https://github.com/LanaShhh/hse_hw2_chip/blob/main/venn_results/Intervene_venn2.pdf) - пересечение ENCODE пиков и наших пиков FNS

- [Intervene_venn3.pdf](https://github.com/LanaShhh/hse_hw2_chip/blob/main/venn_results/Intervene_venn3.pdf) - пересечение наших пиков FNT и ENCODE пиков

- [Intervene_venn4.pdf](https://github.com/LanaShhh/hse_hw2_chip/blob/main/venn_results/Intervene_venn4.pdf) - пересечение ENCODE пиков и наших пиков FNT

Как мы видим, пересечений очень мало. Это связано с тем, что выравнивание происходило на одну хромосому, в то время как ENCODE пики расссчитывались на всех хромосомах. 


