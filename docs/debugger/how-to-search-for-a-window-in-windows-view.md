---
title: 'Postupy: Hledání okna v zobrazení pro Windows | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- windows, searching in Windows view
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 317b815595d6e7bca820b730a2761113e588dded
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53837063"
---
# <a name="how-to-search-for-a-window-in-windows-view"></a>Postupy: Hledání okna v zobrazení oken
Můžete vyhledat konkrétní okno v zobrazení pro Windows s použitím jeho popisovač, titulků, třídy nebo kombinace jeho titulek a třídy jako kritéria hledání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně zobrazí vlastnosti vybrané okno ve stromové struktuře okna.  
  
 Začněte s stromu i na druhé úrovni (všechna okna, které jsou podřízené plochy), takže můžete určit úroveň plochy windows tak, že jejich název třídy a název. Po výběru úrovně desktop okno, můžete rozšířit tuto úroveň najít konkrétní podřízené okno.  
  
### <a name="to-search-for-a-window-in-windows-view"></a>Hledání okna v zobrazení pro Windows  
  
1. Uspořádat okna tak tohoto nástroje Spy ++, [zobrazení Windows](../debugger/windows-view.md) okna a okna cílové jsou vidět.  
  
2. Z **hledání** nabídce zvolte **najít okno**.  
  
    [Dialogové okno hledání](../debugger/window-search-dialog-box.md) otevře.  
  
   > [!TIP]
   >  Chcete-li přehlednost obrazovky, vyberte **skrýt Spy** možnost. Tato možnost ukrývá hlavního okna nástroje Spy ++ a zůstane jen **okno hledání** dialogové okno viditelné nad vaší aplikace. Obnovení hlavního okna nástroje Spy ++, po kliknutí na **OK** nebo **zrušit**, nebo pokud zrušíte výběr **skrýt Spy ++** možnost.  
  
3. Přetáhněte **tažením nástroje hledání** intervalu cíl. Při přetahování nástroj, **okno hledání** dialogové okno zobrazí podrobnosti o vybrané okno.  
  
   - nebo –  
  
     Pokud znáte popisovač okna chcete (například z ladicího programu), můžete zadat ho **zpracování** pole.  
  
   - nebo –  
  
     Pokud víte, titulek a/nebo třídy okna, chcete, můžete je zadat **titulek** a **třídy** textová pole a zrušte zaškrtnutí **zpracování** textového pole.  
  
4. Zvolte **nahoru** nebo **dolů** pro počáteční směr hledání.  
  
5. Klikněte na **OK**.  
  
    Pokud je nalezen odpovídající okno, je zvýrazněn [zobrazení Windows](../debugger/windows-view.md) okna.