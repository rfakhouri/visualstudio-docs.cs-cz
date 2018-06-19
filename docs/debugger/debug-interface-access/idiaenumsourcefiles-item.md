---
title: Idiaenumsourcefiles::Item – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Item method
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1fda746edf51771e7927efd03094f42903141e6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31458340"
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
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)