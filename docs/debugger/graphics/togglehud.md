---
title: ToggleHUD | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4ee371f90636d98d5dd771cc508e58cd1d1a394
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53907972"
---
# <a name="togglehud"></a>ToggleHUD
Přepíná diagnostiky grafiky *HUD* překrytí (zobrazit vedoucí nahoru), nebo vypnout.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>Poznámky  
 HUD Diagnostika grafiky se zobrazí v levém horním rohu aplikace, na kterém běží v rámci diagnostiky grafiky. Zobrazí běhových informací o aplikaci a o zachycení informací grafiky a zprávy, které jsou přidány pomocí volání [AddMessage](addmessage.md) členskou funkci.  
  
 Chcete-li přepnout HUD, nemusíte být aktivně zachycení informací grafiky – to znamená, ho můžou být prostřednictvím instance `VsgDbg` třídy, ale [Init](init.md) nemusí být nejprve volat členské funkce.