---
title: Neutrální jazyky zdrojů pro lokalizaci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0bbddac532d242ce42330c955a797603b2d7e4a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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