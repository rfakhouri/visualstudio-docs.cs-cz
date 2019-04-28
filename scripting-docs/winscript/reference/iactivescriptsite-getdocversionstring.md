---
title: IActiveScriptSite::GetDocVersionString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 7327b71329c1f476eab9c27d5e0d5a047664abfa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992725"
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