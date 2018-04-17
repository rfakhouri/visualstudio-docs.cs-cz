---
title: Idiasession::put_loadaddress – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fa8f7c12e07f68d8c3fdd85f0d33d964847abf22
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
Nastaví adresu zatížení pro spustitelný soubor, který odpovídá na symboly v tomto úložišti symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `NewVal`  
 [v] Načtěte adresu pro spustitelný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Symbol vlastnosti virtuální adresy (VA) se vypočítávají pomocí hodnoty této metody. Virtuální adresy nejsou vypočítat, pokud je tato vlastnost nastavena na nenulovou hodnotou.  
  
> [!NOTE]
>  Tato metoda musí volat, když získáte [idiasession –](../../debugger/debug-interface-access/idiasession.md) objektu a před zahájením práce objektu, pokud budete muset použít všechny virtuální vlastnosti na symboly.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)