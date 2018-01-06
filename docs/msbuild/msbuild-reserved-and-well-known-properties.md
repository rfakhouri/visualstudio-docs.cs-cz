---
title: "MSBuild vyhrazené a známé vlastnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords: MSBuild, reserved properties
ms.assetid: 99333e61-83c9-4804-84e3-eda297c2478d
caps.latest.revision: "29"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 136e488f78090211f4c63f685338d61556982b9d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-reserved-and-well-known-properties"></a>Vyhrazené a známé vlastnosti nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]poskytuje sadu předdefinovaných vlastností, které obsahují informace o souboru projektu a [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] binární soubory. Tyto vlastnosti jsou vyhodnocovány v stejným způsobem jako jiné [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vlastnosti. Chcete-li například použít `MSBuildProjectFile` vlastnost, zadáte `$(MSBuildProjectFile)`.  
  
 MSBuild používá předdefinovat vyhrazené a známé vlastnosti hodnoty v následující tabulce. Rezervované vlastnosti nelze přepsat, ale dobře známé vlastnosti lze přepsat pomocí vlastnosti stejně jako s názvem prostředí, globální vlastnosti nebo vlastnosti, které jsou deklarované v souboru projektu.  
  
## <a name="reserved-and-well-known-properties"></a>Vyhrazené a známé vlastnosti  
 V následující tabulce jsou popsány [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] předdefinované vlastnosti.  
  
|Vlastnost|Popis|Vyhrazené nebo Well-Known|  
|--------------|-----------------|-----------------------------|  
|`MSBuildBinPath`|Absolutní cesta ke složce kde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] binární soubory, které jsou právě používány nacházejí (například C:\Windows\Microsoft.Net\Framework\\*Cisloverze*). Tato vlastnost je užitečná, pokud máte k odkazování na soubory v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] adresáře.<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.|Vyhrazené|  
|`MSBuildExtensionsPath`|Byla zavedená v rozhraní .NET Framework 4: není žádný rozdíl mezi výchozí hodnoty `MSBuildExtensionsPath` a `MSBuildExtensionsPath32`. Můžete nastavit proměnné prostředí `MSBUILDLEGACYEXTENSIONSPATH` na nenulovou hodnotu povolit chování na výchozí hodnotu `MSBuildExtensionsPath` v dřívějších verzích.<br /><br /> V rozhraní .NET Framework 3.5 a starší, výchozí hodnota `MSBuildExtensionsPath` odkazuje na cestu MSBuild podsložku \Program Files\ nebo \Program soubory (x86) složky, v závislosti na počtu bitů aktuálním procesu. Pro 32bitový proces na 64bitový počítač, například tuto vlastnost odkazuje na složce \Program Files (x86). Pro 64bitový proces na 64bitový počítač tato vlastnost odkazuje na složce \Program Files.<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.<br /><br /> Toto umístění je užitečné místo pro soubory vlastní cíl. Cílové soubory například může nainstalovat na \Program Files\MSBuild\MyFiles\Northwind.targets a pak importovat v souborech projektu pomocí tohoto kódu XML:<br /><br /> `<Import Project="$(MSBuildExtensionsPath)\MyFiles\Northwind.targets"/>`|Známé|  
|`MSBuildExtensionsPath32`|Cestu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podsložku \Program soubory nebo složky \Program Files (x86). Tato cesta vždycky směřuje na 32-bit \Program složka souborů na 32bitový počítač a \Program soubory (x86) na 64bitový počítač. Viz také `MSBuildExtensionsPath` a `MSBuildExtensionsPath64`.<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.|Známé|  
`MSBuildExtensionsPath64`|Cestu [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podsložky ve složce \Program Files. Pro 64bitový počítač tato cesta vždycky směřuje na složce \Program Files. Pro 32bitový počítač je tato cesta je prázdná. Viz také `MSBuildExtensionsPath` a `MSBuildExtensionsPath32`.<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.|Známé|  
|`MSBuildLastTaskResult`|`true`Pokud předchozí úloha dokončeno bez chyb (i když došlo k upozorněním), nebo `false` Pokud předchozí úloha došlo k chybám. Obvykle když dojde k chybě v úloze, chyba je poslední, co se děje v tomto projektu. Hodnota této vlastnosti je proto nikdy `false`, s výjimkou v těchto scénářích:<br /><br /> – Když `ContinueOnError` atribut [Task – Element (MSBuild)](../msbuild/task-element-msbuild.md) je nastaven na `WarnAndContinue` (nebo `true`) nebo `ErrorAndContinue`.<br /><br /> – Když `Target` má [OnError – Element (MSBuild)](../msbuild/onerror-element-msbuild.md) jako podřízený element.|Vyhrazené|  
|`MSBuildNodeCount`|Maximální počet souběžných procesů, které se používají při vytváření. Toto je hodnota, která jste zadali pro **/maxcpucount** na příkazovém řádku. Pokud jste zadali **/maxcpucount** bez zadání hodnoty, pak `MSBuildNodeCount` určuje počet procesorů v počítači. Další informace najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md) a [sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).|Vyhrazené|  
|`MSBuildProgramFiles32`|Umístění složky 32bitový program; například `C:\Program Files (x86)`.<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.|Vyhrazené|  
|`MSBuildProjectDefaultTargets`|Úplný seznam cílů, které jsou určené v `DefaultTargets` atribut `Project` elementu. Například následující `Project` by měla mít element `MSBuildDefaultTargets` hodnota vlastnosti `A;B;C`:<br /><br /> `<Project DefaultTargets="A;B;C" >`|Vyhrazené|  
|`MSBuildProjectDirectory`|Absolutní cesta k adresáři, kde souboru projektu nachází, například `C:\MyCompany\MyProduct`.<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.|Vyhrazené|  
|`MSBuildProjectDirectoryNoRoot`|Hodnota `MSBuildProjectDirectory` vlastnost, s výjimkou kořenovou jednotku.<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.|Vyhrazené|  
|`MSBuildProjectExtension`|Příponu názvu souboru souboru projektu, včetně období; například .proj.|Vyhrazené|  
|`MSBuildProjectFile`|Název souboru dokončení souboru projektu, včetně přípony názvu souboru; například MyApp.proj.|Vyhrazené|  
|`MSBuildProjectFullPath`|Absolutní cesta a název souboru dokončení souboru projektu, včetně přípony názvu souboru; například C:\MyCompany\MyProduct\MyApp.proj.|Vyhrazené|  
|`MSBuildProjectName`|Název souboru bez přípony názvu souboru; souboru projektu například Moje aplikace.|Vyhrazené|  
|`MSBuildRuntimeType`|Typ modulu runtime, který je aktuálně spuštěné. Zavedly v nástroji MSBuild 15. Hodnota může být definován (před verzí nástroje MSBuild 15), `Full` označující, že MSBuild běží na ploše rozhraní .NET Framework, `Core` označující, že MSBuild běží na .NET Core, nebo `Mono` označující, že MSBuild běží na Mono.|Vyhrazené|  
|`MSBuildStartupDirectory`|Absolutní cesta ke složce kde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] je volána. Pomocí této vlastnosti můžete vytvořit všechno pod určitého bodu v projektu stromu bez vytvoření dirs.proj soubory ve všech adresářích. Místo toho máte pouze jednu projektu – například c:\traversal.proj, jak je vidět tady:<br /><br /> `<Project ...>     <ItemGroup>         <ProjectFiles              Include="$            (MSBuildStartupDirectory)            **\*.csproj"/>     </ItemGroup>     <Target Name="build">         <MSBuild             Projects="@(ProjectFiles)"/>     </Target> </Project>`<br /><br /> Chcete-li vytvořit v libovolném bodě ve stromové struktuře, zadejte:<br /><br /> `msbuild c:\traversal.proj`<br /><br /> Nezahrnujte konečné zpětné lomítko na tuto vlastnost.|Vyhrazené|  
|`MSBuildThisFile`|Název souboru a soubor rozšíření část `MSBuildThisFileFullPath`.|Vyhrazené|  
|`MSBuildThisFileDirectory`|Část directory `MSBuildThisFileFullPath`.<br /><br /> Zahrňte do cesty konečné zpětné lomítko.|Vyhrazené|  
|`MSBuildThisFileDirectoryNoRoot`|Část directory `MSBuildThisFileFullPath`, s výjimkou kořenovou jednotku.<br /><br /> Zahrňte do cesty konečné zpětné lomítko.|Vyhrazené|  
|`MSBuildThisFileExtension`|Název souboru příponu část `MSBuildThisFileFullPath`.|Vyhrazené|  
|`MSBuildThisFileFullPath`|Absolutní cesta souboru projektu nebo cíle, který obsahuje cíl, který běží.<br /><br /> Tip: Zadejte relativní cestu v souboru cíle, která je relativní vzhledem k souboru cíle a není vzhledem k původní soubor projektu.|Vyhrazené|  
|`MSBuildThisFileName`|Část názvu souboru `MSBuildThisFileFullPath`, bez přípony názvu souboru.|Vyhrazené|  
|`MSBuildToolsPath`|Cesta instalace [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] verzi, která je přidružená hodnota `MSBuildToolsVersion`.<br /><br /> V cestě nezahrnují konečné zpětné lomítko.<br /><br /> Tuto vlastnost nelze přepsat.|Vyhrazené|  
|`MSBuildToolsVersion`|Verze [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] sada nástrojů, který je použit k vytvoření projektu.<br /><br /> Poznámka: [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] nástrojů se skládá z úloh, cílů a nástroje, které se používají k vytvoření aplikace. K nástrojům patří kompilátory například csc.exe a vbc.exe. Další informace najdete v tématu [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md), a [standardní a vlastní konfigurace sady nástrojů](../msbuild/standard-and-custom-toolset-configurations.md).|Vyhrazené|  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md) [vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)