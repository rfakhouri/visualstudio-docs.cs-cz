---
title: IDebugField::GetKind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugField::GetKind
helpviewer_keywords:
- IDebugField::GetKind method
ms.assetid: e7c9c60a-8e55-4ecc-aa63-0c814a1e92cc
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2ce0ad7a6e9e7523f8f46814335eaa85c1c092c2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfieldgetkind"></a>IDebugField::GetKind
Tato metoda získá druh typu pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetKind(   
   FIELD_KIND* pdwKind  
);  
```  
  
```csharp  
int GetKind(  
   out enum_FIELD_KIND pdwKind  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwKind`  
 [out] Vrátí typ pole jako kombinace [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) konstanty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)