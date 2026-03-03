# Grupa: Hierarchiczna Analiza Reprezentacji w Modelach Wizyjnych

## Prowadzący

Dawid Płudowski

## Opis

Modele wizyjne potrafią często uczyć się zaskakujących zależności ze zdjęć. Na przykład, model uczący się rozpoznawać wiek osoby ze zdjęcia "przy okazji" potrafi wykrywać zmarszczki, kolor włosów, czy inne *cechy*, które dla nas są intuicyjne, a jednocześnie są nietrywialne do wykrycia statystycznie. Jak skorzystać z tej *ukrytej* wiedzy, którą posiada model? Istnieje wiele metod, ale podczas zajęć skupimy się na podstawach i rozważamy **hipotezę liniowej separowalności**, która mówi, że przestrzeń ukryta modelu może zostać podzielona hiperpłaszczyzną tak, aby oddzielić zdjęcia, które posiadają konkretną *cechę* (np. przedstawiają osobę z siwymi włosami) od pozostałych. Dodatkowo, rozszerzymy ten koncept o **hierarchiczność** cech, narzucając dodatkowe założenia na analizowaną przestrzeń, aby polepszyć aktualnie istniejące metody.

## Projekty

Projekty będą realizowane w grupach 3 osobowych. W ramach zajęć oraz pracy własnej każda z grup:

1. nauczy się korzystać z pretrenowanych dużych modeli, takich jak CLIP czy ResNet,
2. przeanalizuje przestrzeń ukrytą wybranego modelu i zweryfikuje **hipotezę liniowej separowalności**,
3. napisze podstawową metodę do wykrywania *cech* w przestrzeni ukrytej,
4. rozwinie metodę z punktu 3. o poprawkę na hierarchiczność *cech*.

## Punktacja

*(Może ulec zmianie w pierwszych 2 tygodniach zajęć)*

**Projekt** (40pkt)

1. Checkpoint I - wybór danych i modelu (5pkt)
2. Checkpoint II - eksperymenty z wektorami sterującymi (15pkt)
3. Checkpoint III - ablacja eksperymentów (5pkt)
4. Końcowa prezentacja (15pkt)

**Prace Domowe** (10pkt)

1. ~ Dwie prace domowe w ciągu semestru, opcjonalne dodatkowe zadania na dodatkowe punkty

**Prezentacja** (10pkt)

1. Zaprezentowanie ~20min prezentacji na temat wybranego artykułu (lista sugerowanych artykułów będzie podana w trakcie zajęć)

## Terminarz

*(Może ulec zmianie w pierwszych ~2 tygodniach zajęć)*

Semestr będzie podzielony na dwie części. Przez pierwsze 7 tygodni będziemy razem pracować, poznawać teorię i ćwiczyć praktyczne umiejętności (formuła głównie laboratoryjna). Następnie przechodzimy do fazy projektowej, gdzie każda grupa realizuje wybrany projekt (formuła głównie projektowa). Jeżeli będzie taka potrzeba - możemy w ramach konsultacji przeprowadzić zajęcia laboratoryjne, żeby uzupełnić wiedzę, przećwiczyć dane zagadnienie itp.

- Week 1 (24.02.2025):
  - krótkie intro do przedmiotu, Q&A
- Week 2 (03.03.2026):
  - wstęp do teorii: czym jest przestrzeń ukryta, czym jest wektor sterujący, po co nam wektory sterujące
  - wstęp do praktyki: intro do GoogleCollab, uruchomienie modelu z HuggingFace, zrobienie pierwszej klasyfikacji za pomocą modelu wizyjnego
  - ustalenie grup projektowych
- Week 3 (10.03.2026):
  - teoria: jak informacja jest tworzona w modelu wizyjnym, gdzie jej szukać, dlaczego połączenia rezydualne w sieciach sprawiają, że wszystko jest prostsze
  - praktyka: eksploracja wnętrza modelu typu ResNet, szukanie "niespodziewanych" zachowań
- Week 4 (17.03.2026):
  - teoria: założenie o liniowej separowalności konceptów i jego znaczenie w zastosowaniach, "debiasing" modelu, porównanie z modelami nieliniowymi
  - praktyka: napisanie pierwszego wektora sterującego oraz "debiasingu" modelu poprzez ortgonalizację
- Week 5 (24.03.2026):
  - podanie dokładnych wymagań projektowych, planowanie projektów, brainstorming pomysłów
- Week 6 (31.03.2026):
  - prezentacje studentów
- Week 7 (07.04.2026):
  - prezentacje studentów
- Week 8 (14.04.2026):
  - Konsultacje
- Week 9 (21.04.2026):
  - Checkpoint I
- Week 10 (28.04.2026):
  - Konsultacje
- Week 11 (05.05.2026):
  - Checkpoint II
- Week 12 (**19.05.2026**):
  - Konsultacje
- Week 13 (26.05.2026):
  - Checkpoint III
- Week 14 (02.06.2026):
  - Prezentacje projektów
- Week 15 (09.06.2026):
  - *awaryjny termin na zrobienie prezentacji*

## Kontakt

Slack (**preferowany**): podany na pierwszym wykładzie

Mail: [dawid.pludowski@pw.edu.pl](mailto:dawid.pludowski@pw.edu.pl) (nie ~~[dawid.pludowski.stud@pw.edu.pl](mailto:dawid.pludowski.stud@pw.edu.pl)~~, nie ~~[dawid.pludowski.dokt@pw.edu.pl](mailto:dawid.pludowski.dokt@pw.edu.pl)~~)

## Literatura

*(Gdyby ktoś chciał poczytać przed zajęciami, może być tematem prezentacji)*

- (**bazowa praca dla całego kursu, CAV**) Kim, B., Wattenberg, M., Gilmer, J., Cai, C., Wexler, J., Viegas, F., et al. Interpretability beyond feature attribution: Quantitative testing with concept activation vectors (TCAV). In ICML, 2018.
- (**FactCAV**) Schmalwasser, Laines, et al. "FastCAV: Efficient Computation of Concept Activation Vectors for Explaining Deep Neural Networks." International Conference on Machine Learning. PMLR, 2025.
- (**PatCAV**) Pahde, Frederik, et al. "Navigating Neural Space: Revisiting Concept Activation Vectors to Overcome Directional Divergence." The Thirteenth International Conference on Learning Representations.
- (**Linear Probe**) Alain, Guillaume, and Yoshua Bengio. "Understanding intermediate layers using linear classifier probes." arXiv preprint arXiv:1610.01644 (2016).
