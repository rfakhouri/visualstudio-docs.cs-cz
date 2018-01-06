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
ms.workload: multiple
ms.openlocfilehash: 9440eeda69592fad2e7c8f4e3e936f4b3dff29b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 [Init](init.md)