---
title: IActiveScriptDebug::GetScriptletTextAttributes | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptDebug.GetScriptletTextAttributes
apilocation:
- jscript.dll
helpviewer_keywords:
- IActiveScriptDebug::GetScriptletTextAttributes
ms.assetid: b3990d86-5fdf-4c9f-9678-3f4b808c7ca8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 781282b5c825954ada4fbb35daa2a97b379c3f13
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955039"
---
# <a name="iactivescriptdebuggetscriptlettextattributes"></a>IActiveScriptDebug::GetScriptletTextAttributes
Vrátí text atributy pro libovolného skriptletu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptletTextAttributes(  
   LPCOLESTR          pstrCode,  
   ULONG              uNumCodeChars,  
   LPCOLESTR          pstrDelimiter,  
   DWORD              dwFlags,  
   SOURCE_TEXT_ATTR*  pattr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrCode`  
 [in] Textu skriptletu. Tento řetězec nemusí být null byl ukončen.  
  
 `uNumCodeChars`  
 [in] Počet znaků v textu skriptletu.  
  
 `pstrDelimiter`  
 [in] Adresa oddělovače end skriptletu. Když `pstrCode` je analyzován z toku textu, hostitel obvykle používá oddělovač, jako jsou například dvě jednoduché uvozovky ("), k zjištění konce skriptletu. Tento parametr určuje oddělovač, který používá hostitel a který umožňuje skriptovacímu stroji poskytovat některé podmíněné primitivní předzpracování (například nahrazení jednoduchou uvozovku ['] dvěma jednoduchými uvozovkami pro použití jako oddělovače). Jak přesně (a zda) skriptovací stroj používá tyto informace závisí na skriptovacím stroji. Tento parametr nastavte na hodnotu NULL, pokud hostitel nepoužili oddělovač pro označení konce skriptletu.  
  
 `dwFlags`  
 [in] Příznaky spojené se skriptletem. Může být kombinací těchto hodnot:  
  
|Konstanta|Value|Popis|  
|--------------|-----------|-----------------|  
|GETATTRTYPE_DEPSCAN|0x0001|Označuje, že identifikátory a tečka mají identifikovat SOURCETEXT_ATTR_IDENTIFIER a SOURCETEXT_ATTR_MEMBERLOOKUP příznaků, v uvedeném pořadí.|  
|GETATTRFLAG_THIS|0x0100|Označuje, že se mají s příznakem SOURCETEXT_ATTR_THIS identifikovat identifikátor pro aktuální objekt.|  
|GETATTRFLAG_HUMANTEXT|0x8000|Označuje, že se mají s příznakem SOURCETEXT_ATTR_HUMANTEXT identifikovat text řetězce obsah a komentáře.|  
  
 `pattr`  
 [out v] Vyrovnávací paměť pro vrácený atributy obsahují.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Inteligentního hostitele, který implementuje `IDebugDocumentText` rozhraní tuto metodu můžete použít k volání delegáta `IDebugDocumentText::GetText` metody.  
  
 Toto volání je k dispozici protože skriptlety bývají výrazy a mohou mít odlišnou syntaxi než blok skriptu. Pokud mají stejnou syntaxi, implementace této metody bude identické s implementací `GetScriptTextAttributes` metody.  
  
## <a name="see-also"></a>Viz také  
 [Iactivescriptdebug – rozhraní](../../winscript/reference/iactivescriptdebug-interface.md)   
 [IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)   
 [IDebugDocumentText Interface](../../winscript/reference/idebugdocumenttext-interface.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)   
 [SOURCE_TEXT_ATTR – výčet](../../winscript/reference/source-text-attr-enumeration.md)