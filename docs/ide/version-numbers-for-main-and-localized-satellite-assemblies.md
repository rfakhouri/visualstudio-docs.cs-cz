---
title: Čísla verzí pro hlavní a lokalizované satelitní sestavení
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- satellite assemblies, version numbers
- SatelliteContractVersionAttribute
- version numbers, assemblies
- assemblies [Visual Studio], version numbers
- versioning, assemblies
ms.assetid: 5489aea1-57b4-4561-9bb4-24d490269602
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4544a1d29cede7922f88c3a1aa7ae053b0b723cb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="version-numbers-for-main-and-localized-satellite-assemblies"></a>Čísla verzí pro hlavní a lokalizované satelitní sestavení
<xref:System.Resources.SatelliteContractVersionAttribute> Třída poskytuje podporu správy verzí pro hlavní sestavení, který používá místní zdroje prostřednictvím Resource Manager. Použití <xref:System.Resources.SatelliteContractVersionAttribute> k aplikaci hlavní sestavení vám umožní aktualizovat a znovu nasaďte sestavení bez aktualizace jeho satelitních sestavení. Například můžete použít <xref:System.Resources.SatelliteContractVersionAttribute> třídy s aktualizací service pack, která není zavést nové prostředky bez znovu sestavit a znovu nasazovat satelitní sestavení. Pro vaše lokalizované prostředky k dispozici, musí odpovídat verzi satelitní kontrakt hlavní sestavení <xref:System.Reflection.AssemblyVersionAttribute> třída satelitních sestavení. Zadejte číslo přesnou verzi v <xref:System.Resources.SatelliteContractVersionAttribute>; zástupné znaky, jako například "*" nejsou povoleny. Další informace najdete v tématu [načítání prostředků](/dotnet/framework/resources/retrieving-resources-in-desktop-apps).

## <a name="updating-assemblies"></a>Aktualizace sestavení
 <xref:System.Resources.SatelliteContractVersionAttribute> Třída umožňuje aktualizovat hlavní sestavení bez nutnosti aktualizovat satelitní sestavení, nebo naopak. Při aktualizaci hlavní sestavení se změní jeho číslo verze sestavení. Pokud chcete dál používat existující satelitní sestavení, změnit číslo verze sestavení hlavní ale číslo verze smlouvy satelitní zůstanou stejná. Například v první verzi může být vaší hlavní sestavení verzi 1.0.0.0. Satelitní kontrakt verze a verze sestavení satelitní sestavení bude také 1.0.0.0. Pokud je potřeba aktualizovat vaše hlavní sestavení pro aktualizace service pack, můžete změnit verze sestavení 1.0.0.1, při zachování satelitní kontrakt verze a verze pro satelitní sestavení jako 1.0.0.0.

 Pokud je potřeba aktualizovat satelitní sestavení, ale není vaší hlavní sestavení, můžete změnit <xref:System.Reflection.AssemblyVersionAttribute> satelitní sestavení. Společně s satelitní sestavení budete mít k dodání sestavení zásady, která uvádí, že nové satelitní sestavení je kompatibilní s vaší staré satelitní sestavení. Další informace o zásadách najdete v tématu [jak modul Runtime vyhledává sestavení](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).

 Následující kód ukazuje, jak nastavit verze smlouvy satelit. Kód mohou být umístěny ve skriptu sestavení nebo v souboru AssemblyInfo.vb nebo AssemblyInfo.cs.

```vb
<Assembly: SatelliteContractVersionAttribute("4.3.2.1")>

```

```csharp
[assembly: SatelliteContractVersionAttribute("4.3.2.1")]
```

## <a name="see-also"></a>Viz také

- [Jak běhové prostředí vyhledává sestavení](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [Nastavování atributů sestavení](/dotnet/framework/app-domains/set-assembly-attributes)
- [Zabezpečení a lokalizovaná satelitní sestavení](../ide/security-and-localized-satellite-assemblies.md)
- [Lokalizace aplikací](../ide/localizing-applications.md)
- [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)