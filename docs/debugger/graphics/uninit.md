---
title: UnInit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 285cfb5a68055612fc7d77022b8f9d1d61067ded
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="uninit"></a>UnInit
Dokončí soubor protokolu grafiky, zavře se a uvolní prostředky, které jste použili při aplikaci se aktivně zaznamenání grafických informací.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void UnInit();  
```  
  
## <a name="remarks"></a>Poznámky  
 `UnInit`je volána automaticky, když instance `VsgDbg` třída zničena. Pokud `VsgDbg` instance nebyla aktivně zaznamenání grafických informací, tato akce nemá vliv.  
  
 Po `UnInit` byla volána na instanci systému `VsgDbg` třídy, nové grafiky souboru protokolu lze vytvořit voláním `Init` a dokončené voláním `UnInit`. To můžete opakovat tolikrát, kolikrát chcete použít stejné `VsgDbg` instance vytvořit několik nezávislých grafiky soubory protokolu.  
  
## <a name="see-also"></a>Viz také  
 [Init –](init.md)