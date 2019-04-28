---
title: IDebugSyncOperation::Execute | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSyncOperation.Execute
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::Execute
ms.assetid: a45b8c7d-c51a-4098-877f-fbec2f1f6947
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2bc204169ff94a240e363eb8caa35ec8c7de9be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63004875"
---
# <a name="idebugsyncoperationexecute"></a>IDebugSyncOperation::Execute
Synchronní operace provede a vrátí.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Execute(  
   IUnknown**  ppunkResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppunkResult`  
 [out] Parametr objektu vrácená operací.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_ABORT`|Operace byla přerušena při volání `IDebugSyncOperation::InProgressAbort` metody.|  
  
## <a name="remarks"></a>Poznámky  
 Správce ladění procesu v cílové vlákno vyvolá `Execute` metoda synchronně.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSyncOperation – rozhraní](../../winscript/reference/idebugsyncoperation-interface.md)