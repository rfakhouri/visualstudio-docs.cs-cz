---
title: Přepsání nastavení parametru ToolsVersion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, overriding ToolsVersion setting
- MSBuild, building solutions with
ms.assetid: ccd42c07-0fb6-4e8b-9ebb-a6a6db18aa2e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25d4254e8f45da6a476207740cfa28e1db2253e4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="overriding-toolsversion-settings"></a>Přepsání nastavení parametru ToolsVersion
Můžete změnit sada nástrojů pro projekty a řešení v jednom ze tří způsobů:  
  
1.  pomocí `/ToolsVersion` přepínače (nebo `/tv`, pro zkrácení) při vytváření projekt nebo řešení z příkazového řádku  
  
2.  nastavením `ToolsVersion` parametr na úlohy nástroje MSBuild  
  
3.  nastavením `$(ProjectToolsVersion)` vlastnost na projektu v rámci řešení. To umožňuje vytváření projektu v řešení s verzí sady nástrojů, která se liší od jiné projekty.  
  
## <a name="override-the-toolsversion-settings-of-projects-and-solutions-on-command-line-builds"></a>Přepsání nastavení parametru ToolsVersion projekty a řešení na příkazovém řádku sestavení  
 I když k parametru ToolsVersion zadaný v souboru projektu obvykle sestavení projektů sady Visual Studio, můžete použít `/ToolsVersion` (nebo `/tv`) přepnout na příkazovém řádku přepsat tuto hodnotu a všechny projekty a jejich projekt na projekt sestavení závislosti pomocí různých nástrojů. Příklad:  
  
```  
msbuild.exe someproj.proj /tv:12.0 /p:Configuration=Debug  
```  
  
 V tomto příkladu jsou sestaveny všechny projekty, pomocí parametru ToolsVersion 12.0. (Ale najdete v části "Pořadí priorit" dál v tomto tématu.)  
  
 Při použití `/tv` přepnout na příkazovém řádku, můžete volitelně použít `$(ProjectToolsVersion)` vlastnost v jednotlivých projektů pro sestavení je s jinou hodnotou parametru ToolsVersion než ostatní projekty v řešení.  
  
## <a name="override-the-toolsversion-settings-using-the-toolsversion-parameter-of-the-msbuild-task"></a>Přepsání nastavení ToolsVersion pomocí parametru ToolsVersion úlohy nástroje MSBuild  
 Úlohy nástroje MSBuild je hlavním prostředkem pro jeden projekt k jiné sestavení. Pokud chcete povolit úlohy nástroje MSBuild pro vytvoření projektu s jiný atribut ToolsVersion než verze zadaná v projektu, poskytuje parametru nepovinná úloha s názvem `ToolsVersion`. Následující příklad ukazuje, jak používat tento parametr:  
  
1.  Vytvoření souboru, který je pojmenován `projectA.proj` a který obsahuje následující kód:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go" >   
            <Message Text="projectA.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
  
            <MSBuild Projects="projectB.proj"  
                ToolsVersion="2.0"  
                Targets="go" />  
        </Target>  
    </Project>  
    ```  
  
2.  Vytvořte jiný soubor, který je pojmenován `projectB.proj` a který obsahuje následující kód:  
  
    ```xml  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
    ToolsVersion="12.0">  
  
        <Target Name="go">  
            <Message Text="projectB.proj" />  
            <Message Text="MSBuildToolsVersion: $(MSBuildToolsVersion)" />  
            <Message Text="MSBuildToolsPath:    $(MSBuildToolsPath)" />  
        </Target>  
    </Project>  
    ```  
  
3.  Zadejte následující příkaz na příkazovém řádku:  
  
    ```  
    msbuild projectA.proj /t:go /toolsversion:3.5  
    ```  
  
4.  Zobrazí se následující výstup. Pro `projectA`, `/toolsversion:3.5` přepíše nastavení na příkazovém řádku `ToolsVersion=12.0` nastavení v `Project` značky.  
  
     `ProjectB` je volána úloha v `projectA`. Tento úkol má `ToolsVersion=2.0`, který přepíše dalších `ToolsVersion` nastavení pro `projectB`.  
  
    ```  
    Output:  
      projectA.proj  
      MSBuildToolsVersion: 3.5  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v3.5  
  
      projectB.proj  
      MSBuildToolsVersion: 2.0  
      MSBuildToolsPath:    C:\Windows\Microsoft.NET\Framework\v2.0.50727  
    ```  
  
## <a name="order-of-precedence"></a>Pořadí priorit  
 Pořadí priorit od nejvyšší po nejnižší používá k určení `ToolsVersion` je:  
  
1.  `ToolsVersion` Atribut na úlohu MSBuild používanou pro sestavení projektu, pokud existuje.  
  
2.  `/toolsversion` (Nebo `/tv`) přepínač, který se používá v příkazu msbuild.exe, pokud existuje.  
  
3.  Pokud proměnná prostředí `MSBUILDTREATALLTOOLSVERSIONSASCURRENT` nastavena, potom použijte aktuální `ToolsVersion`.  
  
4.  Pokud proměnná prostředí `MSBUILDTREATHIGHERTOOLSVERSIONASCURRENT` nastavena a `ToolsVersion` definované v projektu soubor je větší než aktuální `ToolsVersion`, použijte aktuální `ToolsVersion`.  
  
5.  Pokud proměnná prostředí `MSBUILDLEGACYDEFAULTTOOLSVERSION` nastaven, nebo pokud `ToolsVersion` není nastavena, použijí se následující kroky:  
  
    1.  `ToolsVersion` Atribut [projektu](../msbuild/project-element-msbuild.md) element souboru projektu. Pokud tento atribut neexistuje, předpokládá se, že se jako aktuální verze.  
  
    2.  Výchozí verze nástroje v souboru MSBuild.exe.config.  
  
    3.  Výchozí verze nástroje v registru. Další informace najdete v tématu [standardní a vlastní konfigurace sady nástrojů](../msbuild/standard-and-custom-toolset-configurations.md).  
  
6.  Pokud proměnná prostředí `MSBUILDLEGACYDEFAULTTOOLSVERSION` není nastavena, použijí se následující kroky:  
  
    1.  Pokud proměnná prostředí `MSBUILDDEFAULTTOOLSVERSION` je nastaven na `ToolsVersion` , existuje, použijte ji.  
  
    2.  Pokud `DefaultOverrideToolsVersion` je nastavena v MSBuild.exe.config, použijte ji.  
  
    3.  Pokud `DefaultOverrideToolsVersion` je nastavení v registru, použijte ji.  
  
    4.  Jinak použijte aktuální `ToolsVersion`.  
  
## <a name="see-also"></a>Viz také  
 [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md)   
 [Standardní a vlastní konfigurace sady nástrojů](../msbuild/standard-and-custom-toolset-configurations.md)