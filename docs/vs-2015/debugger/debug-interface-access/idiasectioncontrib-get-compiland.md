---
title: Idiasectioncontrib::get_compiland – | Dokumentace Microsoftu
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
- IDiaSectionContrib::get_compiland method
ms.assetid: c0496f6f-f8f2-435f-8674-6c32db6c5934
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e76fea45f5f18e4ab7b93daa40ab73bec431ea88
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666426"
---
# <a name="idiasectioncontribgetcompiland"></a>IDiaSectionContrib::get_compiland
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasectioncontrib::get_compiland –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasectioncontrib-get-compiland).  
  
Získá odkaz na symbol kompilace, které přispěly v této části.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_compiland (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt představující kompilace, které přispěly v této části.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



