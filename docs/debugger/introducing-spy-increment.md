---
title: "Představení nástroje Spy ++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Spy++
ms.assetid: 733b514b-63a9-402d-89aa-4f0416766655
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cb12ef13e73e33b213d2b8ca79c2439b517fbda9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="introducing-spy"></a>Představení nástroje Spy++
Nástroje Spy ++ umožňuje provádět následující úlohy:  
  
-   Zobrazí grafický stromu vztahů mezi objekty systému. Mezi ně patří [procesy](../debugger/processes-view.md), [vláken](../debugger/threads-view.md), a [windows](../debugger/windows-view.md).  
  
-   Hledání pro zadané [windows](../debugger/how-to-search-for-a-window-in-windows-view.md), [vláken](../debugger/how-to-search-for-a-thread-in-threads-view.md), [procesy](../debugger/how-to-search-for-a-process-in-processes-view.md), nebo [zprávy](../debugger/how-to-search-for-a-message-in-messages-view.md).  
  
-   Zobrazit vlastnosti vybrané [windows](../debugger/how-to-display-window-properties.md), [vláken](../debugger/how-to-display-thread-properties.md), [procesy](../debugger/how-to-display-process-properties.md), nebo [zprávy](../debugger/how-to-display-message-properties.md).  
  
-   Vyberte okno, vlákno, proces nebo zprávy přímo v zobrazení.  
  
-   Použití [nástroj pro vyhledávání](../debugger/how-to-use-the-finder-tool.md) vyberte okno podle umístění ukazatele myši.  
  
-   Nastavit [zprávy možnost](../debugger/how-to-open-messages-view-from-find-window.md) pomocí parametrů výběr komplexní zprávu protokolu.  
  
 Nástroje Spy ++ má panelu nástrojů a hypertextové odkazy, které umožňují pracovat rychleji. Poskytuje také **aktualizovat** příkaz k aktualizaci zobrazení aktivní **nástroj pro vyhledávání oken** aby snadnější, činnosti a **písma** dialogové okno pro přizpůsobení zobrazení systému windows. Kromě toho nástroje Spy ++ umožňuje uložení a obnovení uživatelských předvoleb.  
  
 V různých nástroje Spy ++ systému windows kliknete pravým tlačítkem na zobrazení místní nabídky často používané příkazy. Se zobrazí příkazy, které závisí na to, kde je ukazatele. Například pokud kliknete pravým tlačítkem na položku v zobrazení okna a vybrané okno je viditelná, pak levým na **zvýrazněte** v zástupce nabídky způsobí, že ohraničení vybrané okno na flash, takže může být umístěn snadněji.  
  
> [!NOTE]
>  Dva další nástroje, které se podobají nástroje Spy ++: PView, která zobrazuje podrobnosti o procesy a vláken a DDESPY. EXE, což vám umožní monitorovat dynamické výměny dat (DDE) zprávy.  
  
## <a name="64-bit-operating-systems"></a>64bitové verze operačních systémů  
 Existují dvě verze nástroje Spy ++. První verze, s názvem nástroje Spy ++ (spyxx.exe), je určená k zobrazení zprávy odeslané do okna, ve kterém je spuštěný v 32bitový proces. Například Visual Studio běží v 32bitový proces. Proto můžete použít nástroje Spy ++ zobrazíte zprávy odeslané do **Průzkumníku řešení**. Protože výchozí konfiguraci pro většinu sestavení v sadě Visual Studio je spustit proces 32-bit, tento první verze součásti nástroje Spy ++ je ten, který je [na k dispozici **nástroje** nabídky](../debugger/how-to-start-spy-increment.md) v sadě Visual Studio.  
  
 Druhá verze, s názvem nástroje Spy ++ (64 bitů) (spyxx_amd64.exe) slouží k zobrazení zprávy odeslané do okna, které běží v procesu 64-bit. Na 64bitový operační systém, například Poznámkový blok běží v procesu 64-bit. Proto můžete nástroje Spy ++ (64 bitů) k zobrazení zprávy odeslané do poznámkového bloku. Nástroje Spy ++ (64 bitů) se obvykle nachází v  
  
 .. \\ *Instalační složka nástroje visual Studio*\Common7\Tools\spyxx_amd64.exe.  
  
 Jednu z verzí nástroje Spy ++ můžete spustit přímo z příkazového řádku.  
  
> [!NOTE]
>  I když se název souboru (64 bitů) nástroje Spy ++ obsahuje "amd", běží na všech x64 operačního systému Windows.  
  
## <a name="see-also"></a>Viz také 
 [Postupy: spuštění nástroje Spy ++](../debugger/how-to-start-spy-increment.md)   
 [Použití nástroje Spy ++](../debugger/using-spy-increment.md)   
 [Zobrazení nástroje Spy ++](../debugger/spy-increment-views.md)   
 [Referenční dokumentace nástroje Spy++](../debugger/spy-increment-reference.md)