---
title: IScriptEntry::GetBody | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 7f8f1ad24660401d575af2724b788387fd546af8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60064915"
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
  
- `IScriptEntry` Bloku skriptu  
  
- `IScriptEntry` Funkce v bloku – funkce  
  
- `IScriptEntry` Skriptletu obslužné rutiny události  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)