---
title: IActiveScriptSite::GetDocVersionString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.GetDocVersionString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetDocVersionString
ms.assetid: ab3f892d-06d3-4cb5-9ea5-20c4a1e518cd
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a451f4883373978772643e11fe22feb9122be30e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097211"
---
# <a name="iactivescriptsitegetdocversionstring"></a>IActiveScriptSite::GetDocVersionString
Načte řetězec definované hostitele, který jednoznačně identifikuje aktuální verzi dokumentu. Pokud související dokument byl změněn mimo obor skript Windows (stejně jako v případě stránku HTML, který právě upravujete v aplikaci Poznámkový blok), můžete to spolu s jeho trvalého stavu, je vynucena Opětovná kompilace při příštím načtení skriptu uložit skriptovací stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDocVersionString(  
    BSTR *pbstrVersionString  // address of document version string  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstrVersionString`  
 [out] Adresa řetězec verze dokumentu definované hostitele.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření nebo `E_NOTIMPL` Pokud tato metoda není podporována.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `E_NOTIMPL` je vrácena skriptovací modul by měl předpokládat, že skript je synchronizovaný s dokumentem.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)