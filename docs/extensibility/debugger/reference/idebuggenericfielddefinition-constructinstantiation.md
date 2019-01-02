---
title: IDebugGenericFieldDefinition::ConstructInstantiation | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- ConstructInstantiation
- IDebugGenericFieldDefinition::ConstructInstantiation
ms.assetid: ef8ae261-a98b-4dc2-93b3-7c5191818ba2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6f72e251f66c196ec36eb68f5a228536658ab89d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53823940"
---
# <a name="idebuggenericfielddefinitionconstructinstantiation"></a>IDebugGenericFieldDefinition::ConstructInstantiation
Vytvoří instanci pole zadané pole argumentů typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT ConstructInstantiation(  
   ULONG32       cArgs,  
   IDebugField** ppArgs,  
   IDebugField** ppConstructedField  
);  
```  
  
```csharp  
int ConstructInstantiation(  
   uint            cArgs,  
   IDebugField[]   ppArgs,  
   out IDebugField ppConstructedField  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cArgs`  
 [in] Počet argumentů `ppArgs` pole.  
  
 `ppArgs`  
 [in] Pole, které obsahuje argumenty typu. Argumenty typu musí být uzavřený typy (obecné nebo zcela vytvořenou instanci obecné typy).  
  
 `ppConstructedField`  
 [out] Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, které představuje nové pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Omezení nekontrolují.  
  
## <a name="see-also"></a>Viz také  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)