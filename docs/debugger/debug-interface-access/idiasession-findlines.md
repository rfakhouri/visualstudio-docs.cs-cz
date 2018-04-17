---
title: Idiasession::findlines – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLines method
ms.assetid: d6e84916-fd55-457e-b057-57f97b51fe73
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 49d3c690b81fbf9902ccdb2420c4f17c149dbfcd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindlines"></a>IDiaSession::findLines
Načte čísla řádků v rámci zadaného kompilace a identifikátory zdrojového souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findLines (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `compiland`  
 [v] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt reprezentující souboru pro kompilaci. Pomocí tohoto rozhraní jako kontext, ve kterém se má hledat čísla řádků.  
  
 `file`  
 [v] [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt reprezentující zdrojového souboru, do kterého chcete vyhledat čísla řádků.  
  
 `ppResult`  
 [out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) načíst objekt, který obsahuje seznam čísel řádků.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)