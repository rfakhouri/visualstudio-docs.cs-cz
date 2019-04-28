---
title: IEnumDebugApplicationNodes::Clone | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugApplicationNodes.Clone
apilocation:
- pdm.dll
helpviewer_keywords:
- IEnumDebugApplicationNodes::Clone
ms.assetid: 7190954d-e2da-4a84-8e37-81d4d27886a8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 28ccf1805c1213bd01b1628c73e1dce5500ad8f0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62951512"
---
# <a name="ienumdebugapplicationnodesclone"></a>IEnumDebugApplicationNodes::Clone
Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Clone(  
   IEnumDebugApplicationNodes**  pperddp  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pperddp`  
 [out] Vrátí `IEnumDebugApplicationNodes` rozhraní klonu enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří enumerátor, který obsahuje stejného stavu jako aktuální enumerátor.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugApplicationNodes – rozhraní](../../winscript/reference/ienumdebugapplicationnodes-interface.md)