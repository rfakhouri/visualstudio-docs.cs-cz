---
title: "Setwefprocessid – metoda | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 404eec23-a67e-4f5b-b27d-86651f08be03
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0821c799a4d6385997704724c00a2aff4669eb17
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
  
  