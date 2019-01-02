---
title: IDebugCustomAttributeQuery2::EnumCustomAttributes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
helpviewer_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
ms.assetid: 94bfce74-aa3d-45f0-8e04-5715faf85217
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 25dec8aa273d9b5fa89ce557d95cac181f2fe6de
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53929843"
---
# <a name="idebugcustomattributequery2enumcustomattributes"></a>IDebugCustomAttributeQuery2::EnumCustomAttributes
Získá enumerátor pro všechny vlastní atributy připojené k tomuto poli.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumCustomAttributes(   
   IEnumDebugCustomAttributes** ppEnum  
);  
```  
  
```csharp  
int EnumCustomAttributes(  
   out IEnumDebugCustomAttributes ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) objekt představující seznam vlastních atributů; jinak vrátí hodnotu null, pokud neexistují žádné vlastní atributy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu, vrátí hodnotu S_OK nebo S_FALSE, pokud nejsou žádné vlastní atributy v tomto poli. V opačném případě vrátí kód chyby;  
  
## <a name="remarks"></a>Poznámky  
 Pole může mít několik vlastních atributů.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)