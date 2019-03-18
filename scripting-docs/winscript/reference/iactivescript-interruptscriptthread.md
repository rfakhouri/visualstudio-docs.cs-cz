---
title: IActiveScript::InterruptScriptThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.InterruptScriptThread
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_InterruptScriptThread
ms.assetid: 2304d035-6d39-4811-acd3-8a9640fdbef6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa46bc95087b3defaf739cc3473c58e29a93071c
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58155927"
---
# <a name="iactivescriptinterruptscriptthread"></a>IActiveScript::InterruptScriptThread
Přeruší provádění spuštěné vlákno skriptu (jímky událostí, okamžité spuštění nebo volání makra). Tato metoda slouží k ukončení skript, který se zasekne (například v nekonečné smyčce). Může být volána z vláken znaky bez výsledkem znaky popisek hostitele objektů nebo [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT InterruptScriptThread(  
    SCRIPTTHREADID   stidThread,  // identifier of thread  
    const EXCEPINFO *pexcepinfo,  // receives error information  
    DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stidThread`  
 [in] Identifikátor vlákna k přerušení nebo jednu z následujících hodnot identifikátoru speciální vlákna:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|SCRIPTTHREADID_ALL|Všechna vlákna. Přerušení platí pro všechny metody skriptů právě probíhá. Všimněte si, že pokud volající vyžaduje skript odpojeny, další skriptované událost způsobí, že kód skriptu znovu spustit pomocí volání [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) metodou SCRIPTSTATE_DISCONNECTED nebo SCRIPTSTATE_INITIALIZED příznak nastaven.|  
|SCRIPTTHREADID_BASE|Základní podprocesu. To znamená, že byla vytvořena instance vláken, ve kterém skriptovací stroje.|  
|SCRIPTTHREADID_CURRENT|Aktuálně spuštěné vlákno.|  
  
 `pexcepinfo`  
 [in] Adresa `EXCEPINFO` struktura obsahující informace o chybě, která by se měly hlásit přerušené skriptu.  
  
 `dwFlags`  
 [in] Možnost příznaky, které jsou přidružené k přerušení. Může být jedna z těchto hodnot:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|SCRIPTINTERRUPT_DEBUG|Pokud se podporuje, zadejte skriptovací stroj ladicímu programu na aktuální bod provádění skriptu.|  
|SCRIPTINTERRUPT_RAISEEXCEPTION|Pokud podporovaná skriptovacího jazyka, dejte skript zpracování výjimky. V opačném případě metoda skript byl přerušen a vrácený kód chyby volajícímu; To znamená události zdroje nebo makro původce.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován).|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)