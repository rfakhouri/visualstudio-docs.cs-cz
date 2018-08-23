---
title: 'Postupy: hledání procesu v zobrazení procesů | Dokumentace Microsoftu'
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
- Processes view
- processes, searching for
ms.assetid: 7cb97b37-4a95-4f1b-9eee-4910aa9c115b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ebb0c6a13db0fdc1a586a78038f759c59f8b110
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683385"
---
# <a name="how-to-search-for-a-process-in-processes-view"></a>Postupy: Hledání procesu v zobrazení procesů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: hledání procesu v zobrazení procesů](https://docs.microsoft.com/visualstudio/debugger/how-to-search-for-a-process-in-processes-view).  
  
Můžete vyhledat konkrétního procesu v zobrazení procesů pomocí jeho ID nebo modul řetězec proces jako kritéria hledání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně se zobrazí atributy vybraný proces strom procesu.  
  
### <a name="to-search-for-a-process-in-processes-view"></a>Hledání procesu v zobrazení procesů  
  
1.  Uspořádat okna tak tohoto nástroje Spy ++ a aktivní [zobrazení procesy](../debugger/processes-view.md) okna jsou viditelné.  
  
2.  Z **hledání** nabídce zvolte **najít proces**  
  
     [Dialogové okno hledání procesů](../debugger/process-search-dialog-box.md) otevře.  
  
3.  Zadejte ID procesu nebo řetězce modulu, jako kritéria hledání.  
  
4.  Zrušte zaškrtnutí všech polí, u kterých nechcete k určení hodnot.  
  
    > [!TIP]
    >  Pokud chcete najít všechny procesy vlastní modul, zrušte **procesu** pole a zadejte název modulu v **modulu** pole. Pak pomocí **najít další** chcete pokračovat ve vyhledávání pro procesy.  
  
5.  Zvolte **nahoru** nebo **dolů** pro počáteční směr hledání.  
  
6.  Klikněte na tlačítko **OK**.  
  
 Pokud je nalezen odpovídající proces, je zvýrazněn **zobrazení procesů** okna.



