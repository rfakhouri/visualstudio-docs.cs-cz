---
title: Ensurevstocomponent – funkce
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 912c28086bb918afa406fca7cf4acce06e5be099
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54866073"
---
# <a name="ensurevstocomponent-function"></a>Ensurevstocomponent – funkce
  Toto rozhraní API podporuje infrastrukturu sady Office a není určena pro použití přímo v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp  
HRESULT EnsureVSTOComponent(  
    IVSTProject *pProject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*pProject*|Nepoužívejte.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud funkce uspěje, vrátí **S_OK**. Pokud funkce selže, vrátí kód chyby.  
