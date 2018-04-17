---
title: Idiaenumsymbolsbyaddr::clone – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbolsByAddr::Clone method
ms.assetid: f4582c69-bc3f-4a26-bcca-b641102b85fe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 87f2f42d75b8be3226d59bc23b10ccc90e0a14ed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumsymbolsbyaddrclone"></a>IDiaEnumSymbolsByAddr::Clone
Vytvoří kopii objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Clone (   
   IDiaEnumSymbolsByAddr** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppenum  
 [out] Vrátí [idiaenumsymbolsbyaddr –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md) objekt, který obsahuje duplicitní enumerátor. Symboly se neduplikují, pouze enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)