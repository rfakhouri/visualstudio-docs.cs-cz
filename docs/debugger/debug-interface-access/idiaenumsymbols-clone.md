---
title: Idiaenumsymbols::clone – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Clone method
ms.assetid: 5c542025-98cf-4307-901f-b9430f780cf0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6580676d5bd9f3bb406a124f09a32572727e2cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumsymbolsclone"></a>IDiaEnumSymbols::Clone
Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Clone (   
   IDiaEnumSymbols** ppenum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 ppenum  
 [out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) objekt, který obsahuje duplicitní enumerátor. Symboly se neduplikují, pouze enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)