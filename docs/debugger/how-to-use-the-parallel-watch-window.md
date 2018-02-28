---
title: "Nastavovat sledování na proměnné v paralelních vláken | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.parallelwatch
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, parallel watch window
ms.assetid: 28004d9b-420c-48f7-b80e-ab1519802558
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 570f77cddede91a81dc15200ebcf02b27f1a4f2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="set-a-watch-on-variables-in-parallel-threads-in-visual-studio"></a>Nastavovat sledování na proměnné v paralelních vláken v sadě Visual Studio
V okně paralelního sledování můžete současně zobrazit hodnoty, které obsahuje jeden výraz na více vláken. Každý řádek představuje vlákno, které běží v aplikaci, ale může být reprezentován vlákno ve více řádků. Přesněji řečeno každý řádek představuje volání funkce, jejíž funkce podpis odpovídá funkce na aktuální rámec zásobníku. Můžete řadit, změnit pořadí, odebrat a seskupit položky, které jsou ve sloupcích. Můžete příznak, odstranění označení, zmrazení (Pozastavit) a uvolnění vláken (pokračovat). V následujících sloupcích se zobrazují v **paralelního sledování** okno:  
  
-   Příznak sloupec, ve kterém můžete označit vlákno, které chcete věnujte zvláštní pozornost.  
  
-   Aktuální vlákno sloupec, ve kterém žlutá šipka označuje aktuální vlákno (zelenou šipku s složené tail znamená, že má jiný aktuální vlákno aktuálního kontextu ladicího programu).  
  
-   Konfigurovat sloupec, který může zobrazit počítače, procesu, dlaždice, úloh a přístup z více vláken.  
  
    > [!TIP]
    >  Zobrazí úloh informací ve **paralelního sledování** okna, je nutné nejprve otevřít **úloh** okno.  
  
-   Prázdné *Přidat kukátko* sloupce, ve kterých můžete zadat výrazy, které chcete sledovat.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-display-the-parallel-watch-window"></a>Pro zobrazení okna paralelního sledování  
  
1.  Nastavte zarážky v kódu.  
  
2.  Na řádku nabídek zvolte **ladění**, **spustit ladění**. Počkejte, než aplikace k dosažení zarážku.  
  
3.  Na řádku nabídek zvolte **ladění**, **Windows**, **paralelního sledování**a potom zvolte Okno sledování. Můžete otevřít až čtyři windows.  
  
### <a name="to-add-a-watch-expression"></a>Chcete-li přidat výraz  
  
-   Vyberte jeden prázdný *Přidat kukátko* sloupce a potom zadejte výraz.  
  
### <a name="to-flag-or-unflag-a-thread"></a>Příznak nebo odstranění označení vlákna  
  
-   Vyberte sloupec příznak pro řádek (první sloupec) nebo otevřete místní nabídku pro vlákno a zvolte **příznak** nebo **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Chcete-li zobrazit pouze označení vlákna  
  
-   Vyberte **zobrazit jenom příznakem** tlačítko v levém horním rohu **paralelního sledování** okno.  
  
### <a name="to-switch-to-another-thread"></a>Chcete-li přepnout na jiné vlákno  
  
-   Klikněte dvakrát na sloupci aktuální vlákno (druhý sloupec). (Klávesové: Vyberte řádek, a stiskněte klávesu Enter.)  
  
### <a name="to-sort-a-column"></a>Chcete-li seřadit sloupec  
  
-   Vyberte záhlaví sloupce.  
  
### <a name="to-group-threads"></a>Do skupiny vláken  
  
-   Otevřete místní nabídku pro okna paralelního sledování, zvolte **Group By**a potom vyberte položku příslušné podnabídky.  
  
### <a name="to-freeze-or-thaw-threads"></a>K zablokování nebo odblokování vláken  
  
-   Otevřete místní nabídku pro řádek a zvolte **Freeze** nebo **odblokování**.  
  
### <a name="to-export-the-data-in-the-parallel-watch-window"></a>Exportovat data z okna paralelního sledování  
  
-   Vyberte **otevřít v aplikaci Excel** tlačítko a potom zvolte **otevřít v aplikaci Excel** nebo **exportovat do souboru CSV**.  
  
### <a name="to-filter-by-a-boolean-expression"></a>Filtrovat podle logický výraz  
  
-   Zadejte logický výraz v **filtrovat podle logický výraz** pole. Ladicí program vyhodnotí výraz pro každý kontext přístup z více vláken. Pouze řádky, kde je hodnota `true` jsou zobrazeny.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Postupy: použití okna vláken GPU](../debugger/how-to-use-the-gpu-threads-window.md)   
 [Návod: Ladění aplikace C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)