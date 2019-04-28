---
title: IProcessDebugManager::GetDefaultApplication | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProcessDebugManager.GetDefaultApplication
apilocation:
- pdm.dll
helpviewer_keywords:
- IProcessDebugManager::GetDefaultApplication
ms.assetid: 6c991faa-ea40-4d18-a1b8-6e7d0de6dd43
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6fec84a60863b426f2f65c26e2375262b109d635
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62953969"
---
# <a name="iprocessdebugmanagergetdefaultapplication"></a>IProcessDebugManager::GetDefaultApplication
Vrátí výchozí objekt aplikace pro aktuální proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDefaultApplication(  
   IDebugApplication**  ppda  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppda`  
 [out] Objekt ladění aplikace pro tuto aplikaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytvoří nový objekt ladění aplikace a přidá jej do běhu seznam aplikací, v případě potřeby.  
  
 Moduly jazyka by měl používat aplikaci určené `GetDefaultApplication` metody, pokud jsou spuštěné na hostitele, který neposkytuje aplikace.  
  
## <a name="see-also"></a>Viz také  
 [IProcessDebugManager – rozhraní](../../winscript/reference/iprocessdebugmanager-interface.md)