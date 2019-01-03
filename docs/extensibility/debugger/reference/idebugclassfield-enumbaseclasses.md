---
title: IDebugClassField::EnumBaseClasses | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3001dab0528a0a21ed11befe75b9d2ef4b314ed1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53986489"
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
Vytvoří čítač pro základní třídy této třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumBaseClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumBaseClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam základních tříd. Vrátí hodnotu null, pokud neexistují žádné základní třídy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK, vrátí hodnotu S_SH_NO_BASE_CLASSES Pokud neexistují žádné základní třídy (a `ppEnum` parametr je nastaven na hodnotu null); v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Základní třídy v objekt enumerator jsou uvedeny v pořadí podle nejvíce okamžité (nejvíce odvozené) základní třídy nebo na vzdálený základní třídu. Mějme například třídy jazyka C++:  
  
```  
class Root { }  
class Level1 : Root { }  
class Level2 : Level1 { }  
class MyClass : Level2 { }  
```  
  
 Vrátí výčet základní třídy v pořadí `Level2`, `Level1`, `Root`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)