---
title: IDebugReference2::SetValueAsReference | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 0ce62358df758b7f4cf3ef0883cf0ac457aaf1f5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugreference2setvalueasreference"></a>IDebugReference2::SetValueAsReference
Nastaví hodnotu odkaz z jiného odkazu. Vyhrazeno pro budoucí použití.  
  
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
 [v] Pole [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekty, které umožňuje určit, jak nastavit hodnota odkazu.  
  
 `dwArgCount`  
 [v] Počet odkazů v poli.  
  
 `pValue`  
 [v] [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, ze kterého chcete-li nastavit hodnotu vlastnosti.  
  
 `dwTimeout`  
 [v] Maximální doba v milisekundách pro čekání před návratem od této metody. Použití `INFINITE` čekání po neomezenou dobu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí hodnotu `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)