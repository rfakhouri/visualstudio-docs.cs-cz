---
title: IActiveScriptParseProcedureOld::ParseProcedureText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParseProcedureOld.ParseProcedureText
apilocation:
- jscript.dll
helpviewer_keywords:
- IActiveScriptParseProcedureOld::ParseProcedureText
ms.assetid: 21a21313-35ce-432d-b9a6-7999065f19ac
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e521bbdcd8d7397c1c2dfb377fd9b41811499f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993212"
---
# <a name="iactivescriptparseprocedureoldparseproceduretext"></a>IActiveScriptParseProcedureOld::ParseProcedureText
Analyzuje daný kód procedury a anonymní procedura přidá do oboru názvů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ParseProcedureText(  
   LPCOLESTR    pstrCode,  
   LPCOLESTR    pstrFormalParams,  
   LPCOLESTR    pstrItemName,  
   IUnknown*    punkContext,  
   LPCOLESTR    pstrDelimiter,  
   DWORD_PTR    dwSourceContextCookie,  
   ULONG        ulStartingLineNumber,  
   DWORD        dwFlags,  
   IDispatch**  ppdisp  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrCode`  
 [in] Postup text k vyhodnocení. Výklad tohoto řetězce závisí na skriptovacím jazyce.  
  
 `pstrFormalParams`  
 [in] Názvy formálních parametrů pro proceduru. Názvy parametrů musí být odděleny příslušné oddělovače pro skriptovací stroj. Názvy nesmí být uzavřen v závorkách.  
  
 `pstrItemName`  
 [in] Název pojmenované položky, která poskytuje kontext, ve kterém se má vyhodnotit postup. Pokud je tento parametr `NULL`, kód je vyhodnocen v globálním kontextu skriptovacího stroje.  
  
 `punkContext`  
 [in] Objekt kontextu. Tento objekt je vyhrazen pro použití v prostředí ladění, kde může zadat takový obsah ladicím modulem a představovat aktivní kontext běhu. Pokud je tento parametr `NULL`, používá modul `pstrItemName` pro rozpoznání kontextu.  
  
 `pstrDelimiter`  
 [in] Oddělovač – řád. Když `pstrCode` je analyzován z toku textu, hostitel obvykle používá oddělovač, jako jsou například dvě jednoduché uvozovky ("), k zjištění konce postup. Tento parametr určuje oddělovač, který používá hostitel a který umožňuje skriptovacímu stroji poskytovat některé podmíněné primitivní předzpracování (například nahrazení jednoduchou uvozovku ['] dvěma jednoduchými uvozovkami pro použití jako oddělovače). Jak přesně (a zda) skriptovací stroj používá tyto informace závisí na skriptovacím stroji. Nastavte tento parametr na `NULL` Pokud hostitel nepoužili oddělovač pro označení konce postup.  
  
 `dwSourceContextCookie`  
 [in] Hodnota definované aplikací, která se používá pro účely ladění.  
  
 `ulStartingLineNumber`  
 [in] Založený na nule hodnoty, která určuje, na které řádku se začne analýza.  
  
 `dwFlags`  
 [in] Příznaky spojené s postupem. Může být kombinací těchto hodnot.  
  
|Konstanta|Hodnota|Význam|  
|--------------|-----------|-------------|  
|SCRIPTPROC_ISEXPRESSION|0x00000020|Označuje, že kód v `pstrCode` je výraz, který představuje návratová hodnota procedury.|  
|SCRIPTPROC_IMPLICIT_THIS|0x00000100|Označuje, že `this` ukazatel je zahrnuta v rámci procedury.|  
|SCRIPTPROC_IMPLICIT_PARENTS|0x00000200|Označuje, že nadřazených položek `this` ukazatele jsou zahrnuty v rámci procedury.|  
  
 `ppdisp`  
 [out] Vrátí odeslání obálky, kde je výchozí metodou postup analyzovat touto metodou.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_NOTIMPL`|Tato metoda není podporována. Skriptovací modul nepodporuje přidávání za běhu postupů, obor názvů.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj je v neinicializovaném nebo uzavřeném stavu).|  
|`OLESCRIPT_E_SYNTAX`|V postupu došlo k nespecifikované chybě syntaxe.|  
|`S_FALSE`|Skriptovací modul nepodporuje odesílání objektu. `ppdisp`parametr je nastaven na `NULL`.|  
  
## <a name="remarks"></a>Poznámky  
 Žádný kód skriptu je hodnocen během tohoto volání; Místo toho postup zkompilován metodu na `ppdisp` kde může být volán skriptem později.  
  
 Toto rozhraní je zastaralé nahrazený `IActiveScriptParseProcedure` rozhraní. `IActiveScriptParseProcedure::ParseProcedureText` Způsob se podobá této metody, ale umožňuje zadat název procedury. Za všech okolností `IActiveScriptParseProcedure::ParseProcedureText` by měla sloužit.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptParseProcedureOld Interface](../../winscript/reference/iactivescriptparseprocedureold-interface.md)   
 [IActiveScriptParseProcedure::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure-parseproceduretext.md)