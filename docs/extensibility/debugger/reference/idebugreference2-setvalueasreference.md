---
title: IDebugReference2::SetValueAsReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugReference2::SetValueAsReference
helpviewer_keywords:
- IDebugReference2::SetValueAsReference
ms.assetid: 94a545d2-16b9-45e9-b2e7-4e49ff90aad0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d24cd6658fd4c971e2592a8b05b1593a1090784
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53922769"
---
# <a name="idebugreference2setvalueasreference"></a>IDebugReference2::SetValueAsReference
Nastaví hodnotu odkazu z jiného odkazu. Vyhrazeno pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetValueAsReference (   
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```cpp  
int SetValueAsReference (   
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `rgpArgs`  
 [in] Pole [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekty sloužící k určení, jak nastavit hodnotu odkazu.  
  
 `dwArgCount`  
 [in] Počet odkazů v poli.  
  
 `pValue`  
 [in] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, ze kterého chcete nastavit hodnotu vlastnosti.  
  
 `dwTimeout`  
 [in] Maximální doba v milisekundách pro čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)