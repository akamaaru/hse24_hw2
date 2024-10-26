### Анализ данных секвенирования
# Домашнее задание №2. Отчёт
В данной работе проводится аннотация генома бактерии Thalassolituus oleivorans и сравнение её с геномом другого штамма.

## Основное задание
Для подготовки файлов к аннотации был использован данный в задании проект в [Google Colab](https://colab.research.google.com/drive/1whvEuIrT0bWNk_5Y_JCEtyjvJL-P_6Uj?usp=sharing). 
Для обработки были использованы скаффолды, составленные в [предыдущем задании](https://github.com/akamaaru/hse24_hw1/tree/main/data/base). Для удобства, скаффолды были также помещены в папку `data`.

При помощи пакета SeqKit была составлена следующая статистика:
| Категория      | Количество генов |
| ----------- | ----------- |
| Предсказано всего      |   3612     |
| Аннотированно с помощью сравнения | 3328    |
| Аннотированно с помощью SwissProt |  54    |
| Осталось без аннотации |  284   | 

После работы программ GeneMarkS-2 и blastp на выходе получились следующие файлы, они были перемещены в папку `data`:
- `gms2.lst` -- координаты всех предсказанных генов;
- `proteins.fasta` -- аминокислотные последовательности всех предсказанных генов;
- `scaffolds.hits_from_MIL_1.txt` -- информация о схожести белков из нашей бактерии с белками из бактерии MIL-1;
- `scaffolds.hits_from_SwissProt.txt` -- информация о схожести белков из нашей бактерии с белками из БД SwissProt.

Далее, используем полученные файлы для создания аннотированного генома бактерии в формате GenBank. Вся работа выполнялась в [Google Colab](https://colab.research.google.com/drive/1QUh2CObYxXYdQqek1Hgf6D7-QIPRLf3N?usp=sharing)

## Бонусное задание
Предскажем рибосомальные РНК (5S, 16S, 23S) с помощью BLASTn.
Для этого возьмем нуклеотидные последовательности 5S, 16S, 23S рРНК бактерии Thalassolituus oleivorans и найдем соответствующие участки в полученной сборке.

Бонусное задание было выполнено в том же [блокноте](https://colab.research.google.com/drive/1QUh2CObYxXYdQqek1Hgf6D7-QIPRLf3N?usp=sharing). 
```
Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 99% resemblance
For seq = scaffold70_cov665 	 100% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 99% resemblance
For seq = scaffold65_cov675 	 100% resemblance
For seq = scaffold63_cov665 	 100% resemblance
For seq = scaffold66_cov704 	 100% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 100% resemblance
For seq = scaffold65_cov675 	 100% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 98% resemblance
For seq = scaffold65_cov675 	 99% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 99% resemblance
For seq = scaffold65_cov675 	 100% resemblance
For seq = scaffold63_cov665 	 100% resemblance
For seq = scaffold66_cov704 	 100% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 99% resemblance
For seq = scaffold70_cov665 	 99% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 100% resemblance
For seq = scaffold65_cov675 	 100% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 99% resemblance
For seq = scaffold65_cov675 	 100% resemblance
For seq = scaffold63_cov665 	 100% resemblance
For seq = scaffold66_cov704 	 100% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 99% resemblance
For seq = scaffold70_cov665 	 99% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 100% resemblance
For seq = scaffold65_cov675 	 100% resemblance

Resemblance rRna 341494...343033
For seq = scaffold1_cov273 	 99% resemblance
For seq = scaffold65_cov675 	 100% resemblance
For seq = scaffold63_cov665 	 100% resemblance
For seq = scaffold66_cov704 	 100% resemblance
```

## Вывод
Можем заметить, что большинство генов (92%) было аннотировано простым сравнением с геномом Thalassolituus oleivorans MIL-1 при условии, что изначальное число чтений было не самым большим. Также, последовательности рРНК показали не менее 99% схожести с построенным геномом. Следовательно, можно утверждать, что различие геномов двух различных штаммов невелико.
