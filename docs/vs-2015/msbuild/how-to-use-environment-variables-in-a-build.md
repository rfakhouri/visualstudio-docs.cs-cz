---
title: 'Postupy: Použití proměnných prostředí v sestavení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- environment variables, referencing
- projects [.NET Framework], environment variables
- MSBuild, environment variables
ms.assetid: 7f9e4469-8865-4b59-aab3-3ff26bd36e77
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 72d810f998b111aa2ec08a5874498ed8ee23a3be
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63437893"
---
# <a name="how-to-use-environment-variables-in-a-build"></a>Postupy: Použití proměnných prostředí v sestavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při sestavování projektů, je často nutné nastavit možnosti sestavení pomocí informací, které nejsou v souboru projektu nebo soubory, které tvoří vašeho projektu. Tyto informace jsou obvykle uložená v proměnné prostředí.  
  
## <a name="referencing-environment-variables"></a>Odkazuje na proměnné prostředí  
 Všechny proměnné prostředí jsou k dispozici na [!INCLUDE[vstecmsbuildengine](../includes/vstecmsbuildengine-md.md)] ([!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]) projektu soubor jako vlastnosti.  
  
> [!NOTE]
> Pokud soubor projektu obsahuje explicitní definice vlastnosti, která má stejný název jako proměnné prostředí, přepíše vlastnost v souboru projektu hodnotu proměnné prostředí.  
  
#### <a name="to-use-an-environment-variable-in-an-msbuild-project"></a>Chcete-li použít proměnné prostředí v projektu nástroje MSBuild  
  
- Odkazujte na proměnné prostředí stejným způsobem, jako byste to udělali proměnné deklarované v souboru projektu. Například následující kód odkazuje na proměnnou prostředí BIN_PATH:  
  
   `<FinalOutput>$(BIN_PATH)\MyAssembly.dll</FinalOutput>`  
  
  Můžete použít `Condition` atribut poskytnout výchozí hodnotu pro vlastnost, pokud nebyla nastavena proměnná prostředí.  
  
#### <a name="to-provide-a-default-value-for-a-property"></a>Chcete-li zadat výchozí hodnotu pro vlastnost  
  
- Použití `Condition` atribut u vlastnosti a nastavte vlastnost na hodnotu pouze tehdy, pokud nemá žádnou hodnotu. Například následující kód nastaví `ToolsPath` vlastnost c:\tools pouze tehdy, pokud `ToolsPath` není nastavena proměnná prostředí:  
  
     `<ToolsPath Condition="'$(TOOLSPATH)' == ''">c:\tools</ToolsPath>`  
  
    > [!NOTE]
    > Názvy vlastností nejsou malá a velká písmena tak obě `$(ToolsPath)` a `$(TOOLSPATH)` odkazovat na stejnou vlastnost nebo prostředí proměnnou.  
  
## <a name="example"></a>Příklad  
 Následující soubor projektu používá proměnné prostředí a zadejte umístění adresáře.  
  
```  
<Project DefaultTargets="FakeBuild">  
    <PropertyGroup>  
        <FinalOutput>$(BIN_PATH)\myassembly.dll</FinalOutput>  
        <ToolsPath Condition=" '$(ToolsPath)' == '' ">  
            C:\Tools  
        </ToolsPath>  
    </PropertyGroup>  
    <Target Name="FakeBuild">  
        <Message Text="Building $(FinalOutput) using the tools at $(ToolsPath)..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  

[MSBuild](msbuild.md)

[Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties1.md)

[Postupy: Sestavení stejných zdrojových souborů s různými možnostmi](../msbuild/how-to-build-the-same-source-files-with-different-options.md)
