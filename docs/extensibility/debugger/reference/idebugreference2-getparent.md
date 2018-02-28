---
title: IDebugReference2::GetParent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugReference2::GetParent
helpviewer_keywords:
- IDebugReference2::GetParent
ms.assetid: e3061665-ad3e-4c1b-b33f-82755fa21be3
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0009ebb6cb8a86aebfb897d76197f90850e98037
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugreference2getparent"></a>IDebugReference2::GetParent
Získá odkaz na nadřazený odkaz. Vyhrazeno pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetParent (   
   IDebugReference2** ppParent  
);  
```  
  
```csharp  
int GetParent (   
   out IDebugReference2 ppParent  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppParent`  
 [out] Vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, který reprezentuje nadřazené této vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí hodnotu `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)