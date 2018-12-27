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
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: b93e0de5f1d8c1d4e93189e7bfee36d44db19319
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53648875"
---
# <a name="getvalidcompatibleframework-function"></a>Getvalidcompatibleframework – funkce
  Toto rozhraní API podporuje infrastrukturu sady Office a není určena pro použití přímo v kódu.  

## <a name="syntax"></a>Syntaxe  

```csharp 
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
 Pokud funkce uspěje, vrátí **S_OK**. Pokud funkce selže, vrátí kód chyby.  

