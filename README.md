# Проект по майнору Биоинформатика, ВШЭ 2021

### О проекте

> Целью работы над проектом является поиск и изучение участков генома, где определенная гистоновая метка присутствует в местах образования вторичной структуры ДНК.
>> - **Организм:** human
>> - **Сборка генома:** hg19
>> - **Структура:** ZDNA
>> - **Метка:** H3K27ac
>> - **Типы клеток:** A549, H9


### Список участников

|Имя участник | Группа | Тип клеток | Личный репозиторий |
|--|--|--|--|
| Зялалетдинова Камилла | 3 | H9 | [https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human) |
| Никитенко Яна | 3 | H1 | [https://github.com/nikyavn/hse21_H3K27ac_ZDNA_human](https://github.com/nikyavn/hse21_H3K27ac_ZDNA_human) |


## Отчёт

### Введение

**H3K27ac** - эпигенетическfая модификация упаковочного белка ДНК гистона **H3** . Это знак указывает на ацетилирование лизина 27 на субъединице белка гистона H3.

> **H3K27ac** связан с  высокой активацией транскрипции и поэтому определяется как активная энхансерная метка. H3K27ac обнаруживается как в проксимальных, так и в дистальных областях сайта начала транскрипции (TSS).
H3K27ac обогащены регуляторными областями генов, участвующих в болезни Альцгеймера , в том числе генов тау-белка и амилоидной невропатологии.
**H3K9ME3** имеет роль не только в злокачественном, но и в нормальном развитии клетки, выступая в качестве репрессора наследственных неуместных генов и поддерживая раннюю целостность клетки и геномную стабильность. В начале 2000 года ряд групп предоставили доказательства его важности в взаимодействии с эволюционно консервативным аминомосковным хромодоменом гетерохроматина белка 1 (HP1), отличительной чертой гетерохроматина, тем самым набирая его к определенному Chromatin Loci (15-17).

> **H3K9me3** has a role not only in malignancy but in normal cellular development, acting as a repressor of lineage inappropriate genes and maintaining early cell integrity and genomic stability. In the early 2000's a number of groups provided evidence of its importance in interacting with the evolutionarily conserved amino terminal chromodomain of heterochromatin protein 1 (HP1), a hallmark of heterochromatin, thereby recruiting it to specific chromatin loci (15–17).

Альтернативный подход к исследованию кода гистона выявил другую роль для **H3K9ME3** в AML. Некоторые доказательства говорят о роли для **H3K9ME3**, связанной с активацией либо в качестве одиночной метки путем избирательного взаимодействия с РНК-полимеразой II для содействия удлинению мРНК и транскрипционной активации или через определенный кодовой код гистона в фундаментальных генах с активацией гистона **H3K9AC** и **H3K4ME2**.
 
> An alternative approach to investigating the histone code has identified an opposing role for **H3K9me3** in **AML**. Some evidence postulates a role for **H3K9me3** as associated with activation either as a solo mark by selectively interacting with RNA polymerase II to promote mRNA elongation and transcriptional activation or through a specific histone code co-localizing on fundamental genes with activating histone marks **H3K9ac** and **H3K4me2** .


### Обзор исходных файлов

| Участник | Организм | Тип клетки | Эксперимент 1 | Эксперимент 2 |Эксперименты определения вторичной стр-ры ДНК |
|--|:--:|:--:|:--:|:--:|:--:|
| Зялалетдинова Камилла | human | А549 | ENCFF389RXK | ENCFF926NKP | ZDNA_DeepZ  |
| Никитенко Яна | human | H9 | ENCFF997MGG | ENCFF365GJO | ZDNA_DeepZ  |

**После пересечения:** -TBA-

### Длинны пиков по эксперементам


### Анализ пиков, полученных после тотального пересечения
- Строим гистограмму длин участков:
 > Для обработки данных используем скрипт *.R*
    #### ***Гистограмма длин участков***
      ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/common.intersect.len_hist.DeepZ.png)
- Анализируем, где эти пики находятся относительно аннотированных генов:
> Для обработки данных используем скрипт *.R*
    #### ***Круговая диаграмма ChIPseeker***
      ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/common.intersect.DeepZ.plotAnnoPie.png)
### Визуализация данных в геномном браузере
- Визуализируем в UCSC Genome Browser все исходные .bed файлы,набор участков, полученный после их тотального пересечения:
    - Добавим сustom Tracks командами (аналогично другие файлы):
      ```
      track visibility=dense name="intersect_with_DeepZ"  color=200,0,0  description="H3K27ac_A549.intersect_with_DeepZ.bed"
      https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human/raw/main/data/H3K27ac_A549.intersect_with_DeepZ.bed
      ```
- Найдем места в геноме, где имеется тотальное пересечение всех пиков:
   ### **Координаты chr3:187,432,810-187,482,809**
   ![Alt-текст]() 
   ### **Координаты chr3:187,432,810-187,482,809**
   ![Alt-текст]() 
