---
title: IDebugModule3::LoadSymbols | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugModule3::LoadSymbols
helpviewer_keywords:
- IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b84615f4dd4f27e5c8512c985ac234a17506b0b5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956865"
---
# <a name="idebugmodule3loadsymbols"></a>IDebugModule3::LoadSymbols
Načte symboly pro aktuální modul.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT LoadSymbols(  
   void  
);  
```  
  
```csharp  
int LoadSymbols();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud metoda uspěje, vrátí `S_OK`. Pokud selže, vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda načte symboly z aktuální cesta pro vyhledávání (které mohou být změněny voláním [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) metoda).  
  
 Tato metoda je upřednostňované nad [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)