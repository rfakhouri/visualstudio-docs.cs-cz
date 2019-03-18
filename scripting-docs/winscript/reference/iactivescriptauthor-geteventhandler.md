---
title: IActiveScriptAuthor::GetEventHandler | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetEventHandler
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetEventHandler
ms.assetid: 87c7a71d-46b9-448c-b34d-394105e20982
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7bba60df6485ddaac0363a3416739efd7be69389
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58145639"
---
# <a name="iactivescriptauthorgeteventhandler"></a>IActiveScriptAuthor::GetEventHandler
Vrátí skriptletu, který má zadané atributy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetEventHandler(  
   IDispatch          *pdisp,  
   LPCOLESTR          pszItem,  
   LPCOLESTR          pszSubItem,  
   LPCOLESTR          pszEvent,  
   IScriptEntry       **ppse  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdisp`  
 [in] `IDispatch` Objekt, který odpovídá `NamedItem` skriptletu je připojen.  
  
 `pszItem`  
 [in] Adresa vyrovnávací paměti nejvyšší úrovně identifikátor skriptletu plně kvalifikovaný název v hostiteli.  
  
 `pszSubItem`  
 [in] Adresa vyrovnávací paměti druhé úrovně identifikátor skriptletu plně kvalifikovaný název v hostiteli. Pokud název obsahuje pouze jednu úroveň nastavena na hodnotu NULL.  
  
 `pszEvent`  
 [in] Adresa vyrovnávací paměti, který obsahuje název události. Skriptletu je obslužnou rutinu události pro tuto událost.  
  
 `ppse`  
 [out] Adresa proměnné, která přijímá ukazatel `IScriptEntry` rozhraní, který má zadané atributy skriptletu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor Interface](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)