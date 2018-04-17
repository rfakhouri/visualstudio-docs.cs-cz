---
title: UnInit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 735eb1948acfb03a6aa1a70fb27f012c41bb097d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="uninit"></a>UnInit
Dokončí soubor protokolu grafiky, zavře se a uvolní prostředky, které jste použili při aplikaci se aktivně zaznamenání grafických informací.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void UnInit();  
```  
  
## <a name="remarks"></a>Poznámky  
 `UnInit` je volána automaticky, když instance `VsgDbg` třída zničena. Pokud `VsgDbg` instance nebyla aktivně zaznamenání grafických informací, tato akce nemá vliv.  
  
 Po `UnInit` byla volána na instanci systému `VsgDbg` třídy, nové grafiky souboru protokolu lze vytvořit voláním `Init` a dokončené voláním `UnInit`. To můžete opakovat tolikrát, kolikrát chcete použít stejné `VsgDbg` instance vytvořit několik nezávislých grafiky soubory protokolu.  
  
## <a name="see-also"></a>Viz také  
 [Init](init.md)