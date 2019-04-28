---
title: IScriptEntry::GetName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetName
ms.assetid: 56daa288-618f-497c-a360-7d443afd478b
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d23843aa72ce5cf79f6442048b6493d17eb6ef64
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62787767"
---
# <a name="iscriptentrygetname"></a>IScriptEntry::GetName
U položky, které představují jeden objekt (například funkce) vrátí název objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetName(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstr`  
 [out] Název objektu reprezentovaného parametrem `IScriptEntry` bloku skriptu. Pokud položka nepředstavuje jeden objekt, je vrácena hodnota NULL.  
  
 Podřízené položky představují jeden funkce objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Iscriptentry – rozhraní](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptNode:: CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)