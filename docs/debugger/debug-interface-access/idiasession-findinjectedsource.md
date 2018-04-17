---
title: Idiasession::findinjectedsource – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af1eba03b231bf894084090a191432c64bedc861
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindinjectedsource"></a>IDiaSession::findInjectedSource
Načte seznam zdrojů, který se nachází do úložiště symbolů atribut zprostředkovatelé ani jiné součásti procesu kompilace.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInjectedSource (   
   LPCOLESTR                 srcFile,  
   IDiaEnumInjectedSources** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 srcFile  
 [v] Název zdrojového souboru, pro které chcete vyhledat.  
  
 ppResult  
 [out] Vrátí [idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md) objekt, který obsahuje seznam všech vloženého zdroje.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)