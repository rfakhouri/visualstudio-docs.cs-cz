---
title: IRemoteDebugApplication::QueryAlive | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.QueryAlive
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::QueryAlive
ms.assetid: 08e49d3b-6fb3-4438-960e-f05395ba9b17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: db17bd017b2fc1e1ca52ba8801eb1d197c4b3de7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62944198"
---
# <a name="iremotedebugapplicationqueryalive"></a>IRemoteDebugApplication::QueryAlive
Určuje, zda je interaktivní aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT QueryAlive();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda určuje, zda je interaktivní aplikace. Implementace této metody by měla vždy vrátit `S_OK`.  
  
 Pokud neočekávaně ukončí proces aplikace modelu COM vrátí chybu z sběrného systému proxy serveru pro volání této metody.  
  
## <a name="see-also"></a>Viz také  
 [IRemoteDebugApplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md)