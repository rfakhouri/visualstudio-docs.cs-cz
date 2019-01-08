---
title: IActiveScriptGarbageCollector::CollectGarbage | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 478a7a39c69e0c2106e3c6cc308f44f8f7aa3201
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097120"
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