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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5c27588eb6d09c0565b4b4d8faec52239ef792f7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  