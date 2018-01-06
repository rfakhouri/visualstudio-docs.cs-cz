---
title: "Cíle MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MSBuild, targets
ms.assetid: 8060b4d2-e4a9-48cf-a437-852649ceb417
caps.latest.revision: "26"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1055a11a428d477ef44645fbc85d3f281b523357
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-targets"></a>Cíle nástroje MSBuild
Cíle seskupíte úlohy v určitém pořadí a umožněte proces sestavení se promítnou do menších jednotek. Jeden cíl může například odstranit všechny soubory v adresáři výstup přípravy na sestavení, zatímco jiné zkompiluje vstupy pro projekt a umístí je do prázdného adresáře. Další informace o úlohách najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  
  
## <a name="declaring-targets-in-the-project-file"></a>Deklarování cíle v souboru projektu  
 Cíle jsou deklarované v souboru projektu s [cíl](../msbuild/target-element-msbuild.md) elementu. Například následující kód XML vytvoří cíl s názvem konstrukce, které pak zavolá Csc úloh s typem položky kompilace.  
  
```xml  
<Target Name="Construct">  
    <Csc Sources="@(Compile)" />  
</Target>  
```  
  
 Jako vlastnosti nástroje MSBuild můžete jej předefinovat cíle. Například  
  
```xml  
<Target Name="AfterBuild" >  
    <Message Text="First occurrence" />  
</Target>  
<Target Name="AfterBuild" >  
    <Message Text="Second occurrence" />  
</Target>  
```  
  
 Pokud se provede AfterBuild, zobrazí pouze "druhého výskytu textu".  
  
## <a name="target-build-order"></a>Pořadí sestavení cílů  
 Pokud vstup jeden cíl závisí na výstup jiný cíl, musejí být seřazeny cíle. Existuje několik způsobů, jak určit pořadí, ve které cíle spustit.  
  
-   Počáteční cíle  
  
-   Výchozí cíle  
  
-   První cíl  
  
-   Cílové závislosti  
  
-   `BeforeTargets`a `AfterTargets` (MSBuild 4.0)  
  
 Cíl se nikdy spouští dvakrát během jednoho sestavení, i když na něm závisí následující cíl v sestavení. Jakmile se spustí na cíl, jeho příspěvkem k sestavení je dokončena.  
  
 Pořadí sestavení, podrobnosti a další informace o cíli, najdete v části [cíl sestavení pořadí](../msbuild/target-build-order.md).  
  
## <a name="target-batching"></a>Dávkování cíle  
 Může mít na cílový element `Outputs` atribut, který určuje metadata v podobě % (Metadata). Pokud ano, spustí MSBuild cíl jednou pro každou hodnotu jedinečný metadata seskupení nebo "dávkování" položky, které mají tuto hodnotu metadat. Například  
  
```xml  
<ItemGroup>  
    <Reference Include="System.Core">  
      <RequiredTargetFramework>3.5</RequiredTargetFramework>  
    </Reference>  
    <Reference Include="System.Xml.Linq">  
      <RequiredTargetFramework>3.5</RequiredTargetFramework>  
    </Reference>  
    <Reference Include="Microsoft.CSharp">  
      <RequiredTargetFramework>4.0</RequiredTargetFramework>  
    </Reference>  
</ItemGroup>  
<Target Name="AfterBuild"  
    Outputs="%(Reference.RequiredTargetFramework)">  
    <Message Text="Reference:  
      @(Reference->'%(RequiredTargetFramework)')" />  
</Target>  
```  
  
 dávky odkaz položky podle jejich RequiredTargetFramework metadat. Výstup cíle vypadá takto:  
  
```  
Reference: 3.5;3.5  
Reference: 4.0  
```  
  
 Dávkování cíle se používá zřídka v skutečné sestavení. Dávkování úloh je dnes běžné. Další informace najdete v tématu [Batching](../msbuild/msbuild-batching.md).  
  
## <a name="incremental-builds"></a>Přírůstková sestavení  
 Přírůstková sestavení jsou sestavení, která jsou optimalizována tak, aby cílů se výstupní soubory, které jsou aktualizované s ohledem na jejich odpovídající vstupní soubory nebudou provedeny. Cílový element může mít oba `Inputs` a `Outputs` označující, co položky cíl jako vstup očekává atributů, a co položky, se vytváří jako výstup.  
  
 Pokud jsou všechny položky výstup aktuální, přeskočí MSBuild cíl, což významně zvyšuje rychlost sestavení. Jedná se přírůstkové sestavení cíle. Pokud jenom některé soubory jsou aktuální, provede MSBuild cíl bez aktuální položky. Tomu se říká částečné přírůstkové sestavení cíle. Další informace najdete v tématu [přírůstková sestavení](../msbuild/incremental-builds.md).  
  
## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Postupy: Použití stejného cíle ve více souborech projektu](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md)