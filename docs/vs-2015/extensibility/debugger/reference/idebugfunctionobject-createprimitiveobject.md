---
title: IDebugFunctionObject::CreatePrimitiveObject | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreatePrimitiveObject
helpviewer_keywords:
- IDebugFunctionObject::CreatePrimitiveObject method
ms.assetid: 6e9dc8b6-b4e1-4abf-b6e0-e885910775bc
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3531483c113c37587b253bed90a9985541b2e526
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179453"
---
# <a name="idebugfunctionobjectcreateprimitiveobject"></a>IDebugFunctionObject::CreatePrimitiveObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vytvoří objekt primitivní datové, například jednoduché celočíselné.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CreatePrimitiveObject(   
   OBJECT_TYPE    ot,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreatePrimitiveObject(  
   enum_OBJECT_TYPE ot,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ot`  
 [in] Hodnota z [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md) představující typ primitivní k vytvoření výčtu.  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) představující nově vytvořený objekt.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volejte tuto metodu za účelem vytvoření objektu, který představuje základní objekt, který je parametr funkce, která je reprezentována [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní. Například pokud je řetězec výraz "myString(5)", tato metoda by použije k vytvoření objekt představující celé číslo 5.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
