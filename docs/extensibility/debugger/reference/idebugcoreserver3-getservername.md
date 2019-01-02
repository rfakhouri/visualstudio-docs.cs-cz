---
title: IDebugCoreServer3::GetServerName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::GetServerName
helpviewer_keywords:
- IDebugCoreServer3::GetServerName
ms.assetid: 0fc3fcf5-d6a3-4a00-bf14-458b8645714e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ea67af3c46e69373ab361b5e12cc8c7ad1a87f7f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53866761"
---
# <a name="idebugcoreserver3getservername"></a>IDebugCoreServer3::GetServerName
Načte název serveru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetServerName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetServerName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrName`  
 [out] Vrátí název serveru.  
  
> [!NOTE]
>  Volající zodpovídá za uvolnění řetězec.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Server popisný název, volání [GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)