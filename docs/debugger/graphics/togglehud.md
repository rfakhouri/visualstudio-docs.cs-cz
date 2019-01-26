---
title: ToggleHUD | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e49066d4625990119159ea72f59a3a3fe59d581c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54953299"
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