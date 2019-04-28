---
title: IDebugAsyncOperation::Abort | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperation.Abort
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugAsyncOperation::Abort
ms.assetid: 232541c6-81b8-4eb7-96a7-a8e5fe087b31
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be696f852f7038316141415494920c43580738c9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62822096"
---
# <a name="idebugasyncoperationabort"></a>IDebugAsyncOperation::Abort
Slouží ke zrušení operace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Abort();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|S_OK|Metoda byla úspěšná.|  
|E_NOTIMPL|Operace nejde zrušit.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je obvykle volána z vlákna ladicího programu pro zrušení operace reagovat. Tato metoda způsobí, že `InProgressAbort` metodu `IDebugSyncOperation` objektu, která se má volat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAsyncOperation Interface](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugAsyncOperation::Start](../../winscript/reference/idebugasyncoperation-start.md)   
 [IDebugSyncOperation::InProgressAbort](../../winscript/reference/idebugsyncoperation-inprogressabort.md)