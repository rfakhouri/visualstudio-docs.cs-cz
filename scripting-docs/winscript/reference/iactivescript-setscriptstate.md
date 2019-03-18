---
title: IActiveScript::SetScriptState | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.SetScriptState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_SetScriptState
ms.assetid: f2b2700c-0c8d-40db-ad84-dc751c5d9bc2
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 16a13b545ddd482f8aa143d289d46447370e23ac
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149507"
---
# <a name="iactivescriptsetscriptstate"></a>IActiveScript::SetScriptState
Vloží skriptovací stroj do daného stavu. Tuto metodu lze volat z vlákna znaky bez výsledkem znaky popisek hostitele objektů nebo [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetScriptState(  
    SCRIPTSTATE ss  // identifier of new state  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ss`  
 [in] Nastaví skriptovací stroj má daný stav. Může být jedna z hodnot fronty definovaných v [scriptstate – výčet](../../winscript/reference/scriptstate-enumeration.md) výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_FAIL`|Skriptovací modul nepodporuje přechod zpět do stavu spuštění. Hostitel musí zrušit tento skriptovací stroj a vytvořit, inicializovat a načtení nového skriptovacího stroje k dosažení stejného výsledku.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován) a proto se nezdařilo.|  
|`OLESCRIPT_S_PENDING`|Metoda byla úspěšně ve frontě, ale ještě nebyl změněn stav. Při změně stavu, lokalitu bude volána zpět prostřednictvím [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) metody.|  
|`S_FALSE`|Metoda byla úspěšná, ale tento skript byl již má daný stav.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o skriptovací stroj státy, najdete v části stavy se skriptovacím modulem [Windows skriptovacích strojů](../../winscript/windows-script-engines.md) .  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript::Clone](../../winscript/reference/iactivescript-clone.md)   
 [IActiveScript::GetScriptDispatch](../../winscript/reference/iactivescript-getscriptdispatch.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)   
 [IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md)   
 [IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)