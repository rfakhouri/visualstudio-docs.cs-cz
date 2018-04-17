---
title: IDebugMethodField::EnumParameters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 112b91c2155c28b37b2222a99a45893fcb56e98c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
Vytvoří enumerátor pro parametry metody.  
  
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
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt reprezentující seznam parametrů metody; jinak vrátí hodnotu null, pokud neexistují žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE, pokud neexistují žádné parametry. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek je [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu, který představuje různé typy parametrů. Volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metoda na každém objektu k určení přesně jaký druh parametr objekt představuje.  
  
 Parametr zahrnuje její název proměnné a její typ. První parametr metody třídy je obvykle ukazatel "this".  
  
 Pokud jenom typy parametrů není nutná, volání [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)