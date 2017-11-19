---
title: IDebugClassField::EnumBaseClasses | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugClassField::EnumBaseClasses
helpviewer_keywords: IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6c86f631d08fa3a3d7a43b1da2d6555370257c6b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
Vytvoří enumerátor pro základní třídy této třídy.  
  
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
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objektu, který představuje seznam základních tříd. Vrátí hodnotu null, pokud nejsou žádné základní třídy.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK, vrátí S_SH_NO_BASE_CLASSES, pokud nejsou žádné základní třídy (a `ppEnum` parametr je nastaven na hodnotu null), jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Třídy base v objekt enumerator jsou určené v pořadí nejvíce okamžitou (nebo nejodvozenějších) základní třída pro vzdálený základní třídy. Například zadané třídy C++:  
  
```  
class Root { }  
class Level1 : Root { }  
class Level2 : Level1 { }  
class MyClass : Level2 { }  
```  
  
 Výčtu by vrátit základní třídy v pořadí `Level2`, `Level1`, `Root`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)