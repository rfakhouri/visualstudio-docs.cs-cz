---
title: IDebugClassField::EnumBaseClasses | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 69c300abde0cd540e34ce351573948d3546e2b3d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678730"
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugClassField::EnumBaseClasses](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugclassfield-enumbaseclasses).  
  
Vytvoří čítač pro základní třídy této třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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

