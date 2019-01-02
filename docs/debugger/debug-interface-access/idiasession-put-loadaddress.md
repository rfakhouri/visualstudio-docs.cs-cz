---
title: Idiasession::put_loadaddress – | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: de23c511f238578de2492992556b557c051841db
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53956985"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
Nastaví adresu zatížení pro spustitelný soubor, který odpovídá na symboly v tomto úložišti symbolů.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `NewVal`  
 [in] Načtení adresy pro spustitelný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Vlastnosti virtuální adresy (VA) symbol jsou vypočítány pomocí hodnoty této metody. Virtuální adresy nejsou vypočítat, pokud je tato vlastnost nastavená na nenulovou.  
  
> [!NOTE]
>  Tato metoda musí volat, když dostanete [idiasession –](../../debugger/debug-interface-access/idiasession.md) objektu a před zahájením používání objektu, pokud je třeba použít všechny virtuální vlastnosti na symboly.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)