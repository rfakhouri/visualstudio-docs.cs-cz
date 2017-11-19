---
title: "Řešení potíží s cílením rozhraní .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "29"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: b35c3b87a1526f0453e1385c92c5ecefc5ec55da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-net-framework-targeting-errors"></a>Řešení potíží s cílením na rozhraní .NET Framework
Toto téma popisuje chyby nástroje MSBuild, kterým by mohlo dojít z důvodu odkaz problémy a jak můžete vyřešit tyto chyby.  
  
## <a name="you-have-referenced-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Mít odkazuje na projekt nebo sestavení, která je cílena jinou verzi rozhraní .NET Framework  
 Můžete vytvářet aplikace, které odkazují na projekty nebo sestavení, které cílí různé verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Například můžete vytvořit profil klienta pro aplikaci [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] ale odkazuje na sestavení, která je cílena rozhraní .NET Framework 2.0. Ale pokud vytvoříte projekt, která cílí starší verze systému [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], sadu odkaz nelze v tento projekt na projekt nebo sestavení, které profil klienta pro [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] nebo [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] sám sebe. Vyřešit chyby, ujistěte se, že vaše aplikace zaměřuje profil, nebo profily, které jsou kompatibilní s profilem, který je cílem projekty nebo sestavení, které vaše aplikace odkazuje.  
  
## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework"></a>Mít znovu cílové projekt, který má jinou verzi rozhraní .NET Framework  
 Pokud změníte cílovou verzi sady [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pro aplikaci Visual Studio změní některé odkazy, ale možná budete muset ručně aktualizovat některé odkazy. Například některé z výše uvedených chyb může dojít, pokud změníte aplikace k cíli [!INCLUDE[net_v35SP1_long](../msbuild/includes/net_v35sp1_long_md.md)] a že má prostředky nebo nastavení, které jsou závislé na profil klienta pro aplikaci [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)].  
  
 Nastavení aplikace obejít, otevřete **Průzkumníku řešení**, zvolte **zobrazit všechny soubory**a potom upravte soubor app.config v editoru XML sady Visual Studio. Verzi v nastavení tak, aby odpovídaly příslušnou verzi rozhraní .NET Framework změňte. Například můžete změnit nastavení verze z 4.0.0.0 na 2.0.0.0. Podobně pro aplikaci, která přidala prostředky, otevřete **Průzkumníku řešení**, vyberte **zobrazit všechny soubory** tlačítko, rozbalte položku **Moje projektu** (Visual Basic) nebo **Vlastnosti** (C#) a pak upravte soubor Resources.resx v editoru XML sady Visual Studio. Změňte nastavení verze z 4.0.0.0 na 2.0.0.0.  
  
 Pokud aplikace obsahuje prostředky, třeba jako ikony nebo bitmapy nebo nastavení, jako například datové připojovací řetězce, můžete také vyřešit chyba odebrat všechny položky v **nastavení** stránky **Návrhář projektu**a potom znovu přidat požadovaná nastavení.  
  
## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework-and-references-do-not-resolve"></a>Jste znovu zaměřili projekt, který má jinou verzi rozhraní .NET Framework a odkazy nelze vyřešit.  
 Pokud jste změnit cílový projekt, který má jinou verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], vaše odkazy nemusí správně přeložit v některých případech. Explicitní plně kvalifikované odkazy na sestavení často příčinou tohoto problému, ale abyste ho mohli vyřešit odkazy, které nelze vyřešit odstraněním a jejich přidáním do projektu. Jako alternativu můžete upravit soubor projektu nahradit odkazy. Nejprve odeberte odkazy v následujícím formátu:  
  
```xml  
<Reference Include="System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089, processorArchitecture=MSIL" />  
```  
  
 Potom můžete nahradit je jednoduchý formulář:  
  
```xml  
<Reference Include="System.ServiceModel" />  
```  
  
> [!NOTE]
>  Když zavřete a znovu otevřít projekt, měli byste také znovu vytvořit k zajištění správně vyřešit všechny odkazy.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [Profil klienta rozhraní .NET framework](/dotnet/framework/deployment/client-profile)   
 [Cílení na konkrétní rozhraní .NET Framework verze](../ide/targeting-a-specific-dotnet-framework-version.md)   
 [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)