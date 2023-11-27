# Deep Learing a gyakorlatban

## Csapat neve

15_Drágakő_bányászok

## Csapattagok

Herkules Márton Gergely GE64XE

## Célkitűzés

Egy adott képen felismerni egy drágakövet és azt, hogy mekkora a súlya a képen lévő mérleg digitális mutatójának a leolvasásával. Mivel kevés a kép a tanító adatbázisban, ezért a drágakő felismerésére egy objektum detektálót és egy klasszifikálót is alkalmazunk. A klasszifikáló bemenetét az objektum detektáló által talált, alap képből kivágott drágakő képzi

## Fájlok feladatai

Detection.ipynb:
- Elején szükséges megadni egy detektálandó képet
- A korábban betanított 3 modell súlyait betölti egy általam megosztott helyről
- A kiértékelendő képen lefuttatja a számfelismerést és visszaküldi, hogy milyen számot mutat a "mérleg"
- A drágakő objektum detektáló segítségével megtalálja a drágakövet a képen, ha van. Ha van kő, akkor annak a képét tovább adja a drágakő klasszifikálónak
- Drágakő klasszifikáló a kapott képről elmondja, hogy szerinte milyen osztály
- A végén az objektum detektáló és klasszifikáló is megmondja, hogy szerinte milyen osztályba tartozik a drágakő és mekkora valószínűséggel


GemPreparation.ipynb: 
- Letölti és előkészíti a tanuláshoz a drágakő adatbázist.
- Futtatja az tanítását az drágaköveket felismerni képes objektum detektálónak. A yolov5/run/train/exp tartalmazz az utolsó epoch összes információját. A weight mappa tartalmazza a tanítás közbeni validáció alapján legeredményesebb háló súlyokat a best.pt fájlban
- Végén kiértékelés: yolov5/run/val/exp tartalmazza a Precision, Recall, F1, PR görbét. Tévesztési mátrixot és a test alatt lévő batch-ek tartalmát. (val_batch néven van néhány fájl, de ténylegesen a teszt dataset segítségével futtatja a kiértékelést)

NumberPreparation.ipynb: 
- Teljesen ugyan azt, mint a GemPreparation.ipynb, csak itt számok detectálása a cél.

GemClass.ipynb: 
- Letölti és előkészíti a tanuláshoz a klasszifikáció drágakő adatbázist.
- Futtatja a tanítást, de itt nem objektum detektáció a cél, hanem egy egyszerű klasszifikáció.


## Adatforrások:
Roboflow segítségével összeállított tanító adatbázisok. 

Drágakő gyűjtemény objektum detektálás: https://universe.roboflow.com/msc-onlab-1/gem-9oe6g

Szám gyűjtemény objektum detektálás: https://universe.roboflow.com/legoproject/digital-numbers-vqqx2

Drágakő gyűjtemény klasszifikáció:
https://universe.roboflow.com/msc-onlab-1/gem-q84tk/dataset/3