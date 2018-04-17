---
title: Idiaenumdebugstreams::Next – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams::Next method
ms.assetid: eb8eae5a-be27-45f4-a7bd-6e4ef0652385
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 191914f85ec2c2a8b08d2c2eee3ab4f0bc285e3f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumdebugstreamsnext"></a>IDiaEnumDebugStreams::Next
Načte zadaný počet datové proudy debug v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Next (   
   ULONG                     celt,   
   IDiaEnumDebugStreamData** rgelt,  
   ULONG*                    pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] **T**mu počet datových proudů ladění enumerátor mají být načteny.  
  
 rgelt  
 [out] Vrátí pole [idiaenumdebugstreamdata –](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) objekty, které představuje ladění datové proudy, dojde k načtení.  
  
 pceltFetched  
 [out] Vrátí počet datových proudů ladění vrátila.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné další datové proudy. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)