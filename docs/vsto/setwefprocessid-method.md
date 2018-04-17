---
title: Setwefprocessid – metoda | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9dbd5a9ffb2ff9b3833dc8007fdfafb4b1a35857
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="setwefprocessid-method"></a>SetWefProcessId – metoda
  Poskytuje identifikátor procesu, který se spustí Web rozšíření Framework (WEF) obsah.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*dwProcessId*|Identifikátor procesu, který se použije ke spuštění WEF obsah.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která určuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda musí být volána po vytvoření procesu WEF obsahu, ale před spuštěním jakékoli WEF obsah.  
  
 Pokud chcete připojit ladicí program k obsahu proces WEF vývojového prostředí, prostředí musí provést tuto operaci v vaší implementace této metody.  
  
  