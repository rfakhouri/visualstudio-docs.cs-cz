---
title: IActiveScriptSite::OnScriptTerminate | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: f8ff7c3d531b46fa6681776e79fbb73f6d1efca2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087110"
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