---
title: "Createitem – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#CreateItem
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateItem task [MSBuild]
- MSBuild, CreateItem task
ms.assetid: c4311f38-979e-4324-b524-9e8c1cbdc41a
caps.latest.revision: "15"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7dbf181f89f6cc673452a595da8ec1ddd3b62529
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="createitem-task"></a>CreateItem – úloha
Naplní položku kolekce s vstupní položky. To umožňuje položek, který se má zkopírovat z jednoho seznamu do jiného.  
  
> [!NOTE]
>  Tato úloha je zastaralý. Od verze rozhraní .NET Framework 3.5, položka skupiny může být umístěny uvnitř [cíl](../msbuild/target-element-msbuild.md) elementy. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md).  
  
## <a name="attributes"></a>Atributy  
 Následující tabulka popisuje parametry `CreateItem` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AdditionalMetadata`|Volitelné `String` parametr pole.<br /><br /> Určuje další metadata pro připojení k výstup položky.  Zadejte název metadat a hodnotu pro položku s následující syntaxí:<br /><br /> *MetadataName* `=` *MetadataValue*<br /><br /> Více dvojic název hodnota metadat by měl být oddělené středníkem. Pokud název nebo hodnota obsahuje středníkem nebo jiné speciální znaky, je nutné uvést. Další informace najdete v tématu [postup: vyhnuli speciální znaky v nástroji MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md).|  
|`Exclude`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje položky, které chcete vyloučit z kolekce položek výstup. Tento parametr může obsahovat určení zástupných znaků. Další informace najdete v tématu [položky](../msbuild/msbuild-items.md) a [postupy: vyloučení souborů ze sestavení](../msbuild/how-to-exclude-files-from-the-build.md).|  
|`Include`|Požadované <xref:Microsoft.Build.Framework.ITaskItem> `[]`parametr.<br /><br /> Určuje položky, které chcete zahrnout do kolekce položek výstup. Tento parametr může obsahovat určení zástupných znaků.|  
|`PreserveExistingMetadata`|Volitelné `Boolean` parametr.<br /><br /> Pokud `True`, platí pouze pro další metadata již neexistují.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu vytvoří novou položku kolekci s názvem `MySourceItemsWithMetadata` z kolekce položek `MySourceItems`. `CreateItem` Úloh naplní nové kolekce položek s položkami v `MySourceItems` položky. Potom přidá další metadata položku s názvem `MyMetadata` s hodnotou `Hello` na jednotlivé položky do nové kolekce.  
  
 Po provedení úlohy `MySourceItemsWithMetadata` kolekce položek obsahuje položky `file1.resx` a `file2.resx`, i s záznamů metadat pro `MyMetadata`. `MySourceItems` Kolekce položek se nemění.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceItems Include="file1.resx;file2.resx" />  
    </ItemGroup>  
  
    <Target Name="NewItems">  
        <CreateItem  
            Include="@(MySourceItems)"  
            AdditionalMetadata="MyMetadata=Hello">  
           <Output  
               TaskParameter="Include"  
               ItemName="MySourceItemsWithMetadata"/>  
        </CreateItem>  
  
    </Target>  
  
</Project>  
```  
  
 Následující tabulka popisuje hodnota položky výstupu po spuštění úlohy. Metadata položky se zobrazí v závorkách po položce.  
  
|Kolekce položek|Obsah|  
|---------------------|--------------|  
|`MySourceItemsWithMetadata`|`file1.resx` (`MyMetadata="Hello"`)<br /><br /> `file2.resx` (`MyMetadata="Hello"`)|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)