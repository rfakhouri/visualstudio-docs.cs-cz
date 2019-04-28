---
title: IActiveScriptParse::AddScriptlet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParse.AddScriptlet
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParse_AddScriptlet
ms.assetid: 824929f4-4dd3-473a-92d9-0b96acea2f14
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee5d76060789118e9051c2d8dcc5fc570617f6a8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62954951"
---
# <a name="iactivescriptparseaddscriptlet"></a>IActiveScriptParse::AddScriptlet
Přidá skriptlet kódu do skriptu. Tato metoda se používá v prostředích, kde trvalý stav souboru, který je vzájemně propojeny s dokumentem hostitele a hostitele je zodpovědný za obnovení skript, nikoli prostřednictvím `IPersist*` rozhraní. Primární příklady jsou skriptovací jazyky HTML, které umožňují skriptlety kód vložený v dokumentu HTML připojené na vnitřní události (například ONCLICK="button1.text='Exit" ").  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AddScriptlet(  
    LPCOLESTR pstrDefaultName,       // address of default name of scriptlet  
    LPCOLESTR pstrCode,              // address of scriptlet text  
    LPCOLESTR pstrItemName,          // address of item name  
    LPCOLESTR pstrSubItemName,       // address of subitem name  
    LPCOLESTR pstrEventName,         // address of event name  
    LPCOLESTR pstrDelimiter,         // address of end-of-scriptlet delimiter  
    DWORD_PTR dwSourceContextCookie, // application-defined value for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // scriptlet flags  
    BSTR *pbstrName,                 // address of actual name of scriptlet  
    EXCEPINFO *pexcepinfo            // address of exception information  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrDefaultName`  
 [in] Adresa výchozí název, který chcete přidružit k skriptletu. Pokud skriptletu neobsahuje informace o názvech (stejně jako v předchozím příkladu ONCLICK), tento název se použije k identifikaci skriptletu. Pokud je tento parametr `NULL`, skriptovací stroj vyrábí jedinečný název v případě potřeby.  
  
 `pstrCode`  
 [in] Adresa textu skriptletu k přidání. Výklad tohoto řetězce závisí na skriptovacím jazyce.  
  
 `pstrItemName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název položky přidružené k této skriptletu. Tento parametr navíc `pstrSubItemName`, určuje objekt, pro kterou je skriptletu obslužné rutiny události.  
  
 `pstrSubItemName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název `subobject` s názvem předmětu, se kterou souvisí tato skriptletu; tento název musí být nalezena v informace o typu s názvem položky. Tento parametr hodnotu NULL v případě, že skriptlet má být spojen s požadovanou pojmenovanou položku `subitem`. Tento parametr navíc `pstrItemName`, identifikuje konkrétní objektu, pro kterou je skriptletu obslužné rutiny události.  
  
 `pstrEventName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název události, pro kterou je skriptletu obslužné rutiny události.  
  
 `pstrDelimiter`  
 [in] Adresa oddělovače end skriptletu. Když `pstrCode` parametr je analyzován z toku textu, hostitel obvykle používá oddělovač, jako jsou například dvě jednoduché uvozovky ("), k zjištění konce skriptletu. Tento parametr určuje oddělovač, který používá hostitel a který umožňuje skriptovacímu stroji poskytovat některé podmíněné primitivní předzpracování (například nahrazení jednoduchou uvozovku ['] dvěma jednoduchými uvozovkami pro použití jako oddělovače). Jak přesně (a zda) skriptovací stroj umožňuje použití těchto informací závisí na skriptovacím stroji. Tento parametr nastavte na hodnotu NULL, pokud hostitel nepoužili oddělovač pro označení konce skriptletu.  
  
 `dwSourceContextCookie`  
 [in] Hodnota definované aplikací, která se používá pro účely ladění.  
  
 `ulStartingLineNumber`  
 [in] Založený na nule hodnota, která určuje, který řádek, začne analýza.  
  
 `dwFlags`  
 [in] Příznaky spojené se skriptletem. Může být kombinací následujícího:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|SCRIPTTEXT_ISVISIBLE|Označuje, že text skriptu by měly být viditelné (a tedy volatelný názvem) jako globální metoda v oboru názvu skriptu.|  
|SCRIPTTEXT_ISPERSISTENT|Označuje, že by měla uložit kód přidaný během volání, pokud je uložen skriptovací stroj (například pomocí volání `IPersist*::Save`), nebo pokud skriptovací stroj obnoven pomocí přechodu zpět do stavu spuštění. Další informace o tomto stavu najdete v článku stavy se skriptovacím modulem.|  
  
 `pbstrName` ,  
 [out] Skutečný název používaný k identifikaci skriptletu. Toto je v pořadí podle priority: název v textu skriptletu explicitně zadán, výchozí název zadaný v `pstrDefaultName`, nebo jedinečný název syntetizovat skriptovací modul.  
  
 `pexcepinfo` ,  
 [out] Adresa struktury obsahující informace o výjimce. Tato struktura by měl být vyplněno, pokud se vrátí DISP_E_EXCEPTION.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`DISP_E_EXCEPTION`|Při analýze skriptletu došlo k výjimce. `pexcepinfo` Parametr obsahuje informace o výjimce.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_NOTIMPL`|Tato metoda není podporována. skriptovací modul nepodporuje přidávání skriptlety zpracování událostí.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován) a proto se nezdařilo.|  
|`OLESCRIPT_E_INVALIDNAME`|Zadaný výchozí název je neplatný v tomto skriptovací jazyk.|  
|`OLESCRIPT_E_SYNTAX`|Ve skriptletu došlo k nespecifikované chybě syntaxe.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)