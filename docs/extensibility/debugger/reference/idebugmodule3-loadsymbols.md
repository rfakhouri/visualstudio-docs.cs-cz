---
title: IDebugModule3::LoadSymbols | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugModule3::LoadSymbols
helpviewer_keywords: IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1b3dda16ac3312e7deec21b06a4df05162bfa692
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 Pokud metoda bude úspěšná, vrátí `S_OK`. Pokud se nezdaří, vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda načte symboly z aktuální cesty pro hledání (který může být změněna pomocí volání [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) metoda).  
  
 Tato metoda je upřednostňovaný přes [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)