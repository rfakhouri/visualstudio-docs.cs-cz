---
title: "Exec – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#Exec
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Exec task [MSBuild]
- MSBuild, Exec task
ms.assetid: c9b7525a-b1c9-40fc-8bce-77a5b8f960d8
caps.latest.revision: "20"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7447f3f6fc9042bbcca5fc176e26200f4848a04c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="exec-task"></a>Exec – úloha
Spouští zadaný programu nebo příkaz pomocí zadaných argumentů.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Exec` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Command`|Požadované `String` parametr.<br /><br /> Příkazy ke spuštění. To může být systémové příkazy, jako je například attrib, nebo spustitelný soubor, jako je například program.exe, runprogram.bat nebo setup.msi.<br /><br /> Tento parametr může obsahovat více řádků příkazy. Alternativně můžete umístit více příkazů v dávkovém souboru a spusťte ho pomocí tohoto parametru.|  
|`CustomErrorRegularExpression`|Volitelné `String` parametr.<br /><br /> Určuje regulární výraz, který se používá k přímé chyba řádků v výstupu nástroje. To je užitečné pro nástroje, které produkují neobvykle formátovaný výstup.|  
|`CustomWarningRegularExpression`|Volitelné `String` parametr.<br /><br /> Určuje regulární výraz, který se používá k přímé upozornění řádků v výstupu nástroje. To je užitečné pro nástroje, které produkují neobvykle formátovaný výstup.|  
|`ExitCode`|Volitelné `Int32` výstupní parametr jen pro čtení.<br /><br /> Určuje kód ukončení, které poskytuje provedeného příkazu.|  
|`IgnoreExitCode`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha ignoruje ukončovací kód, který zajišťuje provedeného příkazu. Jinak vrátí úlohu `false` Pokud provedeného příkazu vrátí nenulový ukončovací kód.|  
|`IgnoreStandardErrorWarningFormat`|Volitelné `Boolean` parametr.<br /><br /> Pokud `false`, vybere řádky v výstupu, který odpovídat formátu Standardní chyby nebo upozornění a je zaznamená jako chyby nebo upozornění. Pokud `true`, toto chování zakázat. Výchozí hodnota je `false`.|  
|`Outputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky výstup z úlohy. `Exec` Úloh není nastavena tato sám sebe. Místo toho můžete zadat je jako, pokud nastavena, tak, aby bylo možné později v projektu.|  
|`StdErrEncoding`|Volitelné `String` výstupní parametr.<br /><br /> Určuje kódování standardní chybový proud zaznamenané úloh. Výchozí hodnota je aktuální konzole kódování výstup.|  
|`StdOutEncoding`|Volitelné `String` výstupní parametr.<br /><br /> Určuje kódování standardní výstupní datový proud zaznamenané úloh. Výchozí hodnota je aktuální konzole kódování výstup.|  
|`WorkingDirectory`|Volitelné `String` parametr.<br /><br /> Určuje adresář, ve kterém bude příkaz spuštěn.|  
  
## <a name="remarks"></a>Poznámky  
 Tato úloha je užitečné, pokud konkrétní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy pro úlohu, která chcete provést, není k dispozici. Ale `Exec` úlohy, na rozdíl od více konkrétní úkol, nelze shromáždit výstup ze nástroj nebo příkaz, aby byl spouštěn.  
  
 `Exec` Úloh volá cmd.exe místo přímo vyvolání proces.  
  
 Kromě parametry uvedené v tomto dokumentu, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.ToolTaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.ToolTask> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Exec` úlohy ke spuštění příkazu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Binaries Include="*.dll;*.exe"/>  
    </ItemGroup>  
  
    <Target Name="SetACL">  
        <!-- set security on binaries-->  
        <Exec Command="echo y| cacls %(Binaries.Identity) /G everyone:R"/>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
