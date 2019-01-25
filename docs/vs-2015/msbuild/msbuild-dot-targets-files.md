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
ms.openlocfilehash: 4292509e9177c64a0018e0f1c7e95eebf442ffcf
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54772283"
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
