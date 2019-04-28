---
title: IActiveScriptGarbageCollector::CollectGarbage | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: db8683534e449b2cdd8fcdb344c245d93da8fafc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62954964"
---
# <a name="iactivescriptgarbagecollectorcollectgarbage"></a>IActiveScriptGarbageCollector::CollectGarbage
Hostitel aktivních skriptů volá tuto metodu za účelem spustit uvolňování paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CollectGarbage(        SCRIPTGCTYPE scriptgctype    );  
```  
  
#### <a name="parameters"></a>Parametry  
 `scriptgctype`  
 [in] [Scriptgctype – výčet](../../winscript/reference/scriptgctype-enumeration.md) , který určuje, jestli se má provést normální nebo úplné uvolňování paměti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu HRESULT.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptGarbageCollector – rozhraní](../../winscript/reference/iactivescriptgarbagecollector-interface.md)