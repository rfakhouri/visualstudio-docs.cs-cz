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
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58146354"
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
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_ABORT`|Operace byla přerušena při volání `IDebugSyncOperation::InProgressAbort` metody.|  
  
## <a name="remarks"></a>Poznámky  
 Správce ladění procesu v cílové vlákno vyvolá `Execute` metoda synchronně.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSyncOperation – rozhraní](../../winscript/reference/idebugsyncoperation-interface.md)