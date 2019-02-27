---
title: Ukázkové R projekty
description: Index kolekce ukázek Začínáme s R a sady Visual Studio.
ms.date: 01/24/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: adcc5ce422cdd06e641408b3506fb751a4c730d1
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840880"
---
# <a name="r-tools-for-visual-studio-sample-projects"></a>Nástroje R pro Visual Studio ukázkových projektů

Tato kolekce ukázek vám pomůže začít v R, nástroje R pro Visual Studio (RTVS) a Microsoft Machine Learning Server:

1. Stáhněte si [soubor zip, ukázky](https://github.com/Microsoft/RTVS-docs/archive/master.zip) a rozbalte do složky podle vašeho výběru.
1. Otevřít `examples/Examples.sln` zobrazíte dvě složky v projektu:

    - *První seznámení v R* přináší mírného Úvod pro nové uživatele do jazyka R.
    - *Paní a Machine Learning* příkladů, jak pomocí jazyka R a Microsoft Machine Learning Server pro machine learning.

## <a name="a-first-look-at-r"></a>První pohled na R

Tato ukázka poskytuje jako důkladný Úvod k R prostřednictvím rozsáhlé komentáře ve dvou zdrojových souborů. Pro nejlepší prostředí, umístěte kurzor na začátek souboru a stisknutím kláves Ctrl + Enter odeslat kód řádku podle leží na **interaktivní R** okna. (Řádky, které instalují balíčky může trvat minutu nebo dvě dokončit.)

- `1-Getting Started with R.R` zahrnuje mnoho základy jazyka R, včetně použití balíčků, načítání a analýza dat a vykreslení.

    ![Příklad výstupu z 1 – Začínáme s ukázkou R.R](media/samples-getting-started-output.png)

- `2-Introduction to ggplot2.R` představuje grafické balíček ggplot2 známy jeho vykreslení vizuálně přitažlivé a jednoduchá syntaxe. V tomto příkladu vizualizuje data zemětřesení z Fiji.

    ![Příklad výstupu z 2 – Úvod do ggplot2. Ukázky jazyka R](media/samples-ggplot-output.png)

## <a name="microsoft-machine-learning-server-and-machine-learning"></a>Server Microsoft Machine Learning a Machine Learning

Tuto kolekci z příkladů ukazuje způsob použití jazyka R vytvořit modely strojového učení a chcete využít výhod [Microsoft Machine Learning Server](/machine-learning-server/what-is-machine-learning-server).

S všechny příklady, otevřete soubor, umístěte kurzor na slovo v horní části a poté krokovat kód řádek po řádku s **Ctrl**+**Enter**. Souborů markdownu v každé složky taky obsahovat další podrobnosti.

- `Benchmarks` spuštění, který získá celou řadou algebraický lineární náročné, paralelní výpočty zobrazíte výkonu, které je možné prostřednictvím Microsoft R Open a knihovny pro jádra matematické Intel (MKL). S Simulovaná data porovnat srovnávací testy konkrétně matice výpočty v jednom vlákně a dvě.

    ![Diagram příkladu srovnávacích testů](media/samples-mro-benchmark-plot.png)

- `Bike_Rental_Estimation_with_MRS` Vytvoří model vyžádání předpovědi na základě historické sady dat pomocí Microsoft ML Server pronajatých kol za.

- `Data_Exploration` obsahuje tři skripty:

  - `Import Data from URL.R` ukazuje, jak načíst identifikovaný adresa URL datového souboru do R.
  - `Import Data from URL to xdf.R` ukazuje, jak načíst soubor identifikovaný adresy URL dat do Microsoft ML Server jako xdf.
  - `Using ggplot2.R` je rozšířením `A First Look at R/2-Introduction to ggplot2.R` ukázka poskytuje rozsáhlejší prohlídku funkcí ggplot2 společnosti včetně interaktivní 3D vykreslení.

      ![Výstup pomocí ggplot2. Příklad R](media/samples-3d-interactive.png)

- `Datasets` obsahuje tři *CSV* soubory používané aplikací Další ukázky
- `Flight_Delays_Prediction_with_R` a `Flight_Delays_Prediction_with_MRS` ukazuje, jak k předpovědi zpoždění letů pomocí R, strojové učení a historická o včasných odletech a data o počasí.
- `Machine learning` obsahuje tři ukázky pro učení k předpovědi zpoždění letů, ubytování ceny a pronajatých kol za. Společně tyto ukázky ukazují použití R a Microsoft ML Server na reálných problémů. Jsou také ukazují, jak použít několik modelů oblíbených strojového učení a jejich nasazení jako webové služby Azure s použitím [Azure Machine Learning](https://azure.microsoft.com/services/machine-learning/) pracovního prostoru.

- `R_MRO_MRS_Comparison` je šestidílném porovnání, která zobrazuje podobnosti a rozdíly v R, Microsoft R Open nebo Microsoft ML Server s příkazy, syntaxe, konstrukce a výkonu.

## <a name="whats-special-about-microsoft-r-open-and-microsoft-ml-server"></a>Co je speciální informace o Microsoft R Open a Microsoft ML Server?

[Microsoft R Open](https://aka.ms/rtvs-r-open), což je distribuce Microsoftu jazyka R se liší od [CRAN r.](https://cran.r-project.org/) dvěma důležitými způsoby:

1. [Vyšší výpočetní výkon](https://mran.revolutionanalytics.com/rro/#intelmkl1) při použití s [Intel matematické jádra knihovny](https://software.intel.com/intel-mkl). Tyto knihovny jsou k dispozici jako bezplatná položka ke stažení od společnosti Microsoft pro použití s Microsoft R Open.

1. [Reprodukovatelné nástrojů R](https://mran.revolutionanalytics.com/rro/#reproducibility) zajistí, že knihovny použité k vytvoření programu jazyka R budou vždy k dispozici pro ostatní, které chcete reprodukovat svou práci.

[Microsoft ML Server (MLS)](/machine-learning-server/what-is-machine-learning-server) je rozšíření jazyka R, který umožňuje zpracovávat další data a zpracovávat rychleji. Poskytuje výkonné funkce R dvě:

1. Větší datové sady bez omezení paměti RAM. ML Server může zpracovávat data na více instancí z důvodu nedostatku paměti z nejrůznějších zdrojů, včetně clusterů Hadoop, databází a datových skladů.

1. Zpracování paralelních, více jádry. MLS můžete efektivně distribuovat výpočty napříč výpočetní prostředky k dispozici. Na váš osobní pracovní stanice nebo vzdáleného clusteru MLS získá odpověď rychleji.

Toto porovnání ukazuje, že MLS a MRO s MKL jsou výrazně vyšší výpočetní výkon související se určité matice výpočtu než R a MRO bez MKL. V tomto výpočtu využívají Simulovaná data:

![Porovnání MLS a MRO s MKL r a MRO bez MKL](media/samples-speed-comparison.png)

Technické porovnání jazyka R s MRO a MLS, projděte si [Lixun Potokar podrobné diskuze](http://htmlpreview.github.io/? https://github.com/lixzhang/R-MRO-MRS/blob/master/Introduction_to_MRO_and_MRS.html) v tomto tématu.

Na následujícím obrázku pak porovná uplynulý čas v sekundách použít při vytváření logistické regresní modely k předpovědi zpoždění letů delší než 15 minut.  Uplynulý čas při CRAN r. zvýší výrazně při zvýšení malý počet řádků, zatímco MLS zvyšuje úroveň pouze přibližně dvakrát. Podrobnosti o tomto srovnávacího testu, podívejte se *srovnávací testy/rxGlm_benchmark. R* příklad.

![rxGlm srovnávacích testů](media/samples-rxGLM-benchmark.png)
