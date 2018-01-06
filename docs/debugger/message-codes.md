---
title: "Kódy zpráv | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 432012d897ecc4da508dd2925ac655b8dc9d1416
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="message-codes"></a>Kódy zpráv
Každý řádek zprávy uvedené v [zobrazení zpráv](../debugger/messages-view.md) obsahuje "P", je, "na,' nebo 'R' kódu. Tyto kódy mají následující významy:  
  
|Kód|Význam|  
|----------|-------------|  
|P|Zpráva byla odeslána do fronty s **zpravy** funkce. Nejsou dostupné, ultimate dispozice zprávy týkající se žádné informace.|  
|S|Zpráva byla odeslána s **SendMessage** funkce. To znamená, že odesílatel nemá znovu získat kontrolu dokud příjemce zpracuje a vrátí zprávu. Příjemce může, tedy předat návratovou hodnotu zpět odesílatele.|  
|s|Zpráva byla odeslána, ale zabezpečení brání přístupu k návratovou hodnotu.|  
|R|Pro každý ' řádek obsahuje odpovídající řádek "R" (vrátit), který uvádí zprávy návratovou hodnotu. V některých případech jsou vnořeny volání zpráva, což znamená, že tuto obslužnou rutinu jednu zprávu odešle další zprávu.|