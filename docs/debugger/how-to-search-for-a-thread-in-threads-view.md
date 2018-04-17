---
title: 'Postupy: hledání vlákna v zobrazení vláken | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- threads, searching
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2d582a10e2738b69724765477ee64c47e8cb68c3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-search-for-a-thread-in-threads-view"></a>Postupy: Hledání vlákna v zobrazení vláken
Můžete hledat konkrétní vlákna v zobrazení vláken pomocí jeho ID nebo modul řetězce vlákno jako kritéria vyhledávání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně se zobrazí atributy vybrané vlákno ve stromové struktuře přístup z více vláken.  
  
### <a name="to-search-for-a-thread-in-threads-view"></a>Hledání vlákna v zobrazení vláken  
  
1.  Uspořádat váš windows proto tohoto nástroje Spy ++ a aktivní [zobrazení vláken](../debugger/threads-view.md) okna jsou viditelné.  
  
2.  Z **vyhledávání** nabídce zvolte **najít vláken**.  
  
     [Dialogové okno vláken hledání](../debugger/thread-search-dialog-box.md) otevře.  
  
3.  Zadejte ID vlákna nebo řetězec modulu jako kritéria vyhledávání.  
  
4.  Vymažte všechna pole, pro které nechcete zadat hodnoty.  
  
    > [!TIP]
    >  Chcete-li najít všechna vlákna vlastníkem modul, zrušte **přístup z více vláken** textového pole a typ modulu názvu **modulu** pole. Potom pomocí **najít další** Hledat další vlákna.  
  
5.  Zvolte **až** nebo **dolů** pro počáteční směr hledání.  
  
6.  Click **OK**.  
  
 Pokud je nalezen odpovídající vlákno, zvýrazní se v okně zobrazení vláken.