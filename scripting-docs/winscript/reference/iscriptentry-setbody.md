---
title: IScriptEntry::SetBody | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetBody
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetBody
ms.assetid: 719062e4-98e4-4a7b-946d-6e5dbbcc5225
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 993ffe59abb9458e1b400633430f708e7520599c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088579"
---
# <a name="iscriptentrysetbody"></a>IScriptEntry::SetBody
Nastaví text, který je v těle `IScriptEntry` bloku skriptu nebo `IScriptScriptlet` skriptletu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetBody(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `psz`  
 [in] Pro `IScriptEntry` bloku skriptu `psz` je text uzavřený v značky skriptu.  
  
 Pro `IScriptEntry` bloku funkce `psz` představuje tělo funkce.  
  
 Pro `IScriptScriptlet` objektu (která je odvozena z `IScriptEntry`), `psz` je skript textu skriptletu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Iscriptentry – rozhraní](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)