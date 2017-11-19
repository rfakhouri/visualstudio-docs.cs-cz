---
title: "Idiaenumsourcefiles::Item – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSourceFiles::Item method
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7cb8172b36542d215502636c96126cae064b3b93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsourcefilesitem"></a>IDiaEnumSourceFiles::Item
Načte zdrojového souboru pomocí indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaSourceFile** sourceFile  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 index  
 [v] Z indexu [idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt, který má být načtena. Index je v rozsahu od 0 do `count`-1, kde `count` je vrácený [idiaenumsourcefiles::get_count –](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md) metoda.  
  
 zdrojový soubor  
 [out] Vrátí [idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt reprezentující požadované zdrojový soubor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)