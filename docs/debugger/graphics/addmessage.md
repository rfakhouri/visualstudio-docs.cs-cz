---
title: AddMessage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b0050f5022b31020879b45e45da48546e5a7caa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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