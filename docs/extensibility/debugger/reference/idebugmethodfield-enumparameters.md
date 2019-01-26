---
title: IDebugMethodField::EnumParameters | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6eb2272aff9f02e4de85c5420bd687b059c0e839
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55035438"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
Vytvoří čítač pro parametry metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppParams`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam parametrů metody; v opačném případě vrátí hodnotu null, pokud neexistují žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné parametry. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek je [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu, který představuje různé typy parametrů. Volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metoda na každém objektu k určení přesně jaký druh parametr objekt představuje.  
  
 Parametr zahrnuje jeho název proměnné a jeho typu. První parametr metody třídy je obvykle ukazatel "Tento".  
  
 Pokud pouze typy parametrů je potřeba, zavolejte [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)