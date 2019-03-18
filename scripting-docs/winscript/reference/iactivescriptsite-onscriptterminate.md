---
title: IActiveScriptSite::OnScriptTerminate | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptTerminate
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptTerminate
ms.assetid: 3301ddf4-5929-404c-81d3-1a720e589008
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 664f974b26a2cae0d1e16d37dc3bc66e95993d6f
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58144820"
---
# <a name="iactivescriptsiteonscriptterminate"></a>IActiveScriptSite::OnScriptTerminate
Informuje o hostiteli, že skript byl dokončen.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnScriptTerminate(  
    VARIANT *pvarResult,   // address of script results  
    EXCEPINFO *pexcepinfo  // address of structure with exception information  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvarResult`  
 [in] Adresa proměnné, která obsahuje výsledek skriptu nebo `NULL` Pokud skript vytvořil žádný výsledek.  
  
 `pexcepinfo`  
 [in] Adresa `EXCEPINFO` strukturu, která obsahuje informace o výjimkách, které jsou generovány, pokud byl ukončen skript, nebo `NULL` Pokud byla vygenerována žádná výjimka.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření.  
  
## <a name="remarks"></a>Poznámky  
 Skriptovací stroj volá tuto metodu před voláním [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) dokončení metody s příznakem SCRIPTSTATE_INITIALIZED,. Tato metoda je možné vrátit stav dokončení a výsledky na hostitele. Všimněte si, že mnoho skriptovacích jazyků, které jsou založeny na zpracování událostí z hostitele, životnosti, které jsou definovány hostitelem. V takovém případě může nikdy volat tuto metodu.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)