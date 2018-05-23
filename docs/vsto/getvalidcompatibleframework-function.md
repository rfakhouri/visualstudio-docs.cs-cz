---
title: Getvalidcompatibleframework – funkce
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
ms.openlocfilehash: a7df1e2d197147399fd6492222978dcf748a4bb2
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
---
# <a name="getvalidcompatibleframework-function"></a>Getvalidcompatibleframework – funkce
  Toto rozhraní API podporuje infrastrukturu rozhraní Office a není určena pro použití přímo z vašeho kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```c  
HRESULT WINAPI GetValidCompatibleFramework(  
    LPCWSTR lpwszCompatibleFrameworksXML,  
    BSTR* pbstrValidFrameworkTag  
);  
```  
  
### <a name="parameters"></a>Parametry  
|Parametr|Popis|  
|---------------|-----------------|  
|*lpwszCompatibleFrameworksXML*|Nepoužívejte.|  
|*pbstrValidFrameworkTag*|Nepoužívejte.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud funkci úspěšné, vrátí **S_OK**. Pokud se funkce nezdaří, vrátí kód chyby.  
  
  