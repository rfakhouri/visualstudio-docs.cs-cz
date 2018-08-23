---
title: Karta zprávy, dialogové okno možností zpráv | Dokumentace Microsoftu
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
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8048c63ed9b9f049ed171002dfcc612fc9361569
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670555"
---
# <a name="messages-tab-message-options-dialog-box"></a>Karta Zprávy, dialogové okno možností zpráv
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [karta zprávy, dialogové okno možností zpráv](https://docs.microsoft.com/visualstudio/debugger/messages-tab-message-options-dialog-box).  
  
Použití **zprávy** kartu, vyberte v seznamu typů zpráv, které [zobrazení zpráv](../debugger/messages-view.md)a určení kritérií hledání zpráv. Chcete-li zobrazit [dialogové okno možností zpráv](../debugger/message-options-dialog-box.md), zvolte **zprávy protokolu** z **Spy** nabídky.  
  
 Obvykle nejprve vybrat **skupiny zpráv**a poté doladit tak, že vyberete jednotlivé výběr **zprávy do zobrazení**. **Všechny** tlačítko vybere všechny typy zpráv a **žádný** tlačítko zruší výběr všech typů.  
  
 Následující nastavení jsou k dispozici na **zprávy** kartu:  
  
 **Zprávy do zobrazení**  
 Vyberte konkrétní zprávy pro zobrazení. Při vytváření nové okno zprávy může zobrazit všechny zprávy. Při filtrování zpráv **zprávy** kartu, tento filtr platí jenom pro nové zprávy, ne zprávy, které již byly zobrazeny v zobrazení Windows.  
  
 **Skupiny zpráv**  
 Vyberte skupiny zprávy pro zobrazení. Dostupné skupiny patří:  
  
-   WM_USER: s kódem větší než nebo rovna hodnotě WM_USER  
  
-   Registrovaný: zaregistrované **RegisterWindowMessage** volání  
  
-   Neznámé: neznámé zprávy v rozsahu 0 až (WM_USER – 1)  
  
 Všimněte si, že tyto **skupiny zpráv** nelze namapovat na konkrétní položky v rámci **zobrazení zpráv**. Když vyberete skupinu, je výběr použitých přímo na datové proudy zpráv.  
  
 Šedým zaškrtávací políčko v rámci **skupiny zpráv** znamená, že **zobrazení zpráv** se změnila pole se seznamem pro zprávy v dané skupině; jsou vybrány všechny typy zpráv v této skupině.  
  
 **Uložit nastavení jako výchozí**  
 Uložte aktuální nastavení pro pozdější použití jako možnosti hledání zpráv. Tato nastavení jsou také uloženy při ukončení nástroje Spy ++.



