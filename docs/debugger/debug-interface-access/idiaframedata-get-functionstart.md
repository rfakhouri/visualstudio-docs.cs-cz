---
title: "Idiaframedata::get_functionstart – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::get_functionStart method
ms.assetid: 49fd24fb-65c2-4812-8303-56a968353e1b
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c7cd995a695f809737c0dbc4adfab0e76e2c8266
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaframedatagetfunctionstart"></a>IDiaFrameData::get_functionStart
Načte příznak, který určuje, zda blok obsahuje vstupní bod funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_functionStart (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` pokud blok obsahuje vstupní bod; v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Je možné pro rámce zásobníku není za spuštění funkce, protože rámečku představuje vložené metody nebo funkce, které jsou vloženy do funkce.  
  
## <a name="see-also"></a>Viz také  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)