---
title: IDebugMethodField::EnumArguments | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: db52be9d345009f88981c56d9d329d31264421d1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49270722"
---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vytvoří čítač pro typ každého argumentu potřebné k volání metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam typů argumentů. Vrátí hodnotu null, pokud nejsou žádné argumenty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že nejsou žádné argumenty. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek je [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt představující typy jednotlivé parametry. Volání [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) metodu pro načtení informací o typu každého parametru.  
  
 Pokud název parametru je potřeba spolu s typem, zavolejte [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)

