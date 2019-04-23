---
title: 'Postupy: Zobrazení informací trasování WPF | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: be3c6859-06e1-459e-9fd0-46375b5f55ef
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c9642902bf334ce83f95a9113059683f183c6116
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60113778"
---
# <a name="how-to-display-wpf-trace-information"></a>Postupy: Zobrazení informací trasování WPF
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] může přijímat informace o trasování ladění z aplikace WPF a zobrazení těchto informací v **výstup** okna. Chcete-li zobrazit informace o trasování ladění, musí být povoleno trasování WPF.  
  
 Můžete povolit trasování WPF ve vašem souboru App.Config nebo programově pomocí <xref:System.Diagnostics.PresentationTraceSources> třídy. Snadný způsob, jak povolit trasování WPF je použít **možnosti** okna. WPF trasování pro webové aplikace se nepodporuje.  
  
### <a name="to-enable-or-customize-wpf-trace-information"></a>Pokud chcete povolit nebo upravte informace o trasování WPF  
  
1. Na **nástroje** nabídce vyberte možnost **možnosti**.  
  
2. V **možnosti** otevřete dialogové okno, v poli na levé straně **ladění** uzlu.  
  
3. V části **ladění**, klikněte na tlačítko **okno výstup**.  
  
4. V části **obecné nastavení výstupní**vyberte **výstup všech ladění**.  
  
5. Do pole na pravé straně, vyhledejte **nastavení trasování WPF**.  
  
6. Otevřít **nastavení trasování WPF** uzlu.  
  
7. V části **nastavení trasování WPF**, klikněte na tlačítko kategorie nastavení, které chcete povolit (třeba **datové vazby**).  
  
     Ovládací prvek rozevíracího seznamu se zobrazí ve sloupci nastavení vedle možnosti **datové vazby** nebo libovolné kategorie jste klikli.  
  
8. Klikněte na rozevírací seznam a vyberte typ trasování informací, které chcete zobrazit: **Všechny**, **kritické**, **chyba**, **upozornění**, **informace**, **podrobné**, nebo **ActivityTracing**.  
  
     **Kritické** Zapíná trasování pouze kritické události.  
  
     **Chyba** Zapíná trasování kritické události a chyby.  
  
     **Upozornění** umožňuje trasování kritický, chyby a upozornění události.  
  
     **Informace o** Zapíná trasování kritické, chyba, upozornění a informace události.  
  
     **Podrobné** Zapíná trasování kritické, chyba, upozornění, informace a podrobné událostí.  
  
     **ActivityTracing** Zapíná trasování událostí, zastavení, spuštění, pozastavit, přenos a pokračovat.  
  
     Další informace o těchto úrovní trasování informací význam, naleznete v tématu <xref:System.Diagnostics.SourceLevels>.  
  
9. Klikněte na **OK**.  
  
### <a name="to-disable-wpf-trace-information"></a>Chcete-li zakázat informace o trasování WPF  
  
1. Na **nástroje** nabídce vyberte možnost **možnosti**.  
  
2. V **možnosti** otevřete dialogové okno, v poli na levé straně **ladění** uzlu.  
  
3. V části **ladění**, klikněte na tlačítko **okno výstup**.  
  
4. Do pole na pravé straně, vyhledejte **nastavení trasování WPF**.  
  
5. Otevřít **nastavení trasování WPF** uzlu.  
  
6. V části **nastavení trasování WPF**, klikněte na tlačítko kategorie nastavení, které chcete povolit (třeba **datové vazby**).  
  
     Ovládací prvek rozevíracího seznamu se zobrazí ve sloupci nastavení vedle možnosti **datové vazby** nebo libovolné kategorie jste klikli.  
  
7. Klikněte na rozevírací seznam a vyberte **vypnout**.  
  
8. Klikněte na **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Ladění WPF](../debugger/debugging-wpf.md)
