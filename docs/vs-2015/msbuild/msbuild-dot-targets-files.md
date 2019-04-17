---
title: Nástroj MSBuild. Cílí na soubory | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- .Targets files
- MSBuild, .Targets files
ms.assetid: f6d98eb4-d2fa-49b7-8e3c-bae1ca3cf596
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 74ac0a2c1ab50cf4c707f4fc9414fe4aa4f403b8
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59655059"
---
# <a name="msbuild-targets-files"></a>MSBuild – soubory .Targets
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] obsahuje několik souborů TARGETS, které obsahují položky, vlastnosti, cíle a úkoly pro běžné scénáře. Tyto soubory jsou automaticky importovány do většiny [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] soubory kvůli zjednodušení údržby a čitelnost projektu.  
  
 Projekty obvykle importují jeden nebo více souborů TARGETS pro definování jejich procesu sestavení. Například [!INCLUDE[csprcs](../includes/csprcs-md.md)] projekt vytvořený v rámci [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] naimportuje Microsoft.CSharp.targets, který importuje Microsoft.Common.targets. [!INCLUDE[csprcs](../includes/csprcs-md.md)] Samotného projektu budou definovat položky a vlastnosti specifické pro daný projekt, ale standardní pravidla pro sestavení [!INCLUDE[csprcs](../includes/csprcs-md.md)] projektu jsou definovány v souborech .targets importované.  
  
 `$(MSBuildToolsPath)` Hodnota Určuje cestu tyto běžné soubory .targets. Pokud `ToolsVersion` 4.0, jsou soubory v následujícím umístění: `WindowsInstallationPath\Microsoft.NET\Framework\v4.0.30319\`  
  
> [!NOTE]
>  Informace o tom, jak vytvořit vlastní cíle, naleznete v tématu [cíle](../msbuild/msbuild-targets.md). Informace o tom, jak používat `Import` element soubor projektu lze vložit do jiného souboru projektu, viz [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md) a [jak: Použití stejného cíle ve více souborech projektu](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md).  
  
## <a name="common-targets-files"></a>Běžné. Soubory cíle  
  
|. Soubor cílů|Popis|  
|-------------------|-----------------|  
|Microsoft.Common.targets|Definuje kroky v procesu standardní sestavení pro [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] a [!INCLUDE[csprcs](../includes/csprcs-md.md)] projekty.<br /><br /> Importováno Microsoft.CSharp.targets a Microsoft.VisualBasic.targets soubory, které zahrnují následující příkaz: `<Import Project="Microsoft.Common.targets" />`|  
|Microsoft.CSharp.targets|Definuje kroky na standardní proces sestavení pro projekty Visual C#.<br /><br /> Importovat pomocí Visual C# soubory projektu (.csproj), které zahrnují následující příkaz: `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`|  
|Microsoft.VisualBasic.targets|Definuje kroky na standardní proces sestavení pro projekty jazyka Visual Basic.<br /><br /> Importovat soubory projektu Visual Basic (.vbproj), které zahrnují následující příkaz: `<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`|  
  
## <a name="see-also"></a>Viz také  
 [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)  
 [MSBuild](msbuild.md)
