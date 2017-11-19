---
title: "Idiasession::findinjectedsource – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dbac48aef894272d1edd9c4881c9f916255459b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)