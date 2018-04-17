---
title: 'Postupy: přírůstkové sestavování | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, incremental builds
- incremental builds
- MSBuild, building incrementally
ms.assetid: 8d82d7d8-a2f1-4df6-9d2f-80b9e0cb3ac3
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee9034d6dcd4b9484d727bd55111c998fc09a968
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-build-incrementally"></a>Postupy: Přírůstkové sestavování
Když vytvoříte nový projekt, je důležité, který dříve vytvořené součásti, které jsou stále aktuální nejsou znovu sestavit. Pokud jsou všechny cíle pokaždé, když, bude každé sestavení trvat dlouhou dobu pro dokončení. Chcete-li povolit přírůstkové sestavení (sestavení, ve kterém jsou zastaralé, tyto cíle, které nebyly byla vytvořená před nebo které cílí jenom se znovu sestavit), [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) můžete porovnat časová razítka vstupní soubory s časová razítka výstupních souborů a zjistěte, jestli se mají přeskočit, sestavení nebo částečně znovu sestavit cíl. Musí však být mapování 1: 1 mezi vstupy a výstupy. Transformace můžete povolit cíle k identifikaci této přímé mapování. Další informace o transformací najdete v tématu [transformuje](../msbuild/msbuild-transforms.md).  
  
## <a name="specifying-inputs-and-outputs"></a>Zadání vstupy a výstupy  
 Cíl může postupně vytvořeny, pokud jsou zadané vstupy a výstupy v souboru projektu.  
  
#### <a name="to-specify-inputs-and-outputs-for-a-target"></a>Chcete-li určit vstupy a výstupy pro cíl  
  
-   Použití `Inputs` a `Outputs` atributy `Target` elementu. Příklad:  
  
    ```xml  
    <Target Name="Build"  
        Inputs="@(CSFile)"  
        Outputs="hello.exe">  
    ```  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] můžete porovnat časová razítka vstupní soubory s časová razítka výstupních souborů a určení, zda přeskočit, sestavení nebo částečně znovu vytvořit cíl. V následujícím příkladu, pokud žádný soubor v `@(CSFile)` seznamu položek je novější než soubor hello.exe [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] spustí cíl; v opačném případě bude přeskočeno:  
  
```xml  
<Target Name="Build"   
    Inputs="@(CSFile)"   
    Outputs="hello.exe">  
  
    <Csc  
        Sources="@(CSFile)"   
        OutputAssembly="hello.exe"/>  
</Target>  
```  
  
 Když vstupy a výstupy jsou určené v cíl, každý výstup je možné namapovat pouze jeden vstup nebo může být žádné přímé mapování mezi vstupy a výstupy. V předchozím [Csc – úloha](../msbuild/csc-task.md), například výstupu hello.exe, nelze namapovat na žádný jeden vstup – závisí na všechny z nich.  
  
> [!NOTE]
>  Cíl, ve kterém není žádné přímé mapování mezi vstupy a výstupy vždy sestavení častěji, než ve kterém každý výstup je možné namapovat pouze jeden vstup vzhledem k tomu cíl [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] nelze určit, které výstupy je třeba znovu sestavit některých vstupních hodnot změnila-li .  
  
 Úlohy, ve kterých můžete identifikovat přímé mapování mezi výstupy a vstupy, například [LC – úloha](../msbuild/lc-task.md), jsou nejvhodnější pro přírůstkové sestavení, na rozdíl od úloh, jako `Csc` a [Vbc –](../msbuild/vbc-task.md), které produktu jednu výstupní sestavení z počet vstupů.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá projekt, který vytváří soubory nápovědy pro hypotetické systému nápovědy. Projekt funguje tak, že převodu zdrojové soubory s příponou .txt zprostředkující .content soubory, které pak spolu se soubory XML metadat k vytvoření souboru konečné .help používá systém nápovědy. Projekt využívá hypotetický následující úlohy:  
  
-   `GenerateContentFiles`: Převede soubory s příponou .txt .content soubory.  
  
-   `BuildHelp`: Kombinuje .content soubory a soubory metadat XML pro sestavení konečné .help souboru.  
  
 Transformace používá k vytvoření mapování 1: 1 mezi vstupy a výstupy v projektu `GenerateContentFiles` úloh. Další informace najdete v tématu [transformuje](../msbuild/msbuild-transforms.md). Navíc `Output` element je nastaven na hodnotu automaticky používat výstupy z `GenerateContentFiles` úloh jako vstupy pro `BuildHelp` úloh.  
  
 Tento projektový soubor obsahuje oba `Convert` a `Build` cíle. `GenerateContentFiles` a `BuildHelp` úlohy jsou umístěny v `Convert` a `Build` cílem v uvedeném pořadí tak, aby každý cíl se dají vytvářet postupně. Pomocí `Output` element, výstupy `GenerateContentFiles` úloh jsou umístěny v `ContentFile` seznamu položek, které můžete použít jako vstupy pro `BuildHelp` úloh. Pomocí `Output` element tímto způsobem automaticky poskytuje výstup z úloh jako vstupy pro jinou úlohu tak, aby nemáte jednotlivé položky seznamu nebo položky seznamů ručně v každé úloze.  
  
> [!NOTE]
>  I když `GenerateContentFiles` cíl můžete přírůstkové sestavování, všechny výstupy z tohoto cíle se vždy vyžadují jako vstupy pro `BuildHelp` cíl. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] všechny výstupy z jeden cíl automaticky poskytuje jako vstupy pro jiný cíl při použití `Output` elementu.  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <TXTFile Include="*.txt"/>  
        <XMLFiles Include="\metadata\*.xml"/>  
    </ItemGroup>  
  
    <Target Name = "Convert"  
        Inputs="@(TXTFile)"  
        Outputs="@(TXTFile->'%(Filename).content')">  
  
        <GenerateContentFiles  
            Sources = "@(TXTFile)">  
            <Output TaskParameter = "OutputContentFiles"  
                ItemName = "ContentFiles"/>  
        </GenerateContentFiles>  
    </Target>  
  
    <Target Name = "Build" DependsOnTargets = "Convert"  
        Inputs="@(ContentFiles);@(XMLFiles)"  
        Outputs="$(MSBuildProjectName).help">  
  
        <BuildHelp  
            ContentFiles = "@(ContentFiles)"  
            MetadataFiles = "@(XMLFiles)"  
            OutputFileName = "$(MSBuildProjectName).help"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Cíle](../msbuild/msbuild-targets.md)   
 [Target – Element (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Transformace](../msbuild/msbuild-transforms.md)   
 [CSC – úloha](../msbuild/csc-task.md)   
 [Vbc – úloha](../msbuild/vbc-task.md)
