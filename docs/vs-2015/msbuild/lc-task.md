---
title: LC – úloha | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#LC
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, LC task
- LC task [MSBuild]
ms.assetid: d5a53472-6f2a-42b8-a6db-593ca99c9790
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d151f99aec8f752a64e2dae965321e4ef54eb734
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670933"
---
# <a name="lc-task"></a>LC – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [LC – úloha](https://docs.microsoft.com/visualstudio/msbuild/lc-task).  
  
  
Zabalí LC.exe, který generuje soubor .license z soubor .licx. Další informace o LC.exe najdete v tématu [Lc.exe (kompilátor licencí)](http://msdn.microsoft.com/library/2de803b8-495e-4982-b209-19a72aba0460).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje odřádkování pro `LC` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`LicenseTarget`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje spustitelný soubor, pro které jsou generovány soubory .licenses.|  
|`NoLogo`|Volitelné `Boolean` parametru.<br /><br /> Potlačí zobrazení úvodního nápisu společnosti Microsoft.|  
|`OutputDirectory`|Volitelné `String` parametru.<br /><br /> Určuje adresář, do které chcete umístit soubor .licenses výstup.|  
|`OutputLicense`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje název souboru .licenses. Pokud název nezadáte, název soubor .licx se používá a soubor .licenses je umístěn v adresáři, který se nachází soubor .licx.|  
|`ReferencedAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje načtení při generování souboru .license odkazované součástí.|  
|`SdkToolsPath`|Volitelné `String` parametru.<br /><br /> Určuje cestu k sadě SDK nástroje, jako je resgen.exe.|  
|`Sources`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje položky, které obsahují licencovaných součástí, které chcete zahrnout do souboru .licenses. Další informace najdete v tématu v dokumentaci `/complist` přepínače v [Lc.exe (kompilátor licencí)](http://msdn.microsoft.com/library/2de803b8-495e-4982-b209-19a72aba0460).|  
  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `LC` úkolů ke kompilaci licence.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
<!-- Item declarations, etc -->  
  
    <Target Name="CompileLicenses">  
        <LC  
            Sources="@(LicxFile)"  
            LicenseTarget="$(TargetFileName)"  
            OutputDirectory="$(IntermediateOutputPath)"  
            OutputLicenses="$(IntermediateOutputPath)$(TargetFileName).licenses"  
            ReferencedAssemblies="@(ReferencePath);@(ReferenceDependencyPaths)">  
  
            <Output  
                TaskParameter="OutputLicenses"  
                ItemName="CompiledLicenseFile"/>  
        </LC>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)



