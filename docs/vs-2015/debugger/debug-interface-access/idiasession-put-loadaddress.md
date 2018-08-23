---
title: Idiasession::put_loadaddress – | Dokumentace Microsoftu
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
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e39ac68468113f371c032f2f29b4613fa229a3b7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666295"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasession::put_loadaddress –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-put-loadaddress).  
  
Nastaví adresu zatížení pro spustitelný soubor, který odpovídá na symboly v tomto úložišti symbolů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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



