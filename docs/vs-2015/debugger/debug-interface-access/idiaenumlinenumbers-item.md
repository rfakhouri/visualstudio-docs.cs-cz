---
title: Idiaenumlinenumbers::Item – | Dokumentace Microsoftu
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
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a74fac7ae3a75d88b70360d36dafe5c4d85cb72
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633141"
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaenumlinenumbers::Item –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumlinenumbers-item).  
  
Získá číslo řádku pomocí indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Item (   
   DWORD            index,  
   IDiaLineNumber** lineNumber  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [in] Index o [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objekt, který se má načíst. Index je v rozsahu 0 až `count`-1, kde `count` je vrácený [idiaenumlinenumbers::get_count –](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md) metody.  
  
 Číslo řádku  
 [out] Vrátí [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objekt reprezentující počet požadovaných řádků.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)



