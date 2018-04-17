---
title: ToggleHUD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8839e41048a68adf09380e6fa428087299a12801
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="togglehud"></a>ToggleHUD
Přepíná diagnostiky grafiky *HUD* (zobrazení Head-Up) překrytí zapnout nebo vypnout.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>Poznámky  
 HUD diagnostiky grafiky se zobrazí v levém horním rohu aplikace, která je spuštěná s pověřeními diagnostiky grafiky. Zobrazuje běhu informace o aplikaci a o grafiky informace o zachycení a zprávy, které jsou přidány voláním [AddMessage](addmessage.md) – členská funkce.  
  
 K přepnutí HUD, nemusíte být aktivně zaznamenání grafických informací – to znamená, můžou být změněny prostřednictvím instance `VsgDbg` třídy, ale [Init](init.md) – členská funkce nemá být volána nejprve.