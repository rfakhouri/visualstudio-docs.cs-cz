---
title: IActiveScriptAuthor::ParseScriptText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 8c5f9e4969795cedd7da80864c1ad69c0d68f8b9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091803"
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
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptAuthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)