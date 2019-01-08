---
title: IActiveScriptParseProcedure32::ParseProcedureText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede37171-2f1e-4467-a358-17bd4a4f1869
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: e772d8276de5528f0aed25278a03725d09edb180
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090906"
---
# <a name="iactivescriptparseprocedure32parseproceduretext"></a>IActiveScriptParseProcedure32::ParseProcedureText
Analyzuje daný kód postupu a postup přidá do oboru názvů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ParseProcedureText(  
    LPCOLESTR pstrCode,              // address of procedure text  
    LPCOLESTR pstrFormalParams,      // address of formal parameter names  
    LPCOLESTR pstrProcedureName,     // address of procedure name  
    LPCOLESTR pstrItemName,          // address of item name  
    IUnknown *punkContext,           // address of debugging context  
    LPCOLESTR pstrDelimiter,         // address of end-of-procedure delimiter  
    DWORD_PTR dwSourceContextCookie, // application-defined value for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // procedure flags  
    IDispatch **ppdisp               // receives IDispatch pointer  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrCode`  
 [in] Adresa textu postup k vyhodnocení. Výklad tohoto řetězce závisí na skriptovacím jazyce.  
  
 `pstrFormalParams`  
 [in] Adresa názvy formálních parametrů pro proceduru. Názvy parametrů musí být odděleny příslušné oddělovače pro skriptovací stroj. Názvy nesmí být uzavřen v závorkách.  
  
 `pstrProcedureName`  
 [in] Adresa název procedury, který se má analyzovat.  
  
 `pstrItemName`  
 [in] Adresa názvu položky, která poskytuje kontext, ve kterém se má vyhodnotit postup. Pokud je tento parametr `NULL`, kód je vyhodnocen v globálním kontextu skriptovacího stroje.  
  
 `punkContext`  
 [in] Adresa objektu kontextu. Tento objekt je vyhrazen pro použití v prostředí ladění, kde může zadat takový obsah ladicím modulem a představovat aktivní kontext běhu. Pokud je tento parametr `NULL`, používá modul `pstrItemName` pro rozpoznání kontextu.  
  
 `pstrDelimiter`  
 [in] Adresa oddělovače end postup. Když `pstrCode` je analyzován z toku textu, hostitel obvykle používá oddělovač, jako jsou například dvě jednoduché uvozovky ("), k zjištění konce postup. Tento parametr určuje oddělovač, který používá hostitel a který umožňuje skriptovacímu stroji poskytovat některé podmíněné primitivní předzpracování (například nahrazení jednoduchou uvozovku ['] dvěma jednoduchými uvozovkami pro použití jako oddělovače). Jak přesně (a zda) skriptovací stroj umožňuje použití těchto informací závisí na skriptovacím stroji. Nastavte tento parametr na `NULL` Pokud hostitel nepoužili oddělovač pro označení konce postup.  
  
 `dwSourceContextCookie`  
 [in] Hodnota definované aplikací, která se používá pro účely ladění.  
  
 `ulStartingLineNumber`  
 [in] Založený na nule hodnota, která určuje, který řádek, začne analýza.  
  
 `dwFlags`  
 [in] Příznaky spojené s postupem. Může být kombinací těchto hodnot:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|SCRIPTPROC_ISEXPRESSION|Označuje, že kód v `pstrCode` je výraz, který představuje návratová hodnota procedury. Ve výchozím nastavení může kód obsahovat výraz, seznam příkazů nebo cokoli, co jinak povoluje v proceduře skriptovací jazyk.|  
|SCRIPTPROC_IMPLICIT_THIS|Označuje, že `this` ukazatel je zahrnuta v rámci procedury.|  
|SCRIPTPROC_IMPLICIT_PARENTS|Označuje, že nadřazených položek `this` ukazatele jsou zahrnuty v rámci procedury.|  
  
 `ppdisp`  
 [out] Adresa ukazatele na objekt obsahující globální metody a vlastnosti vašeho skriptu. Pokud skriptovací modul nepodporuje takový objekt `NULL` je vrácena.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_NOTIMPL`|Tato metoda není podporována. Skriptovací modul nepodporuje přidávání za běhu postupů, obor názvů.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj je v neinicializovaném nebo uzavřeném stavu).|  
|`OLESCRIPT_E_SYNTAX`|V postupu došlo k nespecifikované chybě syntaxe.|  
|`S_FALSE`|Skriptovací modul nepodporuje odesílání objektu. `ppdisp` parametr je nastaven na `NULL`.|  
  
## <a name="remarks"></a>Poznámky  
 Žádný kód skriptu je hodnocen během tohoto volání; Místo toho postup zkompilován do stavu skriptu, kde může být volán skriptem později.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptParseProcedure32](../../winscript/reference/iactivescriptparseprocedure32.md)