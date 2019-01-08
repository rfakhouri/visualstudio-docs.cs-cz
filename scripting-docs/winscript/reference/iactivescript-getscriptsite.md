---
title: IActiveScript::GetScriptSite | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptSite
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptSite
ms.assetid: 83a2a89d-93d0-4cbd-9244-91a730cb406b
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 85b7d94ccb9e2589b10bf705721fc289df9638a9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094156"
---
# <a name="iactivescriptgetscriptsite"></a>IActiveScript::GetScriptSite
Načte objekt lokality přidružený modul skriptu Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptSite(  
    REFIID iid,           // interface identifier  
    void **ppvSiteObject  // address of host site interface  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `iid`  
 [in] Identifikátor požadované rozhraní.  
  
 `ppvSiteObject`  
 [out] Adresa umístění, která přijímá ukazatel rozhraní na objekt sítě hostiteli.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_NOINTERFACE`|Zadané rozhraní není podporováno.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`S_FALSE`|Žádná lokalita byla nastavena; `ppvSiteObject` parametr je nastaven na `NULL`.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)