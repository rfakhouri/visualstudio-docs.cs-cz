---
title: Nástroj MSBuild. Cílí na soubory | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93207bb46b8294fe0b4fb3d93416e2fdabe61273
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676336"
---
# <a name="msbuild-targets-files"></a>MSBuild – soubory .Targets
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [MSBuild. Cílí na soubory](https://docs.microsoft.com/visualstudio/msbuild/msbuild-dot-targets-files).  
  
  
[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] obsahuje několik souborů TARGETS, které obsahují položky, vlastnosti, cíle a úkoly pro běžné scénáře. Tyto soubory jsou automaticky importovány do většiny [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] soubory kvůli zjednodušení údržby a čitelnost projektu.  
  
 Projekty obvykle importují jeden nebo více souborů TARGETS pro definování jejich procesu sestavení. Například [!INCLUDE[csprcs](../includes/csprcs-md.md)] projekt vytvořený v rámci [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] naimportuje Microsoft.CSharp.targets, který importuje Microsoft.Common.targets. [!INCLUDE[csprcs](../includes/csprcs-md.md)] Samotného projektu budou definovat položky a vlastnosti specifické pro daný projekt, ale standardní pravidla pro sestavení [!INCLUDE[csprcs](../includes/csprcs-md.md)] projektu jsou definovány v souborech .targets importované.  
  
 `$(MSBuildToolsPath)` Hodnota Určuje cestu tyto běžné soubory .targets. Pokud `ToolsVersion` 4.0, jsou soubory v následujícím umístění: `WindowsInstallationPath\Microsoft.NET\Framework\v4.0.30319\`  
  
> [!NOTE]
>  Informace o tom, jak vytvořit vlastní cíle, naleznete v tématu [cíle](../msbuild/msbuild-targets.md). Informace o tom, jak používat `Import` element soubor projektu lze vložit do jiného souboru projektu, viz [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md) a [postupy: použití stejného cíle ve více souborech projektu](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md).  
  
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


