---
title: Getvstosolutionmetadata – funkce
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: f0cb0acd57ff04b7487d5311f8a05219b3ce0c0a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53853720"
---
# <a name="getvstosolutionmetadata-function"></a>Getvstosolutionmetadata – funkce
  Toto rozhraní API podporuje infrastrukturu sady Office a není určena pro použití přímo v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp
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
 Pokud funkce uspěje, vrátí **S_OK**. Pokud funkce selže, vrátí kód chyby.  
