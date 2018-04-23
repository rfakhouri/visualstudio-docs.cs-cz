---
title: 'Postupy: hledání okna v zobrazení oken | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- windows, searching in Windows view
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4333a79e76358216ce87697975dcb54173570534
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-search-for-a-window-in-windows-view"></a>Postupy: Hledání okna v zobrazení oken
Můžete hledat konkrétní okna v zobrazení oken pomocí svého popisovače, popisek, třída nebo kombinaci její popisek a třída jako kritéria vyhledávání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně zobrazí ve stromu okno atributy vybrané okno.  
  
 Začněte s stromu rozšířit tak, aby druhé úrovně (všechny systémy windows, které jsou podřízené plochy), takže můžete identifikovat windows desktop úrovni podle jejich název třídy a titulu. Jakmile jste vybrali okno úrovni plocha, můžete rozbalit této úrovni najít konkrétní podřízeného okna.  
  
### <a name="to-search-for-a-window-in-windows-view"></a>K vyhledání okna v zobrazení oken  
  
1.  Uspořádat váš windows proto tohoto nástroje Spy ++, [zobrazení oken](../debugger/windows-view.md) se zobrazí okno a cílové okno.  
  
2.  Z **vyhledávání** nabídce zvolte **najít okno**.  
  
     [Dialogové okno hledání oken](../debugger/window-search-dialog-box.md) otevře.  
  
    > [!TIP]
    >  Chcete-li přehlednost obrazovky, vyberte **skrýt Spy** možnost. Tato možnost ukrývá hlavní okno nástroje Spy ++ a zanechá pouze **hledání oken** dialogové okno zobrazené na jiné aplikace. Hlavní okno nástroje Spy ++ obnovení po kliknutí na tlačítko **OK** nebo **zrušit**, nebo když zrušíte **skrýt nástroje Spy ++** možnost.  
  
3.  Přetáhněte **nástroj pro vyhledávání** přes cílové okno. Přetahování nástroj **hledání oken** dialogové okno zobrazí podrobnosti o na vybrané okno.  
  
     - nebo –  
  
     Pokud znáte popisovač okna chcete (například z ladicí program), můžete ho zadat **zpracování** pole.  
  
     - nebo –  
  
     Pokud víte, popisek nebo třídě okna chcete, můžete je zadat **popisek** a **třída** textová pole a zrušte zaškrtnutí **zpracování** textového pole.  
  
4.  Zvolte **až** nebo **dolů** pro počáteční směr hledání.  
  
5.  Click **OK**.  
  
     Pokud je nalezen odpovídající okna, je označený na [zobrazení oken](../debugger/windows-view.md) okno.