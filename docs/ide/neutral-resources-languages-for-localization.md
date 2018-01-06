---
title: "Neutrální jazyky zdrojů pro lokalizaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 755be1dac065f2a8cd9ee769557f0a48e72ce03f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="neutral-resources-languages-for-localization"></a>Neutrální jazyky zdrojů pro lokalizaci
<xref:System.Resources.NeutralResourcesLanguageAttribute> Třída určuje jazykovou verzi zdrojů, součástí hlavní sestavení. Tento atribut slouží jako vylepšení výkonu, tak, aby <xref:System.Resources.ResourceManager> objekt nehledá prostředky, které jsou součástí hlavní sestavení.  
  
 Následující kód ukazuje, jak nastavit jazyk neutrální prostředky. Kód mohou být umístěny ve skriptu sestavení nebo v souboru AssemblyInfo.vb nebo AssemblyInfo.cs.  
  
```vb  
' Set neutral resources language for assembly.  
<Assembly: NeutralResourcesLanguageAttribute("en")>  
  
```  
  
```csharp  
// Set neutral resources language for assembly.  
[assembly: NeutralResourcesLanguageAttribute("en")]  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Resources.ResourceManager>   
 [Úvod do mezinárodních aplikací založených na rozhraní .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [Hierarchická organizace zdrojů pro lokalizaci](../ide/hierarchical-organization-of-resources-for-localization.md)   
 [Lokalizace aplikací](../ide/localizing-applications.md)   
 [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)