---
title: MSBuild Cílová architektura a cílová platforma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: df6517c5-edd6-4cc4-97ad-b3cdfc78e799
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93eff2375e9b1cab043a30acaf5ebec31ba8e89f
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="msbuild-target-framework-and-target-platform"></a>Cílová architektura a cílová platforma nástroje MSBuild
Projekt se dají vytvářet ke spuštění na *cílové rozhraní*, což je konkrétní verzi rozhraní .NET Framework a *Cílová platforma*, což je architektura určitého softwaru.  Například můžete určit cílovou aplikaci spustit v rozhraní .NET Framework 2.0 na 32bitové platformě, který je kompatibilní s třídu procesoru 802 x 86 ("x86"). Kombinace Cílová architektura a cílová platforma se označuje jako *cílový kontext*.  
  
## <a name="target-framework-and-profile"></a>Cílová architektura a profilu  
 Cílové rozhraní je konkrétní verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] vytvořené pro spouštění v projektu. Specifikace cílového prostředí není nutná, protože umožňuje funkce kompilátoru a odkazy na sestavení, které jsou výhradně pro tuto verzi rozhraní framework.  
  
 V současné době jsou k dispozici pro použití následující verze rozhraní .NET Framework:  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 2.0 (zahrnutá v sadě Visual Studio 2005)  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 3.0 (součástí [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)])  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 3.5 (součástí [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)])  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.5.2  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.6 (součástí [!INCLUDE[vs_dev14](../misc/includes/vs_dev14_md.md)])  

-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.6.1  

-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.6.2  

-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.7  

-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4.7.1  
  
 Verze rozhraní .NET Framework se liší od sebe navzájem v seznamu sestavení, že každý zpřístupní odkazovat. Nelze například vytvářet aplikace Windows Presentation Foundation (WPF), pokud je cílem vašeho projektu je .NET Framework verze 3.0 nebo vyšší.  
  
 Cílovém Frameworku, který je uveden v `TargetFrameworkVersion` vlastnost v souboru projektu. Pomocí stránky vlastností projektu v sadě Visual Studio integrované vývojové prostředí (IDE) můžete změnit cílový framework projektu. Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md). Dostupné hodnoty pro `TargetFrameworkVersion` jsou `v2.0`, `v3.0`, `v3.5`, `v4.5.2`, `v4.6`, `v.4.6.1`, `v4.6.2`, `4.7`, a `4.7.1`.  
  
```xml  
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>  
```  
  
 A *cíle profil* je podmnožinou cílové rozhraní. Profil klienta rozhraní .NET Framework 4 například nezahrnuje odkazy na sestavení nástroje MSBuild.  
  
 Je profil cílového je uveden v `TargetFrameworkProfile` vlastnost v souboru projektu. Je profil cílového můžete změnit pomocí ovládacího prvku cílové rozhraní na stránkách vlastností projektu v prostředí IDE. Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
```xml  
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>  
<TargetFrameworkProfile>Client</TargetFrameworkProfile>  
```  
  
## <a name="target-platform"></a>Cílová platforma  
 A *platformy* je kombinace hardwaru a softwaru, který definuje konkrétní běhového prostředí. Například  
  
-   `x86` označí 32bitový operační systém Windows, který běží na procesor Intel 80 x 86 nebo jeho ekvivalent.  

-   `x64` označí 64-bit operačního systému Windows, který běží na procesor Intel x64 nebo ekvivalentní.
  
-   `Xbox` označí platformou Microsoft Xbox 360.  
  
 A *Cílová platforma* je konkrétní platformy, na které ke spuštění na sestavení projektu. Cílové platformy je uveden v `PlatformTarget` sestavení vlastnost v souboru projektu. Cílové platformy můžete změnit pomocí stránky vlastností projektu nebo **nástroje Configuration Manager** v prostředí IDE.  
  
```xml  
<PropertyGroup>  
   <PlatformTarget>x86</PlatformTarget>  
</PropertyGroup>  
  
```  
  
 A *konfigurace cílového* je podmnožinou cílové platformy. Například `x86``Debug` konfigurace nezahrnuje většinu kódu optimalizace. Konfigurace cílového je uveden v `Configuration` sestavení vlastnost v souboru projektu. Konfigurace cílového můžete změnit pomocí stránky vlastností projektu nebo **nástroje Configuration Manager**.  
  
```xml  
<PropertyGroup>  
   <PlatformTarget>x86</PlatformTarget>  
   <Configuration>Debug</Configuration>  
<PropertyGroup>  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)