---
title: IDebugMethodField::EnumArguments | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 515897838b2061a04479a69f5118f69a72e89f86
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
Vytvoří enumerátor pro typ všechny argumenty pro volání metody požadován.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumArguments(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumArguments(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppParams`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objektu, který představuje seznam typy argumentů. Vrátí hodnotu null, pokud žádné argumenty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE, pokud žádné argumenty. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek je [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt reprezentující typy jednotlivé parametry. Volání [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) metodu za účelem načtení informací o typu jednotlivé parametry.  
  
 Pokud název parametru není nutná spolu s typem, zavolejte [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)