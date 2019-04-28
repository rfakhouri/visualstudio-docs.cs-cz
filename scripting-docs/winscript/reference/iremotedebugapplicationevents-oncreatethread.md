---
title: IRemoteDebugApplicationEvents::OnCreateThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEvents.OnCreateThread
apilocation:
- jscript.dll
helpviewer_keywords:
- IRemoteDebugApplicationEvents::OnCreateThread
ms.assetid: 0b7c5181-eda6-4303-b4ae-d45962e8a3d3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64317666fe5c449207c2eedac550ca6a1effc1ab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62943636"
---
# <a name="iremotedebugapplicationeventsoncreatethread"></a>IRemoteDebugApplicationEvents::OnCreateThread
Zpracovává událost vytvoření vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnCreateThread(  
   IRemoteDebugApplicationThread*  prdat  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `prdat`  
 [in] Nově vytvořeného vlákna.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda zpracovává vytvořit vlákno událost.  
  
## <a name="see-also"></a>Viz také  
 [IRemoteDebugApplicationEvents – rozhraní](../../winscript/reference/iremotedebugapplicationevents-interface.md)