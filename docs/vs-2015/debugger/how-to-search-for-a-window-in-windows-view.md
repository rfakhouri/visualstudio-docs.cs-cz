---
title: 'Postupy: hledání okna v zobrazení pro Windows | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- windows, searching in Windows view
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 043e3e92004eb5b0995bc285e90a138f4dc902f4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669588"
---
# <a name="how-to-search-for-a-window-in-windows-view"></a>Postupy: Hledání okna v zobrazení oken
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: hledání okna v zobrazení pro Windows](https://docs.microsoft.com/visualstudio/debugger/how-to-search-for-a-window-in-windows-view).  
  
Můžete vyhledat konkrétní okno v zobrazení pro Windows s použitím jeho popisovač, titulků, třídy nebo kombinace jeho titulek a třídy jako kritéria hledání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně zobrazí vlastnosti vybrané okno ve stromové struktuře okna.  
  
 Začněte s stromu i na druhé úrovni (všechna okna, které jsou podřízené plochy), takže můžete určit úroveň plochy windows tak, že jejich název třídy a název. Po výběru úrovně desktop okno, můžete rozšířit tuto úroveň najít konkrétní podřízené okno.  
  
### <a name="to-search-for-a-window-in-windows-view"></a>Hledání okna v zobrazení pro Windows  
  
1.  Uspořádat okna tak tohoto nástroje Spy ++, [zobrazení Windows](../debugger/windows-view.md) okna a okna cílové jsou vidět.  
  
2.  Z **hledání** nabídce zvolte **najít okno**.  
  
     [Dialogové okno hledání](../debugger/window-search-dialog-box.md) otevře.  
  
    > [!TIP]
    >  Chcete-li přehlednost obrazovky, vyberte **skrýt Spy** možnost. Tato možnost ukrývá hlavního okna nástroje Spy ++ a zůstane jen **okno hledání** dialogové okno viditelné nad vaší aplikace. Obnovení hlavního okna nástroje Spy ++, po kliknutí na **OK** nebo **zrušit**, nebo pokud zrušíte výběr **skrýt Spy ++** možnost.  
  
3.  Přetáhněte **tažením nástroje hledání** intervalu cíl. Při přetahování nástroj, **okno hledání** dialogové okno zobrazí podrobnosti o vybrané okno.  
  
     – nebo –  
  
     Pokud znáte popisovač okna chcete (například z ladicího programu), můžete zadat ho **zpracování** pole.  
  
     – nebo –  
  
     Pokud víte, titulek a/nebo třídy okna, chcete, můžete je zadat **titulek** a **třídy** textová pole a zrušte zaškrtnutí **zpracování** textového pole.  
  
4.  Zvolte **nahoru** nebo **dolů** pro počáteční směr hledání.  
  
5.  Klikněte na tlačítko **OK**.  
  
     Pokud je nalezen odpovídající okno, je zvýrazněn [zobrazení Windows](../debugger/windows-view.md) okna.



