---
title: Neutrální jazyky zdrojů pro lokalizaci | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: da39ed9373daaa1dbef21ad36931ce97ea1f1e1b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62558265"
---
# <a name="neutral-resources-languages-for-localization"></a>Neutrální jazyky zdrojů pro lokalizaci
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:System.Resources.NeutralResourcesLanguageAttribute> Třída určuje jazykovou verzi prostředků zahrnuté v hlavním sestavení. Tento atribut se používá jako vylepšení výkonu, tak, aby <xref:System.Resources.ResourceManager> objekt neprohledává za prostředky, které jsou zahrnuty v hlavním sestavení.  
  
 Následující kód ukazuje, jak nastavit jazyk neutrální prostředky. Kód je možné použít ve skriptu sestavení nebo v souboru AssemblyInfo.vb nebo AssemblyInfo.cs.  
  
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
 [Představení mezinárodních aplikací založených na rozhraní .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [Hierarchická organizace zdrojů pro lokalizaci](../ide/hierarchical-organization-of-resources-for-localization.md)   
 [Lokalizace aplikací](../ide/localizing-applications.md)   
 [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)
