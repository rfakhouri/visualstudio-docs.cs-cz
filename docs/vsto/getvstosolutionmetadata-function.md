---
title: Getvstosolutionmetadata – funkce | Microsoft Docs
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
ms.openlocfilehash: 6c024d97d13c2794dd4fdaee6cfcd53d24c2e668
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="getvstosolutionmetadata-function"></a>GetVstoSolutionMetadata – funkce
  Toto rozhraní API podporuje infrastrukturu rozhraní Office a není určena pro použití přímo z vašeho kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT WINAPI GetVstoSolutionMetadata(  
    LPCWSTR lpwszSolutionMetadataKey,  
    ISolutionMetadata** ppSolutionInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*lpwszSolutionMetadataKey*|Nepoužívejte.|  
|*ppSolutionInfo*|Nepoužívejte.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud funkci úspěšné, vrátí **S_OK**. Pokud se funkce nezdaří, vrátí kód chyby.  
  
  