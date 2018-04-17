---
title: Registerassembly – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#RegisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, RegisterAssembly task
- RegisterAssembly task [MSBuild]
ms.assetid: ba5f19ac-6764-4d28-9b79-a86de58f8987
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b6b199876419cba3c53bf2d9443d42deac8fa0e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="registerassembly-task"></a>RegisterAssembly – úloha
Načte metadata v rámci zadaného sestavení a přidá nezbytné položky registru, která umožňuje klientům COM vytvořit [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] třídy transparentně. Chování této úlohy je podobný, ale není stejná jako ve [Regasm.exe (Nástroj registrace sestavení)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `RegisterAssembly` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Assemblies`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje ta sestavení zaregistrovat u modelu COM.|  
|`AssemblyListFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Obsahuje informace o stavu mezi `RegisterAssembly` úloh a [unregisterassembly –](../msbuild/unregisterassembly-task.md) úloh. Zabrání se tak `UnregisterAssembly` úloh v pokusu o zrušení registrace sestavení, které se nepodařilo zaregistrovat v `RegisterAssembly` úloh.|  
|`CreateCodeBase`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vytvoří codebase záznam v registru, který určuje cestu k souboru pro sestavení, které není nainstalována v globální mezipaměti sestavení. Tuto možnost byste neměli zadávat, pokud následně instalujete sestavení, které budete registrovat do globální mezipaměti sestavení (GAC).|  
|`TypeLibFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje typ knihovny generování na základě zadaného sestavení. Vygenerovaný typ knihovna obsahuje definice dostupné typy definované v rámci sestavení. Knihovny typů se vygeneruje pouze tehdy, pokud platí jedna z následujících akcí:<br /><br /> -Knihovny typů s tímto názvem neexistuje v tomto umístění.<br />-Existuje knihovny typů, ale je starší než předávány v sestavení.<br /><br /> Pokud je novější než sestavení předávány knihovny typů, nevytvoří nové, ale bude stále registrovaná sestavení.<br /><br /> Pokud je tento parametr zadán, musí mít stejný počet položek, jako `Assemblies` parametr nebo úloha se nezdaří. Pokud nejsou zadány žádné vstupy, bude úloha výchozí název sestavení a změňte příponu položky na .tlb.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `RegisterAssembly` úloh k registraci sestavení určeného `MyAssemblies` kolekce položek.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyAssemblies Include="MyAssembly.dll" />  
    <ItemGroup>  
  
    <Target Name="RegisterAssemblies">  
        <RegisterAssembly  
            Assemblies="@(MyAssemblies)" >  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)