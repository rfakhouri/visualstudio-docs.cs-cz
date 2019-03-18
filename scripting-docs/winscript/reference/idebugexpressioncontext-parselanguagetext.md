---
title: IDebugExpressionContext::ParseLanguageText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionContext.ParseLanguageText
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpressionContext::ParseLanguageText
ms.assetid: 650cb016-7d80-4011-b264-780f871a3466
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50f9f398b9193c776f8e2a823b78ce7b8da438b1
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58153471"
---
# <a name="idebugexpressioncontextparselanguagetext"></a>IDebugExpressionContext::ParseLanguageText
Vytvoří výrazu ladění pro zadaný text.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ParseLanguageText(  
   LPCOLESTR           pstrCode,  
   UINT                nRadix,  
   LPCOLESTR           pstrDelimiter,  
   DWORD               dwFlags,  
   IDebugExpression**  ppe  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrCode`  
 [in] Obsahuje text výrazu nebo příkazů.  
  
 `nRadix`  
 [in] Číselná soustava k použití.  
  
 `pstrDelimiter`  
 [in] Oddělovač koncový ze skriptu blok. Když `pstrCode` je analyzován z toku textu, hostitel obvykle používá oddělovač, jako jsou například dvě jednoduché uvozovky ("), k zjištění konce bloku skriptu. Tento parametr určuje oddělovač, který používá hostitel a který umožňuje skriptovacímu stroji poskytovat některé podmíněné primitivní předzpracování (například nahrazení jednoduchou uvozovku ['] dvěma jednoduchými uvozovkami pro použití jako oddělovače). Jak přesně (a zda) skriptovací stroj používá tyto informace závisí na skriptovacím stroji. Nastavte tento parametr na `NULL` Pokud hostitel nepoužili oddělovač pro označení konce bloku skriptu.  
  
 `dwFlags`  
 [in] Kombinace následující příznaky ladění text:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|DEBUG_TEXT_ISEXPRESSION|0x00000001|Označuje, že text je výraz na rozdíl od příkazu. Tento příznak může mít vliv na způsob, ve kterém se analyzovat text v některých jazycích.|  
|DEBUG_TEXT_RETURNVALUE|0x00000002|Pokud vrácená hodnota je k dispozici, použije se volající.|  
|DEBUG_TEXT_NOSIDEEFFECTS|0x00000004|Nepovolit vedlejší účinky. Pokud je tento příznak nastaven, vyhodnocování výrazu by měl změnit bez běhový stav.|  
|DEBUG_TEXT_ALLOWBREAKPOINTS|0x00000008|Umožňuje body přerušení během vyhodnocení textu. Pokud není nastavený tento příznak jsou ignorovány zarážky během vyhodnocení textu.|  
|DEBUG_TEXT_ALLOWERRORREPORT|0x00000010|Umožňuje zprávy o chybách během vyhodnocení textu. Pokud není nastavený tento příznak pak nejsou hlášeny chyby k hostiteli během hodnocení.|  
|DEBUG_TEXT_EVALUATETOCODECONTEXT|0x00000020|Označuje výraz k vyhodnocení na kontext kódu, spíše než spuštění samotný výraz|  
  
 `ppe`  
 [out] Vrátí výraz ladění pro zadaný text.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří výrazu ladění pro zadaný text.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpressionContext – rozhraní](../../winscript/reference/idebugexpressioncontext-interface.md)