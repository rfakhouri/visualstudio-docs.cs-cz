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
ms.workload: multiple
ms.openlocfilehash: 0841e622b0fe7c0d01d374da21a12a151c59021d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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