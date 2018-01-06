---
title: "Krok 1: Vytvořte projekt a přidejte do svého formuláře popisky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f44e50be-a5f5-4d77-9cff-dd52374c3f74
caps.latest.revision: "16"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ab50592e345a54853e9cfbd95d0b9bd1bc86d794
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="step-1-create-a-project-and-add-labels-to-your-form"></a>Krok 1: Vytvořte projekt a přidejte do svého formuláře popisky
Jako první kroky při vývoji tento kvízu s časovým limitem můžete vytvořit projekt a přidejte popisky, tlačítka a jiných ovládacích prvků na formuláři. Můžete také nastavit vlastnosti pro každý ovládací prvek, který přidáte. Projekt bude obsahovat formulář, ovládací prvky a (dále v tomto kurzu) kódu. Tlačítko spustí kvízu, popisky zobrazit kvízu s časovým limitem problémy, a jiných ovládacích prvků zobrazit kvízu s časovým limitem odpovědi a čas, který zbývá k dokončení kvízu.  
  
> [!NOTE]
>  Toto téma je součástí série, kurz o základních konceptech kódování. Přehled kurzu, najdete v tématu [kurzu 2: vytvoření vypršel časový limit matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).  
  
### <a name="to-create-a-project-and-and-set-properties-for-a-form"></a>Vytvoření projektu a a nastavte vlastnosti formuláře  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V **nainstalovaných šablonách** vyberte buď **C#** nebo **jazyka Visual Basic**.  
  
3.  V seznamu šablon, vyberte **formulářové aplikace Windows** šablony, pojmenujte ji **matematického kvízu**a potom zvolte **OK** tlačítko.  
  
     Formulář, který je s názvem **Form1.cs** nebo **Form1.vb** se zobrazí, v závislosti na programovací jazyk, který jste si zvolili.  
  
4.  Vybrat formuláře a poté změňte jeho **Text** vlastnost **matematického kvízu**.  
  
     **Vlastnosti** okno obsahuje vlastnosti pro daný formulář.  
  
5.  Změníte velikost formuláře na 500 × široké 400 pixelů vysoký.  
  
     Velikost formuláře můžete změnit tak, že přetáhnete jeho hran, dokud správnou velikost, zobrazí se v levém horním rohu integrované vývojové prostředí (IDE). Jako alternativu, můžete změnit hodnoty **velikost** vlastnost.  
  
6.  Změňte hodnotu **FormBorderStyle** vlastnost **Fixed3D**a nastavte **MaximizeBox** vlastnost **False**.  
  
     Tyto hodnoty zabránit píší kvízu s časovým limitem poznámky Změna velikosti formuláře.  
  
### <a name="to-create-the-time-remaining-box"></a>Chcete-li vytvořit pole Zbývající čas  
  
1.  Přidat **popisek** řízení z panelu nástrojů a pak nastavte hodnotu jeho **(název)** vlastnost `timeLabel`.  
  
     Tento popisek začnou pole v pravém horním rohu, které zobrazuje počet sekund, které zůstávají v kvízu.  
  
2.  Změna **AutoSize** vlastnost **False** tak, aby můžete změnit velikost pole.  
  
3.  Změna **styl okraje** vlastnost **FixedSingle** kreslení čáry kolem pole.  
  
4.  Nastavte **velikost** vlastnost **200, 30**.  
  
5.  Přesuňte popisek do pravého horního rohu formulář, kde se zobrazí modré oddělovací čáry.  
  
     Tyto řádky usnadňují zarovnání ovládacích prvků formuláře.  
  
6.  V **vlastnosti** okně zvolte **Text** vlastnost a potom vyberte klíč Backspace zrušte jeho hodnotu.  
  
7.  Vyberte znaménko plus (+) vedle položky **písma** vlastnost a poté změňte hodnotu **velikost** vlastnost **15.75**.  
  
     Můžete změnit několik vlastností písma, jak ukazuje následující obrázek.  
  
     ![Vlastnosti – okno zobrazuje velikost písma](../ide/media/express_setfontsize.png "Express_setFontSize")  
Velikost písma zobrazuje vlastnosti – okno  
  
8.  Přidejte další **popisek** řízení z panelu nástrojů a potom změňte jeho velikost písma na **15.75**.  
  
9. Nastavte **Text** vlastnost **zbývající čas**.  
  
10. Přesuňte popisek tak, aby zarovnán právě nalevo od **timeLabel** popisek.  
  
### <a name="to-add-controls-for-the-addition-problems"></a>K přidávání ovládacích prvků pro přidání problémy  
  
1.  Přidat **popisek** řízení z panelu nástrojů a nastavte její **Text** vlastnost **?** (otazník).  
  
2.  Nastavte **AutoSize** vlastnost **False**.  
  
3.  Nastavte **velikost** vlastnost **60, 50**.  
  
4.  Nastavit velikost písma na **18**.  
  
5.  Nastavte **zarovnání textu** vlastnost **MiddleCenter**.  
  
6.  Nastavte **umístění** vlastnost **50, 75** na pozici ovládacího prvku na formuláři.  
  
7.  Nastavte **(název)** vlastnost **plusLeftLabel**.  
  
8.  Vyberte **plusLeftLabel** label a potom vyberte klíče Ctrl + C nebo **kopie** na **upravit** nabídky.  
  
9. Vložte popisek třikrát výběrem Ctrl + V klíče nebo **vložení** na **upravit** nabídky.  
  
10. Uspořádat tři nové štítky tak, aby se v řádku napravo **plusLeftLabel** popisek.  
  
     Oddělovací čáry můžete místo nich a zarovnejte je.  
  
11. Nastavte hodnotu druhý popisku **Text** vlastnost  **+**  (znaménko plus).  
  
12. Nastavte hodnotu třetí popisku **(název)** vlastnost **plusRightLabel**.  
  
13. Nastavte hodnotu čtvrté popisku **Text** vlastnost  **=**  (rovná).  
  
14. Přidat **NumericUpDown** z panelu nástrojů, nastavte jeho velikost písma **18**a nastavte šířku na **100**.  
  
     Dozvíte více o tento druh řízení později.  
  
15. Zarovnat **NumericUpDown** ovládacího prvku s ovládacími prvky popisek pro přidání problém.  
  
16. Změňte hodnotu **(název)** vlastnost **NumericUpDown** řídit k **součet**.  
  
     Vytvoření první řádek, jak ukazuje následující obrázek.  
  
     ![První řádek matematického kvízu](../ide/media/express_firstrow.png "Express_firstRow")  
První řádek matematického kvízu  
  
### <a name="to-add-controls-for-the-subtraction-multiplication-and-division-problems"></a>K přidávání ovládacích prvků pro problémy odčítání, násobení a dělení  
  
1.  Zkopírujte všechny pět ovládací prvky pro sčítání (čtyři ovládací prvky popisek a ovládacího prvku NumericUpDown) a potom je vložit.  
  
     Tento formulář obsahuje pět nových ovládacích prvků, které jsou stále vybrané.  
  
2.  Přesouvání všech ovládacích prvků do místní tak, aby rovině níže ovládacími prvky.  
  
     Oddělovací čáry můžete poskytnout dostatek vzdálenost mezi dva řádky.  
  
3.  Změňte hodnotu **Text** vlastnosti pro druhý štítek, který chcete  **-**  (znaménka minus).  
  
4.  Název první popisek otazník **minusLeftLabel**.  
  
5.  Název druhé popisek otazník **minusRightLabel**.  
  
6.  Název **NumericUpDown** řízení **rozdíl**.  
  
7.  Vložte pět ovládacích prvků dvakrát.  
  
8.  Pro třetí řádek název první popisek **timesLeftLabel**, změna druhý štítku **Text** vlastnost **×** (znaménko násobení), název třetí popisek **timesRightLabel**a název ovládacího prvku NumericUpDown **produktu**.  
  
9. U čtvrtého řádku název první popisek **dividedLeftLabel**, změna druhý štítku **Text** vlastnost **÷** (znaménko dělení), název třetí popisek  **dividedRightLabel**a název ovládacího prvku NumericUpDown **koeficient**.  
  
    > [!NOTE]
    >  Můžete zkopírovat × přihlašovací násobení a dělení přihlašovací ÷ z tohoto kurzu a vložit do formuláře.  
  
### <a name="to-add-a-start-button-and-set-the-tab-index-order"></a>Chcete-li přidat tlačítko start a nastavte pořadí pořadových  
  
1.  Přidat **tlačítko** řízení z panelu nástrojů a nastavte její **(název)** vlastnost **startButton**.  
  
2.  Nastavte **Text** vlastnost **spustit kvízu**.  
  
3.  Nastavit velikost písma na **14**.  
  
4.  Nastavte **AutoSize** vlastnost **True**, což způsobí, že tlačítko Automatická změna velikosti podle textu.  
  
5.  Center tlačítko v dolní části formuláře.  
  
6.  Nastavte hodnotu **pořadové číslo prvku** vlastnost **startButton** řídit k **1**.  
  
    > [!NOTE]
    >  **Pořadové číslo prvku** vlastnost nastaví pořadí ovládacích prvků, když příjemce kvízu s časovým limitem vybere klávesy Tab. Pokud chcete zobrazit, jak to funguje, otevřete dialogové okno všechny (například na řádku nabídek zvolte **soubor**, **otevřete**) a potom vyberte klávesy Tab několikrát. Podívejte se jak kurzor přesune ovládací pokaždé, když, abyste zvolili klávesy Tab. Při vytváření tohoto formuláře se rozhodla programátorem pořadí.  
  
7.  Nastavte hodnotu **pořadové číslo prvku** vlastnost ovládacího prvku NumericUpDown součet k **2**, pro ovládací prvek rozdíl k **3**, pro ovládací prvek produktu na **4**a k ovládacímu prvku na **5**.  
  
     Formulář by měl vypadat jako na následujícím obrázku.  
  
     ![Počáteční formulář matematického kvízu](../ide/media/express_formlaidout.png "Express_FormLaidOut")  
Počáteční formulář matematického kvízu  
  
8.  K ověřte, zda **pořadové číslo prvku** vlastnost funguje podle očekávání, uložte a spusťte svůj program výběrem klávesy F5 nebo výběrem **ladění**, **spustit ladění** v řádku nabídek a poté zvolte klávesy Tab několikrát.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 2: Vytvořte náhodný problém s přidáním](../ide/step-2-create-a-random-addition-problem.md).  
  
-   Přejděte k tématu Přehled, najdete v části [kurzu 2: vytvoření vypršel časový limit matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).