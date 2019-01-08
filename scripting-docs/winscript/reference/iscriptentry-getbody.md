---
title: IScriptEntry::GetBody | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetBody
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetBody
ms.assetid: 419c8c11-a1f8-4b97-ab00-e8af2b2f9bfc
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b5eb878bccaa8ed415fd813095e31064bc7e245
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094811"
---
# <a name="iscriptentrygetbody"></a>IScriptEntry::GetBody
Vrátí text, který odpovídá do těla `IScriptEntry` skriptovém bloku, blok funkce nebo skriptletu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetBody(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstr`  
 [out] Text, který je v těle jednoho z následujících akcí:  
  
-   `IScriptEntry` Bloku skriptu  
  
-   `IScriptEntry` Funkce v bloku – funkce  
  
-   `IScriptEntry` Skriptletu obslužné rutiny události  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)