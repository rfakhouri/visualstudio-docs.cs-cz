---
title: Kódy zpráv | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c3899da3b668406a701ce5c1c4935b531754d10e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017080"
---
# <a name="message-codes"></a>Kódy zpráv
Každý řádek zprávy zobrazeny v [zobrazení zpráv](../debugger/messages-view.md) obsahuje "P", je, "společnosti," nebo "R" kód. Tyto kódy mají následující význam:  
  
|Kód|Význam|  
|----------|-------------|  
|P|Publikování zprávy do fronty s **zpravy** funkce. Nejsou dostupné, ultimate dispozice zprávy týkající se žádné informace.|  
|S|Zpráva byla odeslána s **SendMessage** funkce. To znamená, že odesílatel není znovu získat kontrolu dokud příjemce zpracovává a odpovídá na zprávu. Příjemce, proto projdou návratovou hodnotu zpět do odesílatele.|  
|s|Zpráva byla odeslána, ale zabezpečení brání v přístupu k návratovou hodnotu.|  
|R|Pro každý "řádek obsahuje odpovídající řádek"R"(návrat), který obsahuje seznam zpráv návratovou hodnotu. Někdy jsou vnořené zpráva volání, což znamená, že tato obslužná rutina zpráv pošle jinou zprávu.|