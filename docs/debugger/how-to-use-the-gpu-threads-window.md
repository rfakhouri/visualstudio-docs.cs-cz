---
title: "Zobrazení vláken GPU v ladicím programu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.gputthreads
- vs.debug.gputhreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, GPU threads window
ms.assetid: c647c502-a9f0-48e0-a430-976744a5fa51
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b4782a1650034424d2616e47f46e07cec4d01ae5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-gpu-threads-window"></a>Postupy: Použití okna vláken GPU
V okně vláken GPU můžete prozkoumat a práce s vlákny, které jsou spuštěny na grafického procesoru v aplikaci, kterou ladíte. Další informace o aplikacích, které běží na GPU najdete v tématu [přehled produktu C++ AMP](/cpp/parallel/amp/cpp-amp-overview).  
  
 Okna vláken GPU obsahuje tabulku, ve kterém každý řádek představuje sadu GPU vláken, které mají stejné hodnoty ve všech sloupců. Můžete řadit, změnit pořadí, odebrat a seskupit položky, které jsou ve sloupcích. Můžete příznak, odstranění označení, zmrazení (Pozastavit) a uvolnění vláken (pokračovat) z okna vláken GPU. V následujících sloupcích se zobrazují v okna vláken GPU:  
  
-   Příznak sloupec, ve kterém můžete označit vlákno, které chcete věnujte zvláštní pozornost.  
  
-   Aktuální vlákno sloupec, ve kterém žlutá šipka označuje aktuální vlákno.  
  
-   **Počtu vláken** sloupec, který zobrazuje počet vláken ve stejném umístění.  
  
-   **Řádku** sloupec, který zobrazí řádek kódu, kde se nachází každou skupinu vláken.  
  
-   **Adresu** sloupec, který zobrazí adresa instrukce, kde se nachází každou skupinu vláken. Ve výchozím nastavení je tento sloupec skrytá.  
  
-   **Umístění** sloupec, který je umístění, ve zdrojovém kódu.  
  
-   **Stav** sloupec, který zobrazuje, zda vlákno je aktivní, blokované, není spuštěn nebo dokončení.  
  
-   **Dlaždici** sloupec, který zobrazí dlaždice index pro vláken v řádku.  
  
 Záhlaví tabulky se zobrazuje dlaždice a vlákno se zobrazuje.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-display-the-gpu-threads-window"></a>Pro zobrazení okna vláken GPU  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídky projektu a zvolte **vlastnosti**.  
  
2.  V **stránky vlastností** okna pro projekt, v části **vlastnosti konfigurace**, zvolte **ladění**.  
  
3.  V **ladicí program ke spuštění** seznamu, vyberte **místní ladicí program Windows**. V **ladicí program typu** seznamu, vyberte **GPU pouze**. Musíte zvolit tento ladicí program na přerušení na zarážky v kódu, který běží na GPU.  
  
4.  Vyberte **OK** tlačítko.  
  
5.  Nastavte zarážky v kódu GPU.  
  
6.  Na řádku nabídek zvolte **ladění**, **spustit ladění**. Počkejte, než aplikace k dosažení zarážku.  
  
7.  Jednoho řádku nabídek zvolte **ladění**, **Windows**, **vláken GPU**.  
  
### <a name="to-switch-to-a-different-thread"></a>Přejděte na jiném podprocesu  
  
-   Dvakrát klikněte na sloupec. (Klávesové: Vyberte řádek a zadejte zvolte.)  
  
### <a name="to-display-a-particular-tile-and-thread"></a>Chcete-li zobrazit konkrétní dlaždice a přístup z více vláken  
  
1.  Vyberte **rozbalte vláken přepínači** tlačítka na okna vláken GPU.  
  
2.  Do textových polí zadejte hodnoty dlaždice a přístup z více vláken.  
  
3.  Zvolte tlačítko se šipkou na něm.  
  
### <a name="to-display-or-hide-a-column"></a>Chcete-li zobrazit nebo skrýt sloupce  
  
-   Otevřete místní nabídku pro okna vláken GPU, zvolte **sloupce**a potom vyberte sloupec, který chcete zobrazit nebo skrýt.  
  
### <a name="to-sort-by-a-column"></a>Chcete-li řadit podle sloupce  
  
-   Vyberte záhlaví sloupce.  
  
### <a name="to-group-threads"></a>Do skupiny vláken  
  
-   Otevřete místní nabídku pro okna vláken GPU, zvolte **Group By**a pak vyberte jednu z zobrazují názvy sloupců. Zvolte **žádné** oddělení vláken.  
  
### <a name="to-freeze-or-thaw-a-row-of-threads"></a>Zablokování nebo odblokování řádek vláken  
  
-   Otevřete místní nabídku pro řádek a zvolte **Freeze** nebo **odblokování**.  
  
### <a name="to-flag-or-unflag-a-row-of-threads"></a>Příznak nebo odstranění označení řádek vláken  
  
-   Vyberte sloupec příznak pro vlákno, nebo otevřete místní nabídku pro vlákno a zvolte **příznak** nebo **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Chcete-li zobrazit pouze označení vlákna  
  
-   Klikněte na tlačítko příznak v okna vláken GPU.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Postupy: použití okna paralelního sledování](../debugger/how-to-use-the-parallel-watch-window.md)   
 [Návod: Ladění aplikace C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)