---
title: IActiveScriptSite::GetLCID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.GetLCID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_GetLCID
ms.assetid: 7b4a2dc1-bcf6-4bbf-884e-97b305a28eb7
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 959989d14d2a71f9c9eab4c78ef1b1bd9078362f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095001"
---
# <a name="iactivescriptsitegetlcid"></a>IActiveScriptSite::GetLCID
Načte identifikátor národního prostředí, které jsou spojené s uživatelským rozhraním hostitele. Skriptovací modul použije identifikátor zajistit, že chybové řetězce a další prvky uživatelského rozhraní generovaných modul zobrazí příslušný jazyk.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetLCID(  
    LCID *plcid  // address of variable for language identifier  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `plcid`  
 [out] Adresa proměnné, která přijímá identifikátor národního prostředí pro prvky uživatelského rozhraní zobrazí skriptovacím modulem.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_NOTIMPL`|Tato metoda není implementována. Používají národní prostředí definované v systému.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud tato metoda vrátí `E_NOTIMPL`, by měla sloužit identifikátor národního prostředí definované v systému.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)