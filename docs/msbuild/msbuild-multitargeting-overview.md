---
title: "Přehled cílení na více verzí nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eecbcd65-9fbc-4307-a321-46d3c3b79b12
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 573e88f1ebc3777f0ce6a6bfa048a9784d8f6488
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-multitargeting-overview"></a>Přehled cílení na více verzí nástroje MSBuild
Pomocí nástroje MSBuild při kompilaci aplikace ke spuštění na libovolném několik verzí rozhraní .NET Framework a na některý ze několik platforem systému. Můžete například kompilovat aplikaci spustit v rozhraní .NET Framework 2.0 na 32bitové platformě a zkompilovat stejnou aplikaci spustit v rozhraní .NET Framework 4.5 na 64bitové platformě.  
  
> [!IMPORTANT]
>  Bez ohledu název "cílení na více verzí" projektu, můžete vybrat pouze jeden framework a pouze jednu platformu najednou.  
  
 Toto jsou některé funkce nástroje MSBuild cílových:  
  
-   Můžete vyvíjet aplikace, která se zaměřuje na starší verzi rozhraní .NET Framework, například verze 2.0, 3.5 nebo 4.  
  
-   Můžete určit cílovou rozhraní než rozhraní .NET Framework, například rozhraní Silverlight.  
  
-   Můžete se zaměřit *profil framework*, což je předdefinovaná část cílové rozhraní.  
  
-   Pokud vydání aktualizace service pack pro aktuální verze rozhraní .NET Framework, může ho cíle.  
  
-   Cílení na MSBuild zaručuje, že aplikace používá jenom funkce, které jsou k dispozici v cílové verzi rozhraní a platformy.  
  
## <a name="target-framework-and-platform"></a>Cílová architektura a platforma  
 A *cílové rozhraní* je verze rozhraní .NET Framework projektu integrovaný ke spuštění, a *Cílová platforma* je platforma systému, která ke spuštění na sestavení projektu.  Například můžete chtít cílová aplikace rozhraní .NET Framework 2.0 na 32bitové platformě, který je kompatibilní s třídu procesoru 802 x 86 (x86) spouštět. Kombinace Cílová architektura a cílová platforma se označuje jako *cílový kontext*. Další informace najdete v tématu [Cílová architektura a cílová platforma](../msbuild/msbuild-target-framework-and-target-platform.md).  
  
## <a name="toolset-toolsversion"></a>Sada nástrojů (atribut ToolsVersion)  
 Sady nástrojů shromažďuje společně nástroje, úlohy a cíle, které se používají k vytvoření aplikace. Nástrojů obsahuje kompilátory například csc.exe a vbc.exe běžné souborů cíle (microsoft.common.targets), a běžné úlohy souborů (microsoft.common.tasks). Rozhraní 4.5 sadu nástrojů lze použít na cílové rozhraní .NET Framework verze 2.0, 3.0, 3.5, 4 a 4.5. Ale 2.0 nástrojů pouze slouží k cílové rozhraní .NET Framework verze 2.0. Další informace najdete v tématu [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).  
  
## <a name="reference-assemblies"></a>Odkaz na sestavení  
 Referenční sestavení, které jsou určené v sady nástrojů můžete navrhnout a sestavit aplikaci. Tyto referenční sestavení pouze povolit konkrétní cílový build, ale také na ty, které jsou kompatibilní s cílem omezit komponenty a funkce v prostředí Visual Studio IDE. Další informace najdete v tématu [řešení sestavení v době návrhu](../msbuild/resolving-assemblies-at-design-time.md)  
  
## <a name="configuring-targets-and-tasks"></a>Konfigurace cílů a úloh  
 Můžete nakonfigurovat cíle MSBuild a aby úlohy běžely out-of-process pomocí nástroje MSBuild tak, aby můžete určit cílovou kontextů, které se podstatně liší než ten, který běží na.  Například můžete určit cílovou aplikací rozhraní .NET Framework 2.0 32-bit, když vývojovém počítači běží na 64bitové platformě pomocí rozhraní .NET Framework 4.5. Další informace najdete v tématu [konfigurace cílů a úloh](../msbuild/configuring-targets-and-tasks.md).  
  
## <a name="troubleshooting"></a>Poradce při potížích  
 Pokud se pokusíte odkazování na sestavení, který není součástí cílový kontext, může dojít k chybám. Další informace o tyto chyby a co dělat, o nich najdete v tématu [řešení potíží s chybami cílení na rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).