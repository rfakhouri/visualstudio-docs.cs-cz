---
title: IActiveScriptParse::ParseScriptText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParse.ParseScriptText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParse_ParseScriptText
ms.assetid: 2d237d6c-cc65-415b-8808-72791304a136
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8d88258a1bd16dba1de8d6ffa282f0f8ba409e2d
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088969"
---
# <a name="iactivescriptparseparsescripttext"></a>IActiveScriptParse::ParseScriptText
Analyzuje daný skriptlet kódu, přidává deklarace do oboru názvů a hodnotí kód podle potřeby.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ParseScriptText(  
    LPCOLESTR pstrCode,              // address of scriptlet text  
    LPCOLESTR pstrItemName,          // address of item name  
    IUnknown *punkContext,           // address of debugging context  
    LPCOLESTR pstrDelimiter,         // address of end-of-scriptlet delimiter  
    DWORD_PTR dwSourceContextCookie, // cookie for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // scriptlet flags  
    VARIANT *pvarResult,             // address of buffer for results  
    EXCEPINFO *pexcepinfo            // address of buffer for error data  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|||  
|-|-|  
|`pstrCode`|[in] Adresa textu skriptletu k vyhodnocení. Výklad tohoto řetězce závisí na skriptovacím jazyce.|  
|`pstrItemName`|[in] Adresa názvu položky, která poskytuje kontext, ve kterém skriptletu k vyhodnocení. Pokud má parametr hodnotu NULL, kód je vyhodnocen v globálním kontextu skriptovacího stroje.|  
|`punkContext`|[in] Adresa objektu kontextu. Tento objekt je vyhrazen pro použití v prostředí ladění, kde může zadat takový obsah ladicím modulem a představovat aktivní kontext běhu. Pokud tento parametr hodnotu NULL, použije modul `pstrItemName` pro rozpoznání kontextu.|  
|`pstrDelimiter`|[in] Adresa oddělovače end skriptletu. Když `pstrCode` je analyzován z toku textu, hostitel obvykle používá oddělovač, jako jsou například dvě jednoduché uvozovky ("), k zjištění konce skriptletu. Tento parametr určuje oddělovač, který používá hostitel a který umožňuje skriptovacímu stroji poskytovat některé podmíněné primitivní předzpracování (například nahrazení jednoduchou uvozovku ['] dvěma jednoduchými uvozovkami pro použití jako oddělovače). Jak přesně (a zda) skriptovací stroj umožňuje použití těchto informací závisí na skriptovacím stroji. Nastavte tento parametr na `NULL` Pokud hostitel nepoužili oddělovač pro označení konce skriptletu.|  
|`dwSourceContextCookie`|[in] Soubor cookie používaný pro účely ladění.|  
|`ulStartingLineNumber`|[in] Založený na nule hodnota, která určuje, který řádek, začne analýza.|  
|`dwFlags`|[in] Příznaky spojené se skriptletem. Může být kombinací těchto hodnot:|  
  
|Hodnota|Význam|  
|-----------|-------------|  
|SCRIPTTEXT_ISEXPRESSION|Pokud rozdíl mezi výpočetním výrazem a prohlášení je důležitý, ale syntakticky dvojznačný ve skriptovacím jazyku, tento příznak určuje, že skriptlet má být interpretován jako výraz, nikoli jako příkaz nebo seznamu příkazů. Standardně se předpokládají příkazy, pokud se dá určit správnou volbu podle syntaxe textu skriptletu.|  
|SCRIPTTEXT_ISPERSISTENT|Označuje, že by měla uložit kód přidaný během volání, pokud je uložen skriptovací stroj (například pomocí volání `IPersist*::Save`), nebo pokud skriptovací stroj obnoven pomocí přechodu zpět do stavu spuštění.|  
|SCRIPTTEXT_ISVISIBLE|Označuje, že text skriptu by měly být viditelné (a tedy volatelný názvem) jako globální metoda v oboru názvu skriptu.|  
  
|||  
|-|-|  
|`pvarResult`|[out] Adresa vyrovnávací paměti, která přijímá výsledky zpracování skriptletu, nebo `NULL` Pokud volající nepředpokládá žádný výsledek (to znamená, že není nastavena hodnota SCRIPTTEXT_ISEXPRESSION).|  
|`pexcepinfo`|[out] Adresa struktury, která bude přijímat informace o výjimce. Tato struktura je vyplněna, pokud `IActiveScriptParse::ParseScriptText` vrátí DISP_E_EXCEPTION.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`DISP_E_EXCEPTION`|Při zpracování skriptletu došlo k výjimce. `pexcepinfo` Parametr obsahuje informace o výjimce.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_NOTIMPL`|Tato metoda není podporována. Skriptovací modul nepodporuje vyhodnocení výrazů nebo příkazů.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj je v neinicializovaném nebo uzavřeném stavu, nebo byl nastaven příznak SCRIPTTEXT_ISEXPRESSION a skriptovací stroj je v inicializovaném stavu).|  
|`OLESCRIPT_E_SYNTAX`|Ve skriptletu došlo k nespecifikované chybě syntaxe.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud skriptovací stroj je v inicializovaném stavu, žádný kód nebudou skutečně hodnocen během tohoto volání; Místo toho je takový kód ve frontě a spuštěn, když skriptovací nástroj je přepnuta do (nebo pomocí) počátečního stavu. Protože spuštění není povoleno v inicializovaném stavu, jedná se o chybu volání této metody s příznakem scripttext_isexpression při inicializovaném stavu.  
  
 Skriptletu může být výraz, seznam příkazů nebo cokoli, co povoluje skriptovací jazyk. Například tato metoda se používá v pořadí vyhodnocování HTML \<skript > značky, který umožňuje příkazy, které mají být provedeny při konstrukci stránky HTML, místo jejich kompilace do stavu skriptu.  
  
 Kód předaný této metodě musí být platnou a kompletní částí kódu. Například v jazyce VBScript je neplatné volat tuto metodu jednou se Sub Function(x) a podruhé s `End Sub`. Analyzátor nesmí čekat na dokončení podprogramu druhé volání, ale spíše musí generovat chybu analýzy, protože deklarace podprogramu byla zahájena, ale nebyla dokončena.  
  
 Další informace o stavech skriptu naleznete v části stavy se skriptovacím modulem v [Windows skriptovacích strojů](../../winscript/windows-script-engines.md).  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)