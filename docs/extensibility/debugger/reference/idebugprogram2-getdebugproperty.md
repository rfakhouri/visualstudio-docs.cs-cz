---
title: IDebugProgram2::GetDebugProperty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::GetDebugProperty
helpviewer_keywords:
- IDebugProgram2::GetDebugProperty
ms.assetid: d194224e-f0e6-46ab-85d4-9e2639e28946
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 359dd06c6105741ec2f7eec6428cbb2dc838f491
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951222"
---
# <a name="idebugprogram2getdebugproperty"></a>IDebugProgram2::GetDebugProperty
Získá vlastnosti programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDebugProperty(   
   IDebugProperty2** ppProperty  
);  
```  
  
```csharp  
int GetDebugProperty(   
   out IDebugProperty2 ppProperty  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppProperty`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje vlastnosti programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vlastnosti vrácený touto metodou jsou specifické pro program. Pokud program musí vracet víc než jednu vlastnost, pak bude [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt vrácený touto metodou je kontejner další vlastnosti a volání [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) metoda vrátí hodnotu seznam všech vlastností.  
  
 Program může vystavit libovolný počet a typ další vlastnosti, které mohou být vyjadřuje se pomocí `IDebugProperty2` rozhraní. Integrované vývojové prostředí se může zobrazit vlastnosti další program přes uživatelské rozhraní prohlížeče obecná vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)