---
title: Exec – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Exec
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Exec task [MSBuild]
- MSBuild, Exec task
ms.assetid: c9b7525a-b1c9-40fc-8bce-77a5b8f960d8
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 139739524b2c5c4a37f04b7d12dbfe725c6e068c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="exec-task"></a>Exec – úloha
Spouští zadaný programu nebo příkaz pomocí zadaných argumentů.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Exec` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Command`|Požadované `String` parametr.<br /><br /> Příkazy ke spuštění. To může být systémové příkazy, jako je například attrib, nebo spustitelný soubor, jako je například program.exe, runprogram.bat nebo setup.msi.<br /><br /> Tento parametr může obsahovat více řádků příkazy. Alternativně můžete umístit více příkazů v dávkovém souboru a spusťte ho pomocí tohoto parametru.|  
|`ConsoleOutput`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Výstup každé položky je řádek ze standardní výstup nebo standardní chybový proud vygenerované nástrojem. To zachycenou pouze pokud `ConsoleToMsBuild` je nastaven na `true`.|
|`ConsoleToMsBuild`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha zaznamená standardní chybu a standardní výstup nástroje a zpřístupnit v `ConsoleOutput` výstupní parametr. Výchozí hodnota je `false`.|
|`CustomErrorRegularExpression`|Volitelné `String` parametr.<br /><br /> Určuje regulární výraz, který se používá k přímé chyba řádků v výstupu nástroje. To je užitečné pro nástroje, které produkují neobvykle formátovaný výstup.|  
|`CustomWarningRegularExpression`|Volitelné `String` parametr.<br /><br /> Určuje regulární výraz, který se používá k přímé upozornění řádků v výstupu nástroje. To je užitečné pro nástroje, které produkují neobvykle formátovaný výstup.|  
|`EchoOff`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, nebude úloha emitování rozšířené formu `Command` do protokolu nástroje MSBuild. Výchozí hodnota je `false`.|
|`ExitCode`|Volitelné `Int32` výstupní parametr jen pro čtení.<br /><br /> Určuje kód ukončení, které poskytuje provedeného příkazu.|  
|`IgnoreExitCode`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, úloha ignoruje ukončovací kód, který zajišťuje provedeného příkazu. Jinak vrátí úlohu `false` Pokud provedeného příkazu vrátí nenulový ukončovací kód.|  
|`IgnoreStandardErrorWarningFormat`|Volitelné `Boolean` parametr.<br /><br /> Pokud `false`, vybere řádky v výstupu, který odpovídat formátu Standardní chyby nebo upozornění a je zaznamená jako chyby nebo upozornění. Pokud `true`, toto chování zakázat. Výchozí hodnota je `false`.|  
|`Outputs`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky výstup z úlohy. `Exec` Úloh není nastavena tato sám sebe. Místo toho můžete zadat je jako, pokud nastavena, tak, aby bylo možné později v projektu.|  
|`StdErrEncoding`|Volitelné `String` výstupní parametr.<br /><br /> Určuje kódování standardní chybový proud zaznamenané úloh. Výchozí hodnota je aktuální konzole kódování výstup.|  
|`StdOutEncoding`|Volitelné `String` výstupní parametr.<br /><br /> Určuje kódování standardní výstupní datový proud zaznamenané úloh. Výchozí hodnota je aktuální konzole kódování výstup.|  
|`WorkingDirectory`|Volitelné `String` parametr.<br /><br /> Určuje adresář, ve kterém bude příkaz spuštěn.|  
  
## <a name="remarks"></a>Poznámky  
 Tato úloha je užitečné, pokud konkrétní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy pro úlohu, která chcete provést, není k dispozici. Ale `Exec` úlohy, na rozdíl od více konkrétní úkol, nelze provést další zpracování nebo podmíněné operace na základě výsledku nástroj nebo příkaz, který běží.
  
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
