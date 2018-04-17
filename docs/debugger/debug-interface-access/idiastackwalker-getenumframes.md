---
title: IDiaStackWalker::getEnumFrames | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames method
ms.assetid: f9f09729-4c34-441c-989c-e0b7339ee32c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b57ff6f306cd8725264176d0dd26b7304daf6315
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkergetenumframes"></a>IDiaStackWalker::getEnumFrames
Načte enumerátor rámce zásobníku pro x86 platformy.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT getEnumFrames(   
   IDiaStackWalkHelper*   pHelper,  
   IDiaEnumStackFrames**  ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pHelper`  
 [v] Pomocné rutiny [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) objektu.  
  
 `ppEnum`  
 [out] Vrátí [idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md) objekt, který obsahuje seznam [idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md) objekty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li získat seznam rámce zásobníku na jiné platformě, zavolejte [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiastackwalker –](../../debugger/debug-interface-access/idiastackwalker.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [Idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)