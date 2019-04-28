---
title: IMachineDebugManager::EnumApplications | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IMachineDebugManager.EnumApplications
apilocation:
- scrobj.dll
helpviewer_keywords:
- IMachineDebugManager::EnumApplications
ms.assetid: 5d833db4-fd9b-4e61-bebb-130faede5a77
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8a75af7e151ad233e1bd592203fb33d2cd7f5cbe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977588"
---
# <a name="imachinedebugmanagerenumapplications"></a>IMachineDebugManager::EnumApplications
Vrátí enumerátor aktuální seznam spuštěných aplikací.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumApplications(  
   IEnumRemoteDebugApplications**  ppeda  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppeda`  
 [out] Enumerátor, který obsahuje aktuální seznam spuštěných aplikací.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrací enumerátor aktuální seznam spuštěných aplikací. Ladicí program integrovaného vývojového prostředí používá tuto metodu pro zobrazení a připojení aplikací za účelem ladění.  
  
## <a name="see-also"></a>Viz také  
 [IMachineDebugManager – rozhraní](../../winscript/reference/imachinedebugmanager-interface.md)