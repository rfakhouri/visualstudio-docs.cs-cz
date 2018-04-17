---
title: Cíle MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, targets
ms.assetid: 8060b4d2-e4a9-48cf-a437-852649ceb417
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9ab9a367352ddf7980394f8cb87823f7d163ed1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
  
-   `BeforeTargets` a `AfterTargets` (MSBuild 4.0)  
  
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