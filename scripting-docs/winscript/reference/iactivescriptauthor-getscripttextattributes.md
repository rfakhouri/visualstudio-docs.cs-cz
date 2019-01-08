---
title: IActiveScriptAuthor::GetScriptTextAttributes | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetScriptTextAttributes
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetScriptTextAttributes
ms.assetid: a53451de-cc5c-4b53-8e5f-81e196364caf
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57513e51248e26e39f95871e0dad329e8cc2f82c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094702"
---
# <a name="iactivescriptauthorgetscripttextattributes"></a>IActiveScriptAuthor::GetScriptTextAttributes
Vrátí text atributy pro blok skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptTextAttributes(  
    LPCOLESTR        pszCode,  
    ULONG            cch,  
    LPCOLESTR        pszDelimiter,  
    DWORD            dwFlags,  
    SOURCE_TEXT_ATTR *pattr);  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszCode`  
 [v size_is (`cch`)] textového bloku skriptu. Tento řetězec nemá hodnotu NULL byl ukončen.  
  
 `cch`  
 [in] Velikost použitou pro `pszCode` a `pattr` parametry.  
  
 `pszDelimiter`  
 [in] Adresa oddělovače end skriptu. Když `pszCode` je analyzován z toku textu, hostitel obvykle používá oddělovač (například dvěma jednoduchými uvozovkami), k zjištění konce skriptletu. Tento parametr nastavte na hodnotu NULL, pokud neexistuje žádný oddělovač pro určení konce bloku skriptu.  
  
 `dwFlags`  
 [in] Příznaky, které jsou spojeny s atributy textu bloku skriptu. Může být kombinací následujícího:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|GETATTRTYPE_DEPSCAN|0x0001|Identifikujte identifikátory, které mají atribut SOURCETEXT_ATTR_IDENTIFIER a identifikovat tečkou operátory, které mají atribut SOURCETEXT_ATTR_MEMBERLOOKUP.|  
|GETATTRFLAG_THIS|0x0100|Určete aktuální objekt, který má atribut SOURCETEXT_ATTR_THIS.|  
|GETATTRFLAG_HUMANTEXT|0x8000|Určete obsah a komentáře text řetězce, který má atribut SOURCETEXT_ATTR_HUMANTEXT.|  
  
 `pattr`  
 [v out size_is (`cch`)] informace o barvě pro kód bloku skriptu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Iactivescriptauthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)   
 [SOURCE_TEXT_ATTR – výčet](../../winscript/reference/source-text-attr-enumeration.md)