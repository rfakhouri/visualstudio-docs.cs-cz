---
title: IEnumDebugApplicationNodes::Skip | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugApplicationNodes.Skip
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumDebugApplicationNodes::Skip
ms.assetid: b2ad1957-95b5-4c09-9a44-5a765a5308ae
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97880e6a40efefa5f3643b474ba5d731f8dc3630
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62951479"
---
# <a name="ienumdebugapplicationnodesskip"></a>IEnumDebugApplicationNodes::Skip
Vynechá zadaný počet segmentů v sekvenci výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet segmentů v pořadí výčtu pro přeskočení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vynechá zadaný počet segmentů v sekvenci výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugApplicationNodes – rozhraní](../../winscript/reference/ienumdebugapplicationnodes-interface.md)