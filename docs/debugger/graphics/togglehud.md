---
title: ToggleHUD | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: baaa776a64d9b778c161ab7e65bb0f15e6c90099
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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