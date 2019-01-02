---
title: UnInit | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1cb7898042ef7f6974d2ac43ca8630232edddfc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53884925"
---
# <a name="uninit"></a>UnInit
Soubor protokolu grafiky dokončí, zavře a uvolní prostředky, které byly použity při aplikaci se aktivně zaznamenávání informací grafiky.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void UnInit();  
```  
  
## <a name="remarks"></a>Poznámky  
 `UnInit` je volána automaticky, když instance `VsgDbg` třídy je zničen. Pokud `VsgDbg` instance nebyla aktivně zaznamenávání informací grafiky, tato akce nemá vliv.  
  
 Po `UnInit` byla volána na instanci `VsgDbg` třídy nové grafické soubor protokolu může být vytvořen voláním `Init` a dokončí voláním `UnInit`. To můžete opakovat tolikrát, kolikrát chcete použít stejný `VsgDbg` instance vytvořit několik nezávislých grafiky soubory protokolu.  
  
## <a name="see-also"></a>Viz také  
 [Init](init.md)