---
title: "Idiaframedata::get_systemexceptionhandling – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::get_systemExceptionHandling method
ms.assetid: e8df1972-913c-446c-9779-775575b0caa9
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea169502699ce8509f7913659d71e4573fef0a2f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaframedatagetsystemexceptionhandling"></a>IDiaFrameData::get_systemExceptionHandling
Načte příznak, který určuje, zda je systém zpracování výjimek v platnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_systemExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí `TRUE` Pokud systému výjimek je v platnosti; jinak vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zpracovávání výjimek v jazyce systému se běžně označuje jako strukturované zpracování výjimek.  
  
 Pokud chcete zjistit, pokud je v platnosti zpracovávání výjimek v jazyce C++, volání [idiaframedata::get_cplusplusexceptionhandling –](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)   
 [Idiaframedata::get_cplusplusexceptionhandling –](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md)