---
title: IDebugClassField::EnumConstructors | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumConstructors
helpviewer_keywords:
- IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aa525f50a0ffd18f136cfa23ae05a8e2ba193d0d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101729"
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
Vytvoří enumerátor pro konstruktory pro tuto třídu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumConstructors(   
   CONSTRUCTOR_ENUM   cMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumConstructors(  
   CONSTRUCTOR_ENUM     cMatch,   
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cMatch`  
 [v] Hodnota z [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md) výčet, který určuje typ konstruktory výčtu.  
  
 `ppEnum`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objektu, který představuje seznam konstruktory. Vrátí hodnotu null, pokud nejsou žádné konstruktory.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE, pokud nejsou žádné konstruktory. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek výčtu je [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) objekt popisující metody konstruktoru.  
  
 Seznam konstruktory obvykle nezahrnuje poskytl kompilátor výchozí konstruktory.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)