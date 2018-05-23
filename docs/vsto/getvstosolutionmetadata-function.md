---
title: Getvstosolutionmetadata – funkce
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
ms.openlocfilehash: d21b0d2b90441f0b9be543933e7243dd41440b02
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="getvstosolutionmetadata-function"></a>Getvstosolutionmetadata – funkce
  Toto rozhraní API podporuje infrastrukturu rozhraní Office a není určena pro použití přímo z vašeho kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```c  
HRESULT WINAPI GetVstoSolutionMetadata(  
    LPCWSTR lpwszSolutionMetadataKey,  
    ISolutionMetadata** ppSolutionInfo  
);  
```  
  
### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*lpwszSolutionMetadataKey*|Nepoužívejte.|  
|*ppSolutionInfo*|Nepoužívejte.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud funkci úspěšné, vrátí **S_OK**. Pokud se funkce nezdaří, vrátí kód chyby.  
  
  