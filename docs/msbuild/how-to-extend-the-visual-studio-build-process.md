---
title: 'Postupy: rozšíření procesu sestavení sady Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, overriding predefined targets
- MSBuild, overriding DependsOn properties
- MSBuild, extending Visual Studio builds
- MSBuild, DependsOn properties
ms.assetid: cb077613-4a59-41b7-96ec-d8516689163c
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2799fff68fbbe1ee19e98364b83dd56eb375441f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-extend-the-visual-studio-build-process"></a>Postupy: Rozšíření procesu sestavení sady Visual Studio
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Procesu sestavení je definována řadu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] .TARGETS – soubory, které jsou importovány do souboru projektu. Mezi tyto importované soubory Microsoft.Common.targets, lze rozšířit a umožní vám při spouštění vlastní úlohy na několika místech v procesu sestavení. Toto téma popisuje dvě metody, které můžete použít k rozšíření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proces sestavení:  
  
-   Přepsání konkrétní předdefinovaných cílů, které jsou definované v Microsoft.Common.targets.  
  
-   Přepsání vlastností "DependsOn" definované v Microsoft.Common.targets.  
  
## <a name="overriding-predefined-targets"></a>Přepsání předdefinovaných cílů  
 Soubor Microsoft.Common.targets obsahuje sadu předdefinovaných prázdný cílů, které se nazývají před a po některé z hlavních cílů v procesu sestavení. Například [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] volání `BeforeBuild` cíl před hlavním `CoreBuild` cíl a `AfterBuild` cíle po `CoreBuild` cíl. Ve výchozím nastavení prázdný cílů v Microsoft.Common.targets nedělat nic, ale jejich výchozí chování můžete přepsat definováním cílů, které chcete v souboru projektu, který importuje Microsoft.Common.targets. Díky tomu můžete použít [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy, čímž získáte větší kontrolu nad tímto procesem sestavení.  
  
#### <a name="to-override-a-predefined-target"></a>K přepsání předdefinovaných cíl  
  
1.  Zjistit předdefinované cíl v Microsoft.Common.targets, kterou chcete přepsat. Najdete v následující tabulce pro úplný seznam cílů, které můžete bezpečně přepsat.  
  
2.  Zadejte cíl nebo cílů na konci souboru projektu se bezprostředně před `</Project>` značky. Příklad:  
  
    ```xml  
    <Project>  
        ...  
        <Target Name="BeforeBuild">  
            <!-- Insert tasks to run before build here -->  
        </Target>  
        <Target Name="AfterBuild">  
            <!-- Insert tasks to run after build here -->  
        </Target>  
    </Project>  
    ```  
  
3.  Vytvoření souboru projektu.  
  
 V následující tabulce jsou všechny cíle v Microsoft.Common.targets, které můžete bezpečně přepsat.  
  
|Cílový název|Popis|  
|-----------------|-----------------|  
|`BeforeCompile`, `AfterCompile`|Úlohy vložit do jednoho z těchto cílů spustit před nebo po dokončení základní kompilace. Většina přizpůsobení se provádějí v jednom z těchto dvou cíle.|  
|`BeforeBuild`, `AfterBuild`|Vložit v jednom z těchto cílů úlohy se spustí před nebo po všem ostatním v buildu. **Poznámka:** `BeforeBuild` a `AfterBuild` cíle jsou již definováni v komentářích na konci většina souborů projektu. To umožňuje snadno přidat před a po sestavení události do souboru projektu.|  
|`BeforeRebuild`, `AfterRebuild`|Úkoly vložit v jednom z těchto cílů spustit před nebo po základní znovu sestavit funkce je volána. Pořadí provádění cílů v Microsoft.Common.targets je: `BeforeRebuild`, `Clean`, `Build`a potom `AfterRebuild`.|  
|`BeforeClean`, `AfterClean`|Spuštění úlohy v jedné z těchto cílů vložit před nebo po základní vyčištění funkce volána.|  
|`BeforePublish`, `AfterPublish`|Úkoly vložit v jednom z těchto cílů spustit před nebo po publikování základní funkce je volána.|  
|`BeforeResolveReference`, `AfterResolveReferences`|Vložit v jednom z těchto cílů úlohy spustit před nebo po odkazy na sestavení jsou vyřešeny.|  
|`BeforeResGen`, `AfterResGen`|Úlohy vložit do jednoho z těchto cílů spustit před nebo po vygenerování prostředky.|  
  
## <a name="overriding-dependson-properties"></a>Přepsání vlastností "DependsOn"  
 Přepsání předdefinovaných cílů je snadný způsob, jak rozšíření procesu sestavení, ale protože [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vyhodnotí definice cíle postupně, neexistuje žádný způsob, jak zabránit jiného projektu, který umožňuje importovat projekt z přepsání cíle už máte mít přepsat. Tak například poslední `AfterBuild` cíl v souboru projektu po další projekty byly naimportovány, bude ten, který se používá během sestavení.  
  
 Můžete chránit před neúmyslným přepsání cílů přepsáním "DependsOn" vlastnosti, které se používají v `DependsOnTargets` atributy v celém souboru Microsoft.Common.targets. Například `Build` cíl obsahuje `DependsOnTargets` hodnotu atributu `"$(BuildDependsOn)"`. Vezměte v úvahu:  
  
```xml  
<Target Name="Build" DependsOnTargets="$(BuildDependsOn)"/>  
```  
  
 Tato část XML znamená, že před `Build` cíl můžete spustit, všechny cíle zadaný v `BuildDependsOn` vlastnost nejdřív se musí spustit. `BuildDependsOn` Vlastnost je definován jako:  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        BeforeBuild;  
        CoreBuild;  
        AfterBuild  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 Hodnota této vlastnosti můžete přepsat pomocí deklarace jinou vlastnost s názvem `BuildDependsOn` na konci souboru projektu. Zahrnutím předchozí `BuildDependsOn` vlastnost v nové vlastnosti, můžete přidat nového cíle na začátek a konec seznamu cíl. Příklad:  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        MyCustomTarget1;  
        $(BuildDependsOn);  
        MyCustomTarget2  
    </BuildDependsOn>  
</PropertyGroup>  
  
<Target Name="MyCustomTarget1">  
    <Message Text="Running MyCustomTarget1..."/>  
</Target>  
<Target Name="MyCustomTarget2">  
    <Message Text="Running MyCustomTarget2..."/>  
</Target>  
```  
  
 Projekty, které importovat soubory projektu, můžete přepsat tyto vlastnosti bez přepsal přizpůsobení, které jste provedli.  
  
#### <a name="to-override-a-dependson-property"></a>Chcete-li přepsat vlastnost "DependsOn"  
  
1.  Identifikujte předdefinovaná vlastnost "DependsOn" v Microsoft.Common.targets, kterou chcete přepsat. Najdete v následující tabulce pro seznam vlastností běžně přepsaného "DependsOn".  
  
2.  Zadejte jinou instanci vlastnost nebo vlastnosti na konci souboru projektu. Třeba zahrnout vlastnost původní `$(BuildDependsOn)`, v nové vlastnosti.  
  
3.  Definujte vlastní cíle před nebo po definici vlastnosti.  
  
4.  Vytvoření souboru projektu.  
  
### <a name="commonly-overridden-dependson-properties"></a>Běžně přepisované vlastnosti "DependsOn"  
  
|Název vlastnosti|Popis|  
|-------------------|-----------------|  
|`BuildDependsOn`|Vlastnost, která má přepsat, pokud chcete vložit vlastní cíle před nebo po dokončení procesu celý sestavení.|  
|`CleanDependsOn`|Vlastnost, která má přepsat, pokud chcete proces vyčištění výstup z vaše vlastní sestavení.|  
|`CompileDependsOn`|Vlastnost, která má přepsat, pokud chcete vložit vlastní procesy před nebo po kompilační krok.|  
  
## <a name="see-also"></a>Viz také  
 [Integrace sady Visual Studio](../msbuild/visual-studio-integration-msbuild.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [. Soubory cíle](../msbuild/msbuild-dot-targets-files.md)