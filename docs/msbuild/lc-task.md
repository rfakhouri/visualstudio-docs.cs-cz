---
title: LC – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b80d43a291f5afaf9be34ad5b7f1f7a474ba93e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="lc-task"></a>LC – úloha
Zabalí LC.exe, který generuje soubor .license z .licx – soubor. Další informace o LC.exe najdete v tématu [Lc.exe (kompilátor licencí)](/dotnet/framework/tools/lc-exe-license-compiler).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje datového pro `LC` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`LicenseTarget`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje spustitelný soubor, pro které se generují .licenses – soubory.|  
|`NoLogo`|Volitelné `Boolean` parametr.<br /><br /> Potlačí zobrazení úvodního nápisu společnosti Microsoft.|  
|`OutputDirectory`|Volitelné `String` parametr.<br /><br /> Určuje adresář, do níž umístíte .licenses – výstupní soubory.|  
|`OutputLicense`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje název .licenses – soubor. Pokud název nezadáte, bude použit název .licx – soubor a .licenses – soubor je umístěn v adresáři, který obsahuje .licx – soubor.|  
|`ReferencedAssemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje odkazované součásti, které zatížení při generování souboru .license.|  
|`SdkToolsPath`|Volitelné `String` parametr.<br /><br /> Určuje cestu k SDK nástroje, jako je například resgen.exe.|  
|`Sources`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje položky, které obsahují licencovanou komponenty, které chcete zahrnout do .licenses – soubor. Další informace najdete v dokumentaci pro `/complist` přepínač ve [Lc.exe (kompilátor licencí)](/dotnet/framework/tools/lc-exe-license-compiler).|  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `LC` úlohy kompilace licence.  
  
```xml  
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