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
ms.openlocfilehash: 7a1e724c5c328c86398c43263b19980b5f464a39
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="message-codes"></a>Kódy zpráv
Každý řádek zprávy uvedené v [zobrazení zpráv](../debugger/messages-view.md) obsahuje "P", je, "na,' nebo 'R' kódu. Tyto kódy mají následující významy:  
  
|Kód|Význam|  
|----------|-------------|  
|P|Zpráva byla odeslána do fronty s **zpravy** funkce. Nejsou dostupné, ultimate dispozice zprávy týkající se žádné informace.|  
|S|Zpráva byla odeslána s **SendMessage** funkce. To znamená, že odesílatel nemá znovu získat kontrolu dokud příjemce zpracuje a vrátí zprávu. Příjemce může, tedy předat návratovou hodnotu zpět odesílatele.|  
|s|Zpráva byla odeslána, ale zabezpečení brání přístupu k návratovou hodnotu.|  
|R|Pro každý ' řádek obsahuje odpovídající řádek "R" (vrátit), který uvádí zprávy návratovou hodnotu. V některých případech jsou vnořeny volání zpráva, což znamená, že tuto obslužnou rutinu jednu zprávu odešle další zprávu.|