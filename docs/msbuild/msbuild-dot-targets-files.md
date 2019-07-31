---
title: Nástroji. Soubory cílů | Microsoft Docs
ms.date: 02/24/2017
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bacc58184d0ea78a5e54d7cc7b0b93df107b3300
ms.sourcegitcommit: 5694c5236fa32ba7f5bc1236a853f725ec7557e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68681401"
---
# <a name="msbuild-targets-files"></a>MSBuild. targets – soubory
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]obsahuje několik souborů *. targets* , které obsahují položky, vlastnosti, cíle a úkoly pro běžné scénáře. Tyto soubory jsou automaticky importovány do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] většiny souborů projektu pro zjednodušení údržby a čitelnosti.

 Projekty obvykle importují jeden nebo více souborů *. targets* pro definování svého procesu sestavení. Například [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projekt vytvořený pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] provede import *Microsoft. CSharp. targets* , který importuje *Microsoft. Common. targets*. Samotný projekt bude definovat položky a vlastnosti specifické pro daný projekt, ale standardní pravidla sestavení [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] pro projekt jsou definována v importovaných souborech *. targets* . [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]

 Hodnota určuje cestu těchto běžných souborů *. targets.* `$(MSBuildToolsPath)` `ToolsVersion` Pokud je 4,0, soubory jsou v následujícím umístění: *\<WindowsInstallationPath>\Microsoft.NET\Framework\v4.0.30319\\*

> [!NOTE]
> Informace o tom, jak vytvořit vlastní cíle, najdete v tématu [cíle](../msbuild/msbuild-targets.md). Informace o použití `Import` prvku pro vložení souboru projektu do jiného souboru projektu naleznete v tématu [Import element (MSBuild)](../msbuild/import-element-msbuild.md) a [How to: Použijte stejný cíl ve více souborech](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md)projektu.

## <a name="common-targets-files"></a>Společné soubory. targets

| soubor *. targets* | Popis |
|---------------------------------| - |
| *Microsoft. Common. targets* | Definuje kroky ve standardním procesu sestavení pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty a. [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]<br /><br /> Importováno soubory *Microsoft. CSharp. targets* a *Microsoft. VisualBasic. targets* , které zahrnují následující příkaz:`<Import Project="Microsoft.Common.targets" />` |
| *Microsoft.CSharp.targets* | Definuje kroky ve standardním procesu sestavení pro vizuální C# projekty.<br /><br /> Importováno pomocí C# souborů Visual Project ( *. csproj*), které zahrnují následující příkaz:`<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` |
| *Microsoft.VisualBasic.targets* | Definuje kroky ve standardním procesu sestavení pro projekty Visual Basic.<br /><br /> Importováno pomocí Visual Basic soubory projektu ( *. vbproj*), které zahrnují následující příkaz:`<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />` |

## <a name="directorybuildtargets"></a>Directory. Build. targets
*Directory. Build. targets* je uživatelsky definovaný soubor, který poskytuje přizpůsobení projektům v adresáři. Tento soubor se automaticky naimportuje z *Microsoft. Common. targets* , pokud vlastnost **ImportDirectoryBuildTargets** není nastavená na **false**. Další informace získáte [přizpůsobením sestavení](customize-your-build.md).

## <a name="see-also"></a>Viz také:
- [Import – element (MSBuild)](../msbuild/import-element-msbuild.md)
- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
- [MSBuild](../msbuild/msbuild.md)
