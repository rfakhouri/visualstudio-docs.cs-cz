---
title: IDebugClassField::EnumConstructors | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumConstructors
helpviewer_keywords:
- IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cd93f4867221f0b42f91fe1f96b8a8b464bf5aa9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68191034"
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vytvoří čítač pro konstruktory pro tuto třídu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Hodnota z [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md) výčet, který určuje typ pro výčet konstruktory.  
  
 `ppEnum`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam konstruktory. Vrátí hodnotu null, pokud neexistují žádné konstruktory.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné konstruktory. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek výčtu je [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) objekt popisující metodu konstruktoru.  
  
 Seznam konstruktory obvykle neobsahuje výchozí konstruktory poskytnutých kompilátoru.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)
