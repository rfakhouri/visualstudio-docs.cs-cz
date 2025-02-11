---
title: Karta zprávy, dialogové okno možností zpráv | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a9eb1c88d935fa307e8b86a9a75da423bc08111c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68149432"
---
# <a name="messages-tab-message-options-dialog-box"></a>Karta Zprávy, dialogové okno možností zpráv
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Použití **zprávy** kartu, vyberte v seznamu typů zpráv, které [zobrazení zpráv](../debugger/messages-view.md)a určení kritérií hledání zpráv. Chcete-li zobrazit [dialogové okno možností zpráv](../debugger/message-options-dialog-box.md), zvolte **zprávy protokolu** z **Spy** nabídky.  
  
 Obvykle nejprve vybrat **skupiny zpráv**a poté doladit tak, že vyberete jednotlivé výběr **zprávy do zobrazení**. **Všechny** tlačítko vybere všechny typy zpráv a **žádný** tlačítko zruší výběr všech typů.  
  
 Následující nastavení jsou k dispozici na **zprávy** kartu:  
  
 **Zprávy do zobrazení**  
 Vyberte konkrétní zprávy pro zobrazení. Při vytváření nové okno zprávy může zobrazit všechny zprávy. Při filtrování zpráv **zprávy** kartu, tento filtr platí jenom pro nové zprávy, ne zprávy, které již byly zobrazeny v zobrazení Windows.  
  
 **Skupiny zpráv**  
 Vyberte skupiny zprávy pro zobrazení. Dostupné skupiny patří:  
  
- WM_USER: s kódem větší než nebo rovna hodnotě WM_USER  
  
- Registrovaný: zaregistrované **RegisterWindowMessage** volání  
  
- Neznámé: neznámé zprávy v rozsahu 0 až (WM_USER – 1)  
  
  Všimněte si, že tyto **skupiny zpráv** nelze namapovat na konkrétní položky v rámci **zobrazení zpráv**. Když vyberete skupinu, je výběr použitých přímo na datové proudy zpráv.  
  
  Šedým zaškrtávací políčko v rámci **skupiny zpráv** znamená, že **zobrazení zpráv** se změnila pole se seznamem pro zprávy v dané skupině; jsou vybrány všechny typy zpráv v této skupině.  
  
  **Uložit nastavení jako výchozí**  
  Uložte aktuální nastavení pro pozdější použití jako možnosti hledání zpráv. Tato nastavení jsou také uloženy při ukončení nástroje Spy ++.
