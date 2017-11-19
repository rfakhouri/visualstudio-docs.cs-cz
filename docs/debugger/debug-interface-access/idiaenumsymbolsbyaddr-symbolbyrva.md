---
title: "Idiaenumsymbolsbyaddr::symbolbyrva – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSymbolsByAddr::symbolByRVA method
ms.assetid: f7828029-f2ee-4ccd-afac-785adc60a4c8
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65671bee476e772d046c5a22e398ffdda0e600fd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsymbolsbyaddrsymbolbyrva"></a>IDiaEnumSymbolsByAddr::symbolByRVA
Umisťuje enumerátor provedením vyhledávání podle relativní virtuální adresy (RVA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT symbolByRVA (   
   DWORD**      relativeVirtualAddress,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 relativeVirtualAddress  
 [v] Adres relativní spuštění bitové kopie.  
  
 ppsymbol  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objektu, který představuje symbol nalezen.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud je symbol nebyl nalezen. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsymbolsbyaddr –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [Idiaenumsymbolsbyaddr::symbolbyva –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)