---
title: "Postupy: zobrazení a úpravy kódu s použitím funkce Náhled definice (Alt + F12) | Microsoft Docs"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45f3dd20-902a-4047-8cca-9f18216123f4
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bf0dd4ab4a60dc7cfdfd351aee59c4942f75ef69
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-view-and-edit-code-by-using-peek-definition-altf12"></a>Postupy: Zobrazení a úpravy kódu s použitím funkce Náhled definice (ALT+F12)
Můžete použít **funkce Náhled definice** příkaz k zobrazení a úpravy kódu, aniž by se přepnula od kód, který píšete. **Funkce Náhled definice** a **přejít k definici** zobrazovat stejné informace, ale **funkce Náhled definice** zobrazuje v místním okně, a **přejít k definici** ukazuje kód v okně samostatného kódu. **Přejít k definici** způsobí, že váš kontext (tedy active kódu – okno, aktuálního řádku a pozice kurzoru) přejděte do okna Definice kódu. Pomocí **funkce Náhled definice**, můžete zobrazit a upravit definici a pohyb v souboru definice a zachovat přitom vaše místní v původní soubor kódu.  
  
 Můžete použít **funkce Náhled definice** s kódem jazyka C#, Visual Basic a C++. V jazyce Visual Basic **funkce Náhled definice** zobrazuje odkaz **Prohlížeč objektů** pro symboly, které nemají definice metadat (například typy rozhraní .NET Framework, které jsou integrované v).  
  
## <a name="working-with-peek-definition"></a>Práce s náhledem definice  
  
#### <a name="to-open-a-peek-definition-window"></a>Otevření okna Náhled definice    
1.  Definice můžete prohlížet výběrem **funkce Náhled definice** z kontextové nabídky pro člena, který chcete prozkoumat. V aplikaci Visual Studio 2017 verze 15,4 a novější, pokud je povolená možnost, můžete lze také prohlížet definici pomocí myši stisknutím klávesy **Ctrl** (nebo jiné modifikátor) a kliknutím na název člena. Nebo z klávesnice, stiskněte klávesu **Alt + F12**.  
  
     Na tomto obrázku **funkce Náhled definice** okna pro metodu, která je s názvem `Print()`:  
  
     ![Prohlížení okno](../ide/media/peekwindow.png "PeekWindow")  
  
     Definice okna se zobrazí pod `printer.Print("Hello World!")` řádku v původní soubor. Okno neskryje žádný kód v původním souboru. Řádky, které následují `printer.Print("Hello World!")` vyskytovat v části okna definice.  
  
2.  Kurzor můžete přesunout na jiné místo v okně definice kódu. Můžete také stále pohybovat v okně původní kód.  
  
3.  Můžete zkopírovat řetězec v okně definice a vložit ho do původního kódu. Můžete také přetáhnout řetězec z okna definice do původního kódu, aniž by byl v okně definice odstraněn.  
  
4.  Definice okno můžete zavřít výběrem **Esc** klíč nebo **zavřete** tlačítko na kartě okno definice.  
  
#### <a name="to-open-a-peek-definition-window-from-within-a-peek-definition-window"></a>Otevření okna Náhled definice z okna Náhled definice    
-   Pokud již máte **funkce Náhled definice** okno otevřít, můžete volat **funkce Náhled definice** znovu na kód v okně. Otevře se jiné okno definice. Vedle karty okna definice se zobrazí sada teček s popisem cesty, která slouží k navigaci mezi okny definice. Popisek tlačítka na každé tečce zobrazuje název souboru a cestu k souboru definice, který tečka přestavuje.  
  
     ![Funkce Náhled okna v rámci časového období funkce Náhled](../ide/media/peekwithinpeek.png "PeekWithinPeek")  
  
#### <a name="to-use-peek-definition-with-multiple-results"></a>Použití náhledu definice s více výsledky    
-   Pokud používáte **funkce Náhled definice** na kód, který má více než jednu definici (například částečné třídy), zobrazí se seznam výsledků napravo od definice zobrazení kódu. Můžete zvolit některý z výsledků v seznamu k zobrazení jeho definice.  
  
     ![Funkce Náhled okno z více výsledků](../ide/media/peekmultiple.png "PeekMultiple")  
  
#### <a name="to-edit-inside-the-peek-definition-window"></a>Provádění úprav v okně Náhled definice    
-   Když spustíte upravit uvnitř **funkce Náhled definice** okno, soubor, který upravujete, automaticky se otevře jako samostatné kartě v editoru kódu a odráží změny, které jste udělali. Můžete vytvořit, vrátit zpět a změny uložit do **funkce Náhled definice** okno a na kartě budou nadále tyto změny projevily. I když zavřete **funkce Náhled definice** okno bez uložení změn, můžete nastavit, vrátit zpět a další změny uložit na kartě Výběr přesně tam, kde jste přestali v **funkce Náhled definice** okno.  
  
     ![Úpravy v rámci časového období funkce Náhled](../ide/media/peekedit.png "PeekEdit")  
  
#### <a name="to-change-options-for-peek-definition"></a>Chcete-li změnit možnosti pro prohlížení definice  
1. Přejděte na **nástroje**, **možnosti**, **textového editoru**, **Obecné**.  

2. Vyberte možnost **otevřít v zobrazení funkce Náhled definice**.  

3. Klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.  

     ![Nastavení možnosti kliknutí myší funkce Náhled definice](../ide/media/editor_options_peek_view.png)  

#### <a name="to-use-keyboard-shortcuts-for-peek-definition"></a>Použití klávesových zkratek pro náhled definice    
-   Můžete použít tyto klávesové zkratky s **funkce Náhled definice** okno:  
  
    |Funkce|Klávesová zkratka|  
    |-------------------|:-----------------------:|  
    |Otevřít okno definice|Alt+F12|  
    |Zavřít okno definice|Esc|  
    |Povýšit okno definice na běžnou kartu dokumentu|Shift+Alt+Home|  
    |Navigace mezi okny definice|Ctrl+Alt+- a Ctrl+Alt+=|  
    |Navigace mezi několika výsledky|F8 a Shift+F8|  
    |Přepnout mezi oknem editoru kódu a oknem definice|Shift+Esc|  
  
    > [!NOTE]
    >  Můžete také použít stejné klávesové zkratky úprav kódu v **funkce Náhled definice** okno jako můžete použít na jiném místě v sadě Visual Studio.  
  
## <a name="see-also"></a>Viz také  
[Navigace v kódu](../ide/navigating-code.md)  
[Přejděte do definice a funkce Náhled definice](../ide/go-to-and-peek-definition.md)  
[Tipy pro vyšší produktivitu](../ide/productivity-tips-for-visual-studio.md)