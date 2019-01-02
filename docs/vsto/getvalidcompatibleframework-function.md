---
title: Getvalidcompatibleframework – funkce
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
ms.openlocfilehash: 30a116993535e3b99b4e91edf07752c00a020859
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53835484"
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
