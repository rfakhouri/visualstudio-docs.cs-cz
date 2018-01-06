---
title: "Getvalidcompatibleframework – funkce | Microsoft Docs"
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
ms.assetid: dfb365c0-5ffc-4290-ab8b-bd347e0f0db9
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: ee5a2ae08df4649d5e551973539321164d4a8e59
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getvalidcompatibleframework-function"></a>GetValidCompatibleFramework – funkce
  Toto rozhraní API podporuje infrastrukturu rozhraní Office a není určena pro použití přímo z vašeho kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT WINAPI GetValidCompatibleFramework(  
    LPCWSTR lpwszCompatibleFrameworksXML,  
    BSTR* pbstrValidFrameworkTag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*lpwszCompatibleFrameworksXML*|Nepoužívejte.|  
|*pbstrValidFrameworkTag*|Nepoužívejte.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud funkci úspěšné, vrátí **S_OK**. Pokud se funkce nezdaří, vrátí kód chyby.  
  
  