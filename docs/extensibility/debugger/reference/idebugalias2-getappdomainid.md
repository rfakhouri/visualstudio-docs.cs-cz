---
title: IDebugAlias2::GetAppDomainId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetAppDomainId
- IDebugAlias2::GetAppDomainId
ms.assetid: 23581aaa-5a53-4859-b264-eca49fc44bcd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 03d0ebeeddfd212b4ad99b8f1686c4f9d64141d3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900254"
---
# <a name="idebugalias2getappdomainid"></a>IDebugAlias2::GetAppDomainId
Načte identifikátor pro doménu aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetAppDomainId (  
   ULONG32* pappDomainId  
);  
```  
  
```csharp  
int GetAppDomainId (  
   out uint pappDomainId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pappDomainId`  
 [out] Vrátí identifikátor domény aplikace.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokaždé, když se aplikace restartuje změny identifikátor domény aplikace a novou doménu aplikace se vytvoří.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAlias2](../../../extensibility/debugger/reference/idebugalias2.md)