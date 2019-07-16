---
title: UnInit | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0bec86a7f872057b7a0d652df6346e3a1ef2ff8a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68197937"
---
# <a name="uninit"></a>UnInit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Soubor protokolu grafiky dokončí, zavře a uvolní prostředky, které byly použity při aplikaci se aktivně zaznamenávání informací grafiky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
void UnInit();  
```  
  
## <a name="remarks"></a>Poznámky  
 `UnInit` je volána automaticky, když instance `VsgDbg` třídy je zničen. Pokud `VsgDbg` instance nebyla aktivně zaznamenávání informací grafiky, tato akce nemá vliv.  
  
 Po `UnInit` byla volána na instanci `VsgDbg` třídy nové grafické soubor protokolu může být vytvořen voláním `Init` a dokončí voláním `UnInit`. To můžete opakovat tolikrát, kolikrát chcete použít stejný `VsgDbg` instance vytvořit několik nezávislých grafiky soubory protokolu.  
  
## <a name="see-also"></a>Viz také  
 [Init](../debugger/init.md)
