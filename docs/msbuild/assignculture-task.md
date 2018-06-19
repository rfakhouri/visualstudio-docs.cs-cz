---
title: Assignculture – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#AssignCulture
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, AssignCulture task
- AssignCulture task [MSBuild]
ms.assetid: 8f8314cc-82a6-4f16-a62d-b9f0d1d5e274
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 26adf9bd97e10e25402db100ebb0140917ac6143
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31578715"
---
# <a name="assignculture-task"></a>AssignCulture – úloha
Tato úloha přijímá seznam položek, které mohou obsahovat platný řetězec identifikátor jazykové verze rozhraní .NET jako součást názvu souboru a vytvoří položky, které mají metadata, s názvem `Culture` obsahující odpovídající identifikátor jazykovou verzi. Například má název souboru Form1.fr fr.resx embedded jazykovou verzi identifikátor "fr-fr", takže tato úloha vytvoří položku, která má stejný název souboru s metadaty `Culture` rovna `fr-fr`. Úloha také vytvoří seznam názvů souborů s jazykovou verzi odebrána z název souboru.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `AssignCulture` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AssignedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje seznam položek dostali `Files` parametr s `Culture` položka metadat přidat na jednotlivé položky.<br /><br /> Pokud příchozí položky z `Files` již obsahuje parametr `Culture` položka metadat, původní položka metadat se používá.<br /><br /> Pouze přiřadí úlohu `Culture` položka metadat, pokud název souboru obsahuje identifikátor platná jazyková verze. Identifikátor jazykové verze musí být mezi poslední dvě tečky v názvu souboru.|  
|`AssignedFilesWithCulture`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje podmnožinu položky z `AssignedFiles` parametr, který jste `Culture` položka metadat.|  
|`AssignedFilesWithNoCulture`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje podmnožinu položky z `AssignedFiles` parametr, který není `Culture` položka metadat.|  
|`CultureNeutralAssignedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje stejný seznam položek, které se vytvářejí v `AssignedFiles` parametr, s výjimkou s jazykovou verzi odebrána z názvu souboru.<br /><br /> Jazyková verze úlohu pouze odebere z názvu souboru, pokud je identifikátor platná jazyková verze.|  
|`Files`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje seznam souborů, které s názvy vložených jazykovou verzi přiřadit jazykovou verzi pro.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad spustí `AssignCulture` úloh s `ResourceFiles` kolekce položek.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ResourceFiles Include="MyResource1.fr.resx"/>  
        <ResourceFiles Include="MyResource2.XX.resx"/>  
    </ItemGroup>  
  
    <Target Name="Culture">  
        <AssignCulture  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
            <Output TaskParameter="AssignedFilesWithCulture"  
                ItemName="OutAssignedFilesWithCulture"/>  
            <Output TaskParameter="AssignedFilesWithNoCulture"  
                ItemName="OutAssignedFilesWithNoCulture"/>  
            <Output TaskParameter="CultureNeutralAssignedFiles"  
                ItemName="OutCultureNeutralAssignedFiles"/>  
        </AssignCulture>  
    </Target>  
</Project>  
```  
  
 Následující tabulka popisuje hodnoty položek výstupu po spuštění úlohy. Metadata položky se zobrazí v závorkách po položce.  
  
|Kolekce položek|Obsah|  
|---------------------|--------------|  
|`OutAssignedFiles`|`MyResource1.fr.resx (Culture="fr")`<br /><br /> `MyResource2.XX.resx` (žádná další metadata)|  
|`OutAssignedFilesWithCulture`|`MyResource1.fr.resx (Culture="fr")`|  
|`OutAssignedFilesWithNoCulture`|`MyResource2.XX.resx` (žádná další metadata)|  
|`OutCultureNeutralAssignedFiles`|`MyResource1.resx (Culture="fr")`<br /><br /> `MyResource2.XX.resx (`žádná další metadata.)|  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)