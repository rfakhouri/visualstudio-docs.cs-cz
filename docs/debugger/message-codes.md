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
ms.openlocfilehash: 1c09245056bf7e947985bfa55dc9cc4a3a96b8cf
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681189"
---
# <a name="message-codes"></a>Kódy zpráv
Každý řádek zprávy zobrazeny v [zobrazení zpráv](../debugger/messages-view.md) obsahuje "P", je, "společnosti," nebo "R" kód. Tyto kódy mají následující význam:

|Kód|Význam|
|----------|-------------|
|P|Publikování zprávy do fronty s **zpravy** funkce. Nejsou dostupné, ultimate dispozice zprávy týkající se žádné informace.|
|S|Zpráva byla odeslána s **SendMessage** funkce. To znamená, že odesílatel není znovu získat kontrolu dokud příjemce zpracovává a odpovídá na zprávu. Příjemce, proto projdou návratovou hodnotu zpět do odesílatele.|
|s|Zpráva byla odeslána, ale zabezpečení brání v přístupu k návratovou hodnotu.|
|R|Pro každý "řádek obsahuje odpovídající řádek"R"(návrat), který obsahuje seznam zpráv návratovou hodnotu. Někdy jsou vnořené zpráva volání, což znamená, že tato obslužná rutina zpráv pošle jinou zprávu.|