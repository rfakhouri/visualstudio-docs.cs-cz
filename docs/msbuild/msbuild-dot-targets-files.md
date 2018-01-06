---
title: "MSBuild. Cílem soubory | Microsoft Docs"
ms.custom: 
ms.date: 02/24/2017
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
helpviewer_keywords:
- .Targets files
- MSBuild, .Targets files
ms.assetid: f6d98eb4-d2fa-49b7-8e3c-bae1ca3cf596
caps.latest.revision: "17"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c382d6e967705b95e46c6c797915c49841688c6c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-targets-files"></a>MSBuild – soubory .Targets
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]zahrnuje několik .TARGETS – soubory, které obsahují položky, vlastnosti, cílů a úloh pro běžné scénáře. Tyto soubory se automaticky importují do většinu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] soubory ke zjednodušení správy a čitelnost projektu.  

 Projekty obvykle importovat jeden nebo více souborů .targets definovat jejich procesu sestavení. Například [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projektu vytvořených [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] naimportuje Microsoft.CSharp.targets, který importuje Microsoft.Common.targets. [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] Samotném projektu definují položky a vlastnosti specifické pro tento projekt, ale standardní pravidla pro sestavení [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projektu jsou definovány v importovaných .TARGETS – soubory.  

 `$(MSBuildToolsPath)` Hodnota Určuje cestu tyto společné soubory .targets. Pokud `ToolsVersion` 4.0, jsou soubory v následujícím umístění:`WindowsInstallationPath\Microsoft.NET\Framework\v4.0.30319\`  

> [!NOTE]
>  Informace o tom, jak vytvořit vlastní cíle najdete v tématu [cíle](../msbuild/msbuild-targets.md). Informace o tom, jak používat `Import` elementu, který chcete vložit soubor projektu do jiného souboru projektu, najdete v části [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md) a [postupy: použití stejného cíle ve více souborech projektu](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md).  

## <a name="common-targets-files"></a>Běžné. Soubory cíle  

|. Soubor cíle|Popis|  
|-------------------|-----------------|  
|Microsoft.Common.targets|Definuje podle kroků v procesu sestavení standardní pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekty.<br /><br /> Importovat pomocí Microsoft.CSharp.targets a Microsoft.VisualBasic.targets soubory, které zahrnují následující příkaz:`<Import Project="Microsoft.Common.targets" />`|  
|Microsoft.CSharp.targets|Definuje podle kroků v procesu sestavení standardní pro projekty Visual C#.<br /><br /> Importovat pomocí Visual C# soubory projektu (.csproj), které zahrnují následující příkaz:`<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`|  
|Microsoft.VisualBasic.targets|Definuje podle kroků v procesu sestavení standardní pro projekty Visual Basic.<br /><br /> Importovat pomocí souborů projektu jazyka Visual Basic (.vbproj), které zahrnují následující příkaz:`<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`|

## <a name="directorybuildtargets"></a>Directory.Build.targets
Directory.Build.targets je soubor definovaný uživatelem, který poskytuje přizpůsobení projektů adresáře. Tento soubor je automaticky importovány ze Microsoft.Common.targets, pokud vlastnost **ImportDirectoryBuildTargets** je nastaven na **false**.

## <a name="see-also"></a>Viz také  
 [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)  
 [MSBuild](../msbuild/msbuild.md)
