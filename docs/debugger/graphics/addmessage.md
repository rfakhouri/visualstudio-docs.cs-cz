---
title: AddMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f58f716aca83cce9f2e04129d45a9cf9c97df50
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="addmessage"></a>AddMessage
Přidá vlastní zprávu do diagnostiky grafiky *HUD* (zobrazení Head-Up).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szMessage`  
 Zpráva, která mají být přidány do HUD.  
  
## <a name="remarks"></a>Poznámky  
 HUD diagnostiky grafiky se zobrazí v levém horním rohu aplikace, která je spuštěná s pověřeními diagnostiky grafiky. Zobrazuje běhu informace o aplikaci a o grafiky informace o zachycení a zprávy, které jsou přidány voláním této funkce.  
  
 Pokud chcete přidat zprávu HUD, nemusíte být aktivně zaznamenání grafických informací – to znamená, lze přidat zprávu prostřednictvím instance `VsgDbg` třídy, ale [Init](init.md) – členská funkce neobsahuje jako první. Zprávy se zobrazují pouze v HUD, se zaznamenávají v souboru protokolu grafiky.