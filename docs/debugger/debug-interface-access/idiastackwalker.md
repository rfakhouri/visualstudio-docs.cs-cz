---
title: "Idiastackwalker – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalker interface
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e651c8ba8bee152121b96b14613144768a56cc2f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalker"></a>IDiaStackWalker
Poskytuje možnosti metod protokolů provede pomocí informací v souboru pdb.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaStackWalker: IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaStackWalker`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|Načte enumerátor rámce zásobníku pro x86 platformy.|  
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|Načte enumerátor rámce zásobníku pro konkrétní platformu typu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní se používá k získání seznamu rámce zásobníku pro načíst modul. Každou z metod je předána [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) objektu (implementované klientské aplikace), která poskytuje informace potřebné k vytvoření seznamu rámce zásobníku.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní se získá voláním `CoCreateInstance` metoda s identifikátorem třídy `CLSID_DiaStackWalker` a ID rozhraní `IID_IDiaStackWalker`. Příklad ukazuje, jak získat toto rozhraní.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat `IDiaStackWalker` rozhraní.  
  
```C++  
  
      IDiaStackWalker* pStackWalker;  
HRESULT hr = CoCreateInstance(CLSID_DiaStackWalker,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaStackWalker,  
                              (void**) &pStackWalker);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)