---
title: Setwefprocessid – metoda
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3ccce49992073f11245929bf7af0b966537bd079
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53886147"
---
# <a name="setwefprocessid-method"></a>Setwefprocessid – metoda
  Poskytuje identifikátor procesu, který se spustí rozšíření webové rozhraní Framework (WEF) obsah.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*dwProcessId*|Identifikátor procesu, který se použije ke spuštění WEF obsah.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která označuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda musí být volána po procesu WEF obsahu, ale před spuštěním jakéhokoli WEF obsahu.  
  
 Pokud chcete připojit ladicí program k procesu obsahu WEF vývojové prostředí, musí prostředí ve vaší implementaci této metody provedení této operace.  
