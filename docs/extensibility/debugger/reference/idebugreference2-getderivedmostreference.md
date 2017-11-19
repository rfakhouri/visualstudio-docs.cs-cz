---
title: IDebugReference2::GetDerivedMostReference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugReference2::GetDerivedMostReference
helpviewer_keywords: IDebugReference2::GetDerivedMostReference
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 018f843e9e62430c780df1d3d15f06634a31908d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugreference2getderivedmostreference"></a>IDebugReference2::GetDerivedMostReference
Získá odkaz na odvozené většinu odkaz. Vyhrazeno pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDerivedMostReference(   
   IDebugReference2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostReference(   
   out IDebugReference2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppDerivedMost`  
 [out] Vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, který reprezentuje vlastnost odvozené nejvíc.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí hodnotu `E_NOTIMPL`.  
  
## <a name="remarks"></a>Poznámky  
 Například, pokud je tato vlastnost popisuje objekt, který implementuje `ClassRoot` , ale který je ve skutečnosti vytváření instancí z `ClassDerived` je odvozena z `ClassRoot`, pak tato metoda vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objektu představující odkaz na `ClassDerived` objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)