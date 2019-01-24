---
title: Kódy zpráv | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- message codes
ms.assetid: 9f91f4e2-c1f1-4349-9f11-2fbbf59654be
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 92cc911b0217a406302553b3d913c032fc915b4c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54799431"
---
# <a name="message-codes"></a>Kódy zpráv
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Každý řádek zprávy zobrazeny v [zobrazení zpráv](../debugger/messages-view.md) obsahuje "P", je, "společnosti," nebo "R" kód. Tyto kódy mají následující význam:  
  
|Kód|Význam|  
|----------|-------------|  
|P|Publikování zprávy do fronty s **zpravy** funkce. Nejsou dostupné, ultimate dispozice zprávy týkající se žádné informace.|  
|S|Zpráva byla odeslána s **SendMessage** funkce. To znamená, že odesílatel není znovu získat kontrolu dokud příjemce zpracovává a odpovídá na zprávu. Příjemce, proto projdou návratovou hodnotu zpět do odesílatele.|  
|s|Zpráva byla odeslána, ale zabezpečení brání v přístupu k návratovou hodnotu.|  
|R|Pro každý "řádek obsahuje odpovídající řádek"R"(návrat), který obsahuje seznam zpráv návratovou hodnotu. Někdy jsou vnořené zpráva volání, což znamená, že tato obslužná rutina zpráv pošle jinou zprávu.|
