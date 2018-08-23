---
title: Kódy zpráv | Dokumentace Microsoftu
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
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d995a884b8d223a4415549739c9701fd72886a56
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628210"
---
# <a name="message-codes"></a>Kódy zpráv
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kódy zpráv](https://docs.microsoft.com/visualstudio/debugger/message-codes).  
  
Každý řádek zprávy zobrazeny v [zobrazení zpráv](../debugger/messages-view.md) obsahuje "P", je, "společnosti," nebo "R" kód. Tyto kódy mají následující význam:  
  
|Kód|Význam|  
|----------|-------------|  
|P|Publikování zprávy do fronty s **zpravy** funkce. Nejsou dostupné, ultimate dispozice zprávy týkající se žádné informace.|  
|S|Zpráva byla odeslána s **SendMessage** funkce. To znamená, že odesílatel není znovu získat kontrolu dokud příjemce zpracovává a odpovídá na zprávu. Příjemce, proto projdou návratovou hodnotu zpět do odesílatele.|  
|s|Zpráva byla odeslána, ale zabezpečení brání v přístupu k návratovou hodnotu.|  
|R|Pro každý "řádek obsahuje odpovídající řádek"R"(návrat), který obsahuje seznam zpráv návratovou hodnotu. Někdy jsou vnořené zpráva volání, což znamená, že tato obslužná rutina zpráv pošle jinou zprávu.|



