---
title: UnInit | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4cd66d7329fa4bfc288f3d60879e45cc86ded94e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675278"
---
# <a name="uninit"></a>UnInit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [UnInit](https://docs.microsoft.com/visualstudio/debugger/graphics/uninit).  
  
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



