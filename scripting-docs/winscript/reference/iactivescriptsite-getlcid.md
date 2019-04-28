---
title: IActiveScriptSite::GetLCID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: c6ebcfec9764aae98f7d74ac98e0c88ecec7c4da
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992770"
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