---
title: Idiareadexeatrvacallback – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback interface
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75bdd6e2e8c5ee8144b68253fa691792a267a5d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677313"
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiareadexeatrvacallback –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiareadexeatrvacallback).  
  
Umožňuje klientské aplikaci slouží k poskytování bajtů spustitelný soubor určený relativní virtuální adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaReadExeAtRVACallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaReadExeAtRVACallback`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaReadExeAtRVACallback::ReadExecutableAtRVA](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|Přečte zadaný počet bajtů počínaje zadanou relativní virtuální adresu (RVA) ze spustitelného souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Klientská aplikace implementuje toto rozhraní negace bajtů se spustitelný soubor používající relativní virtuální adresu do souboru ke spustitelnému souboru. Chcete-li použít absolutní posun, implementovat [idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Tato metoda je implementované klientská aplikace a předat [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody jako alternativní metoda pro čtení souboru.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)



