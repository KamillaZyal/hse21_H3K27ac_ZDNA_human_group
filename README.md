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
| Зялалетдинова Камилла | 3 | А549 | [https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human) |
| Никитенко Яна | 3 | H9 | [https://github.com/nikyavn/hse21_H3K27ac_ZDNA_human](https://github.com/nikyavn/hse21_H3K27ac_ZDNA_human) |

Клетки **А549** являются аденокорциномой человеческого альвеолярного базальных эпителиальных клеток , и представляют собой клеточную линию , которая была впервые разработана в 1972 году DJ Giard и др. путем удаления и культивирования раковой легочной ткани в эксплантированной опухоли 58-летнего мужчины европеоидной расы. Клетки используются в качестве моделей для изучения рака легких и разработки лекарств против него. 


## Отчёт

### Введение

**H3K27ac** - эпигенетическая модификация упаковочного белка ДНК гистона **H3** . Это знак указывает на ацетилирование лизина 27 на субъединице белка гистона H3. Гистон H3K4me1 и H3K27ac представляют собой модификации, специфичные для энхансеров, и необходимы энхансерам для активации транскрипции генов-мишеней.

> **H3K27ac** связан с  высокой активацией транскрипции и поэтому определяется как активная энхансерная метка. H3K27ac обнаруживается как в проксимальных, так и в дистальных областях сайта начала транскрипции (TSS).
H3K27ac обогащены регуляторными областями генов, участвующих в болезни Альцгеймера , в том числе генов тау-белка и амилоидной невропатологии.



### Обзор исходных файлов

| Участник | Организм | Тип клетки | Эксперимент 1 | Эксперимент 2 |Эксперименты определения вторичной стр-ры ДНК |
|--|:--:|:--:|:--:|:--:|:--:|
| Зялалетдинова Камилла | human | А549 | ENCFF389RXK | ENCFF926NKP | ZDNA_DeepZ  |
| Никитенко Яна | human | H9 | ENCFF997MGG | ENCFF365GJO | ZDNA_DeepZ  |

### Длинны пиков по эксперементам

***Гистограмма длин участков A549***
 ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/len_hist.H3K27ac_A549.intersect_with_DeepZ.png)
 ***Гистограмма длин участков H9***
 ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/len_hist.H3K27ac_H9.intersect_with_DeepZ.png)
#### ***Круговая диаграмма ChIPseeker A549***
![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/chip_seeker.H3K27ac_A549.intersect_with_DeepZ.plotAnnoPie.png)
#### ***Круговая диаграмма ChIPseeker H9***
![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/chip_seeker.H3K27ac_H9.intersect_with_DeepZ.plotAnnoPie.png)


### Анализ пиков, полученных после тотального пересечения
- Строим гистограмму длин участков:
 > Для обработки данных используем скрипт *.R*
 #### ***Гистограмма длин участков***
 ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/common.intersect.len_hist.DeepZ.png)
 **После пересечения:** 14212
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
    - Ссылка на визуализированные данные:
```
      http://genome.ucsc.edu/cgi-bin/hgTracks?         db=hg19&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr3%3A1%2D198022430&hgsid=1124297721_EDRNsmwC5tYtTwUpUk9rIi78ehQT
```
- Найдем места в геноме, где имеется тотальное пересечение всех пиков:
   ### **Координаты chr3:119,180,163-119,185,434**
   ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/intersectUCSC1.png) 
   ### **Координаты chr10:75,543,726-75,547,346**
   ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/intersectUCSC2.png) 
### Ассоциация пиков тотального пересечения с генами и делаем GO анализ
- Было ассоциировано 14208 пиков

- Результат GO-анализа:
  ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/GO.png)
- Наиболее значимые категории:
  ![Alt-текст](https://github.com/KamillaZyal/hse21_H3K27ac_ZDNA_human_group/blob/main/images/allGO.png) 
