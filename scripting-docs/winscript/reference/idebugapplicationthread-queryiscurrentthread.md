---
title: IDebugApplicationThread::QueryIsCurrentThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplicationThread.QueryIsCurrentThread
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplicationThread::QueryIsCurrentThread
ms.assetid: 1580d3aa-3be8-4779-ac7b-41ab5c9edede
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6bbcccc6f3f87ced3b9a5af8fc5febeab020aea0
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086460"
---
# <a name="idebugapplicationthreadqueryiscurrentthread"></a>IDebugApplicationThread::QueryIsCurrentThread
Určuje, zda toto vlákno je aktuálně běžícímu vláknu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT QueryIsCurrentThread();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná, a to je aktuálně spuštěné vlákno.|  
|`S_FALSE`|Toto není aktuálně běžícímu vláknu.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda určuje, zda toto vlákno je aktuálně běžícímu vláknu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplicationThread – rozhraní](../../winscript/reference/idebugapplicationthread-interface.md)