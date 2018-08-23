---
title: Čísla verzí pro hlavní a lokalizované satelitní sestavení | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- satellite assemblies, version numbers
- SatelliteContractVersionAttribute
- version numbers, assemblies
- assemblies [Visual Studio], version numbers
- versioning, assemblies
ms.assetid: 5489aea1-57b4-4561-9bb4-24d490269602
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 041c23c56b99ec1abba43081d6422f0f05d05e60
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667347"
---
# <a name="version-numbers-for-main-and-localized-satellite-assemblies"></a>Čísla verzí pro hlavní a lokalizované satelitní sestavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:System.Resources.SatelliteContractVersionAttribute> Třída poskytuje podporu správy verzí pro hlavní sestavení, které používá lokalizované prostředky prostřednictvím resource Manageru. Použití <xref:System.Resources.SatelliteContractVersionAttribute> k aplikaci hlavní sestavení vám umožní aktualizovat a znovu nasadit sestavení bez aktualizace jeho satelitních sestavení. Například můžete použít <xref:System.Resources.SatelliteContractVersionAttribute> třídy s aktualizací service pack, který nemá zavést nové prostředky bez znovu sestavovat a nasazovat satelitních sestavení. Pro lokalizované prostředky k dispozici, musí odpovídat verze satelitního kontraktu sestavení hlavní <xref:System.Reflection.AssemblyVersionAttribute> třídy satelitních sestavení. Musíte zadat číslo přesnou verzi v <xref:System.Resources.SatelliteContractVersionAttribute>; zástupné znaky, jako "*" nejsou povoleny. Další informace najdete v tématu [načítání prostředků](http://msdn.microsoft.com/library/eca16922-1c46-4f68-aefe-e7a12283641f).  
  
## <a name="updating-assemblies"></a>Aktualizuje se sestavení  
 <xref:System.Resources.SatelliteContractVersionAttribute> Třída umožňuje aktualizovat bez nutnosti aktualizovat satelitní sestavení do hlavního sestavení nebo naopak. Když se aktualizuje hlavní sestavení, číslo verze sestavení se změní. Pokud chcete pokračovat v používání existujícího satelitní sestavení, změňte číslo verze hlavní sestavení, ale ponechat stejné číslo verze satelitního kontraktu. Například v první verzi může být vaše hlavní sestavení verze 1.0.0.0. Verze satelitního kontraktu sestavení verzi satelitního sestavení také to 1.0.0.0. Pokud je potřeba aktualizovat vaše hlavní sestavení pro aktualizace service pack, můžete změnit verzi sestavení 1.0.0.1, při zachování verze satelitního kontraktu a verze pro satelitní sestavení jako 1.0.0.0.  
  
 Pokud je potřeba aktualizovat satelitní sestavení, ale není hlavním sestavení, můžete změnit <xref:System.Reflection.AssemblyVersionAttribute> satelitní sestavení. Spolu se satelitním sestavením bude mít k odeslání zásady sestavení, která uvádí, že vaše nové satelitní sestavení je kompatibilní s původní satelitní sestavení. Další informace o zásadách najdete v tématu [jak modul Runtime vyhledává sestavení](http://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34).  
  
 Následující kód ukazuje, jak nastavit verze satelitního kontraktu. Kód je možné použít ve skriptu sestavení nebo v souboru AssemblyInfo.vb nebo AssemblyInfo.cs.  
  
```vb  
<Assembly: SatelliteContractVersionAttribute("4.3.2.1")>  
  
```  
  
```csharp  
[assembly: SatelliteContractVersionAttribute("4.3.2.1")]  
```  
  
## <a name="see-also"></a>Viz také  
 [Jak běhové prostředí vyhledává sestavení](http://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34)   
 [Nastavování atributů sestavení](http://msdn.microsoft.com/library/36a98a81-b5b5-4c19-912a-11f91eff7f4e)   
 [Zabezpečení a lokalizovaná satelitní sestavení](../ide/security-and-localized-satellite-assemblies.md)   
 [Lokalizace aplikací](../ide/localizing-applications.md)   
 [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)

