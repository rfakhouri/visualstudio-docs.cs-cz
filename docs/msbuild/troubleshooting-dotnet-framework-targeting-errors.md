---
title: Řešení potíží s cílením na rozhraní .NET Framework | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.FrameworkTargetingErrors
- MSBuild.ResolveAssemblyReference.FailedToResolveReferenceBecausePrimaryAssemblyInExclusionList
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], .NET Framework Client Profile
- multi-targeting
- multitargeting
- .NET Framework Client Profile
ms.assetid: 830e3e45-9a93-4279-a249-75b84599aefb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 465952fa41eab7d112ca839be2940cded3d69b33
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744629"
---
# <a name="troubleshoot-net-framework-targeting-errors"></a>Řešení potíží s cílením na rozhraní .NET Framework
Toto téma popisuje chyby nástroje MSBuild, kterým by mohlo dojít z důvodu odkazu problémy a jak můžete tyto chyby vyřešili.

## <a name="you-have-referenced-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Mít odkazuje na projekt nebo sestavení, který cílí na jinou verzi rozhraní .NET Framework
 Můžete vytvářet aplikace, které odkazují na projekty nebo sestavení, které cílí různé verze rozhraní .NET Framework. Můžete například vytvořit aplikaci, která cílí na profil klienta pro rozhraní .NET Framework 4, ale odkazuje na sestavení, které cílí na rozhraní .NET Framework 2.0. Pokud vytvoříte projekt, který se zaměřuje na starší verzi rozhraní .NET Framework, můžete v daném projektu na projekt nebo sestavení, které cílí na profil klienta rozhraní .NET Framework 4 nebo .NET Framework 4, samotný nemůžete nastavit odkaz. Chcete-li chybu vyřešit, ujistěte se, že vaše aplikace cílí na profil, nebo profily, které jsou kompatibilní s profilem, která je cílem projekty nebo sestavení, na které odkazuje vaše aplikace.

## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework"></a>Znovu jste zaměřili projekt na jinou verzi rozhraní .NET Framework
 Pokud změníte cílovou verzi rozhraní .NET Framework pro vaši aplikaci, Visual Studio změní některé z odkazů, ale možná budete muset ručně aktualizovat některé odkazy. Například některé z výše uvedených chyb může dojít, pokud změníte aplikace k cíli [!INCLUDE[net_v35SP1_long](../msbuild/includes/net_v35sp1_long_md.md)] a že aplikace má nastavení, které jsou závislé na profil klienta pro rozhraní .NET Framework 4 nebo prostředky.

 Pokud chcete obejít nastavení aplikace, otevřete **Průzkumníka řešení**, zvolte **zobrazit všechny soubory**a pak upravte *app.config* souboru v editoru XML sady Visual Studio. Změňte verzi v nastavení tak, aby odpovídaly příslušnou verzi rozhraní .NET Framework. Například můžete změnit nastavení verze z 4.0.0.0 na 2.0.0.0. Podobně pro aplikaci, která se má přidat prostředky, otevřete **Průzkumníka řešení**, zvolte **zobrazit všechny soubory** tlačítko, rozbalte **Můj projekt** (Visual Basic) nebo **Vlastnosti** (C#) a pak upravte *Resources.resx* souboru v editoru XML sady Visual Studio. Změňte nastavení verze 2.0.0.0 z 4.0.0.0.

 Pokud aplikace obsahuje prostředky, jako jsou ikony nebo rastrové obrázky nebo nastavení, jako je například připojovací řetězce dat, můžete také vyřešit chybu tak, že odeberete všechny položky na **nastavení** stránku **Návrháře projektu**a poté znovu přidejte požadovaná nastavení.

## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework-and-references-do-not-resolve"></a>Znovu jste zaměřili projekt na jinou verzi rozhraní .NET Framework a odkazy nepřekládat
 Výsledkem změny cílení projektu na jinou verzi rozhraní .NET Framework nemusí v některých případech správně vyřešit vaše odkazy. Explicitní plně kvalifikované odkazy na sestavení často způsobit potíže, ale ho mohli vyřešit odkazy, které nelze vyřešit odstraněním a jejich přidání do projektu. Jako alternativu můžete upravit soubor projektu a nahradit odkazy. Nejdřív odeberte odkazy na následující formu:

```xml
<Reference Include="System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089, processorArchitecture=MSIL" />
```

 Potom můžete nahradit je jednoduchý formulář:

```xml
<Reference Include="System.ServiceModel" />
```

> [!NOTE]
> Po zavření a znovu otevřít projekt, měli byste také znovu vytvořit jej pro zajištění správně přeložit všechny odkazy.

## <a name="see-also"></a>Viz také:

- [Postupy: Cílení na určitou verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md)
- [Profil klienta rozhraní .NET framework](/dotnet/framework/deployment/client-profile)
- [Přehled cílení na rozhraní Framework](../ide/visual-studio-multi-targeting-overview.md)
- [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)