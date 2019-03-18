---
title: IActiveScriptAuthor::AddScriptlet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.AddScriptlet
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::AddScriptlet
ms.assetid: 879a6651-f187-4934-b130-c1247549900b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64df7bd4c0d0dde303cdc15d7111688d14c7dc49
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58146978"
---
# <a name="iactivescriptauthoraddscriptlet"></a>IActiveScriptAuthor::AddScriptlet
Přidá skriptlet kódu jako podřízený objekt úrovni kořenového adresáře `IScriptNode` objektu. Na hostiteli může mít pouze dvě úrovně plně kvalifikovaný název skriptletu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT AddScriptlet(  
   LPCOLESTR pszDefaultName,  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszSubItemName,  
   LPCOLESTR pszEventName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszDefaultName`  
 [in] Adresa výchozí název, který chcete přidružit k skriptletu.  
  
 `pszCode`  
 [in] Adresa textu skriptletu.  
  
 `pszItemName`  
 [in] Adresa vyrovnávací paměti nejvyšší úrovně identifikátor skriptletu plně kvalifikovaný název v hostiteli.  
  
 `pszSubItemName`  
 [in] Adresa vyrovnávací paměti druhé úrovně identifikátor skriptletu plně kvalifikovaný název v hostiteli. Pokud název obsahuje pouze jednu úroveň nastavena na hodnotu NULL.  
  
 `pszEventName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název události, pro kterou je skriptletu obslužné rutiny události.  
  
 `pszDelimiter`  
 [in] Adresa koncového ze skriptu bloku oddělovač. Když `pszCode` je analyzován z toku textu, hostitel obvykle používá oddělovač (například dvěma jednoduchými uvozovkami), k zjištění konce bloku skriptu. Tento parametr nastavte na hodnotu NULL, pokud oddělovač neoznačí konec bloku skriptu.  
  
 `dwCookie`  
 [in] Aplikaci hodnotu definovanou uživatelem, který slouží k přidružení hostitelský objekt skriptletu.  
  
 `dwFlags`  
 [in] Nepoužívá se.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)