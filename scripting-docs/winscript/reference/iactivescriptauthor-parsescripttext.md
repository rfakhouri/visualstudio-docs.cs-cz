---
title: IActiveScriptAuthor::ParseScriptText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.ParseScriptText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::ParseScriptText
ms.assetid: ebe212e8-6789-423d-ad22-92be984dc7ad
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe6870f3b19c5727fdbea0418b8373b990cb671a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955078"
---
# <a name="iactivescriptauthorparsescripttext"></a>IActiveScriptAuthor::ParseScriptText
Analyzuje text skriptu, přidá text skriptu pro vytváření modulu a vytvoří `IScriptEntry` objekt, který odpovídá bloku skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ParseScriptText(  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszCode`  
 [in] Text skriptu k analýze.  
  
 `pszItemName`  
 [in] Adresa vyrovnávací paměti, který obsahuje název položky přidružené k bloku skriptu.  
  
 `pszDelimiter`  
 [in] Adresa koncového ze skriptu bloku oddělovač. Když `pszCode` je analyzován z toku textu, hostitel obvykle používá oddělovač (například dvěma jednoduchými uvozovkami), k zjištění konce bloku skriptu. Tento parametr nastavte na hodnotu NULL, pokud neexistuje žádný oddělovač pro určení konce bloku skriptu.  
  
 `dwCookie`  
 [in] Hodnotu definované aplikací, který je spojen s novými `IScriptEntry` objektu.  
  
 `dwFlags`  
 [in] Nepoužívá se.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)