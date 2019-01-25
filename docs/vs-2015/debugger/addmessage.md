---
title: AddMessage | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f01d4e80c3740ae27b5df8badbc74989c2da2c60
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54757927"
---
# <a name="addmessage"></a>AddMessage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Přidá vlastní zprávu pro diagnostiku grafiky *HUD* (zobrazení vedoucí nahoru).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szMessage`  
 Zpráva, která mají být přidány do HUD.  
  
## <a name="remarks"></a>Poznámky  
 HUD Diagnostika grafiky se zobrazí v levém horním rohu aplikace, na kterém běží v rámci diagnostiky grafiky. Zobrazuje běhové informace o aplikaci a o zachycení informací grafiky a zprávy, které jsou přidány pomocí volání této funkce.  
  
 K přidání zprávy do HUD, nemusíte být aktivně zachycení informací grafiky – to znamená, je možné přidat zprávu prostřednictvím instance `VsgDbg` třídy, ale [Init](../debugger/init.md) členská funkce nevytváří nejprve volat. Zprávy se zobrazují jenom v HUD, se zaznamenávají do souboru protokolu grafiky.
