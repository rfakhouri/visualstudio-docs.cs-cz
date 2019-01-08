---
title: IActiveScriptParseProcedure::ParseProcedureText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParseProcedure.ParseProcedureText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParseProcedure_ParseProcedureText
ms.assetid: 345a74ae-b4e8-42b2-abd8-633a370e8e7f
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3ff49652897c106c1629d5f7b3133a66ccf7c981
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093402"
---
# <a name="iactivescriptparseprocedureparseproceduretext"></a>IActiveScriptParseProcedure::ParseProcedureText
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
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)