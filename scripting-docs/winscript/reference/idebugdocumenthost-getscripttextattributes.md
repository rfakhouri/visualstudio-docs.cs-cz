---
title: IDebugDocumentHost::GetScriptTextAttributes | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.GetScriptTextAttributes
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::GetScriptTextAttributes
ms.assetid: fe459d0d-937f-4176-be81-99d5cca121a1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 016073d2ce22ab814716efc204ce573ea17cd510
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092713"
---
# <a name="idebugdocumenthostgetscripttextattributes"></a>IDebugDocumentHost::GetScriptTextAttributes
Vrátí text atributy pro blok textu dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptTextAttributes(  
   LPCOLESTR          pstrCode,  
   ULONG              uNumCodeChars,  
   LPCOLESTR          pstrDelimiter,  
   DWORD              dwFlags,  
   SOURCE_TEXT_ATTR*  pattr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrCode`  
 [in] Text blok skriptu. Tento řetězec nemusí být null byl ukončen.  
  
 `uNumCodeChars`  
 [in] Počet znaků v textu bloku skriptu.  
  
 `pstrDelimiter`  
 [in] Adresa koncového ze skriptu bloku oddělovač. Když `pstrCode` je analyzován z toku textu, hostitel obvykle používá oddělovač, jako jsou například dvě jednoduché uvozovky ("), k zjištění konce bloku skriptu. Tento parametr určuje oddělovač, který používá hostitel a který umožňuje skriptovacímu stroji poskytovat některé podmíněné primitivní předzpracování (například nahrazení jednoduchou uvozovku ['] dvěma jednoduchými uvozovkami pro použití jako oddělovače). Jak přesně (a zda) skriptovací stroj používá tyto informace závisí na skriptovacím stroji. Tento parametr nastavte na hodnotu NULL, pokud hostitel nepoužili oddělovač pro označení konce bloku skriptu.  
  
 `dwFlags`  
 [in] Příznaky spojené s daným blokem skriptu. Může být kombinací těchto hodnot:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|GETATTRTYPE_DEPSCAN|0x0001|Označuje, že identifikátory a tečka mají identifikovat SOURCETEXT_ATTR_IDENTIFIER a SOURCETEXT_ATTR_MEMBERLOOKUP příznaků, v uvedeném pořadí.|  
|GETATTRFLAG_THIS|0x0100|Označuje, že se mají s příznakem SOURCETEXT_ATTR_THIS identifikovat identifikátor pro aktuální objekt.|  
|GETATTRFLAG_HUMANTEXT|0x8000|Označuje, že se mají s příznakem SOURCETEXT_ATTR_HUMANTEXT identifikovat text řetězce obsah a komentáře.|  
  
 `pattr`  
 [out v] Vyrovnávací paměť pro vrácený atributy obsahují.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Hostitel používá pouze výchozí atributy.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrací atributy textu pro libovolný blok textu dokumentu. Je to přijatelné pro hostitele k vrácení `E_NOTIMPL`, v takovém případě se používají výchozí atributy.  
  
## <a name="see-also"></a>Viz také  
 [Idebugdocumenthost – rozhraní](../../winscript/reference/idebugdocumenthost-interface.md)   
 [SOURCE_TEXT_ATTR – výčet](../../winscript/reference/source-text-attr-enumeration.md)