---
title: AddMessage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41a71a69c916bf2fff30b2dee8784d5d9997436b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56705567"
---
# <a name="addmessage"></a>AddMessage
Přidá vlastní zprávu pro diagnostiku grafiky *HUD* (zobrazení vedoucí nahoru).

## <a name="syntax"></a>Syntaxe

```C++
void AddMessage(
  wchar_t const * szMessage
);
```

#### <a name="parameters"></a>Parametry
 `szMessage` Zpráva, která mají být přidány do HUD.

## <a name="remarks"></a>Poznámky
 HUD Diagnostika grafiky se zobrazí v levém horním rohu aplikace, na kterém běží v rámci diagnostiky grafiky. Zobrazuje běhové informace o aplikaci a o zachycení informací grafiky a zprávy, které jsou přidány pomocí volání této funkce.

 K přidání zprávy do HUD, nemusíte být aktivně zachycení informací grafiky – to znamená, je možné přidat zprávu prostřednictvím instance `VsgDbg` třídy, ale [Init](init.md) členská funkce nevytváří nejprve volat. Zprávy se zobrazují jenom v HUD, se zaznamenávají do souboru protokolu grafiky.