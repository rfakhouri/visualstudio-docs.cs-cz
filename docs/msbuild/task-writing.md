---
title: "Úloha zápis | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, writing tasks
- tasks, creating for MSBuild
- MSBuild, creating tasks
ms.assetid: 3ebc5f87-8f00-46fc-82a1-228f35a6823b
caps.latest.revision: "19"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 0e71fcf69e5624e46261d49ebccc8c634492763a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="task-writing"></a>Zápis úloh
Úlohy zadejte kód, který spouští během procesu sestavení. Úlohy jsou obsažené v cíle. Knihovnu typické úlohy je součástí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], a můžete také vytvořit vlastní úlohy. Další informace o knihovně úlohy, které jsou součástí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], najdete v části [– Reference úlohy](../msbuild/msbuild-task-reference.md).  
  
## <a name="tasks"></a>Úlohy  
 Příklady úloh [kopie](../msbuild/copy-task.md), který zkopíruje jeden nebo více souborů, [makedir –](../msbuild/makedir-task.md), který vytvoří adresář, a [Csc](../msbuild/csc-task.md), které zkompiluje [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] zdrojové soubory kódu. Každý úkol je implementovaný jako třídy rozhraní .NET, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní, která je definována v sestavení Microsoft.Build.Framework.dll.  
  
 Existují dva přístupy, které můžete použít při provádění úlohy:  
  
-   Implementace <xref:Microsoft.Build.Framework.ITask> rozhraní přímo.  
  
-   Vaše třída odvozena od třídy pomocné rutiny, <xref:Microsoft.Build.Utilities.Task>, která je definována v sestavení Microsoft.Build.Utilities.dll. Úloha implementuje ITask a poskytuje výchozí implementaci některé ITask členy. Kromě toho je snazší protokolování.  
  
 V obou případech musíte přidat do vaší třídy metodu s názvem `Execute`, což je metoda, která je volána při spuštění úlohy. Tato metoda nepřijímá žádné parametry a vrátí `Boolean` hodnota: `true` Pokud se úloha úspěšně nebo `false` Pokud se nezdařilo. Následující příklad ukazuje úlohu, která neprovede žádnou akci a vrátí `true`.  
  
```csharp
using System;  
using Microsoft.Build.Framework;  
using Microsoft.Build.Utilities;  
  
namespace MyTasks  
{  
    public class SimpleTask : Task  
    {  
        public override bool Execute()  
        {  
            return true;  
        }  
    }  
}  
```  
  
 Tato úloha spuštěna následující soubor projektu:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyTarget">  
        <SimpleTask />  
    </Target>  
</Project>  
```  
  
 Při spuštění úlohy, můžete také obdrží vstupy ze souboru projektu Pokud vytvoříte .NET vlastnosti pro třídu úloh. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]Nastaví tyto vlastnosti bezprostředně před volání úkolu `Execute` metoda. K vytvoření ve vlastnosti string. použijte kód úlohy, jako:  
  
```csharp
using System;  
using Microsoft.Build.Framework;  
using Microsoft.Build.Utilities;  
  
namespace MyTasks  
{  
    public class SimpleTask : Task  
    {  
        public override bool Execute()  
        {  
            return true;  
         }  
  
        private string myProperty;  
        public string MyProperty  
        {  
            get { return myProperty; }  
            set { myProperty = value; }  
        }  
    }  
}  
```  
  
 Tato úloha a nastaví projektu následující spustí soubor `MyProperty` na zadanou hodnotu:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <SimpleTask MyProperty="Value for MyProperty" />  
   </Target>  
</Project>  
```  
  
## <a name="registering-tasks"></a>Registrace úlohy  
 Pokud projekt budete pro spuštění úlohy, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] musí vědět, jak najít je sestavení obsahující třídu úloh. Úlohy jsou registrovat pomocí [usingtask – Element (MSBuild)](../msbuild/usingtask-element-msbuild.md).  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Soubor Microsoft.Common.Tasks je soubor projektu, který obsahuje seznam `UsingTask` elementy, které registrují všechny úkoly, které jsou součástí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Tento soubor je automaticky zahrnuty při vytváření všech projektech. Pokud úloha, která je registrována v Microsoft.Common.Tasks se registruje v aktuální souboru projektu, aktuální soubor projektu má přednost před; To znamená můžete přepsat výchozí úlohu s vlastní úlohu, která má stejný název.  
  
> [!TIP]
>  Zobrazí se seznam úloh, které jsou součástí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zobrazením obsah Microsoft.Common.Tasks.  
  
## <a name="raising-events-from-a-task"></a>Vyvolání událostí z úlohy  
 Pokud vaším úkolem je odvozena z <xref:Microsoft.Build.Utilities.Task> pomocná třída, můžete použít některý z následujících metod helper na <xref:Microsoft.Build.Utilities.Task> třídy pro vyvolání události, které bude zachycena a zobrazí všechny registrované protokolovacích nástrojů:  
  
```csharp
public override bool Execute()  
{  
    Log.LogError("messageResource1", "1", "2", "3");  
    Log.LogWarning("messageResource2");  
    Log.LogMessage(MessageImportance.High, "messageResource3");  
    ...  
}  
```  
  
 Pokud vaše úloha implementuje <xref:Microsoft.Build.Framework.ITask> přímo, můžete dál zvýšit tyto události ale musí používat rozhraní IBuildEngine. Následující příklad ukazuje úlohu, která implementuje ITask a vyvolá vlastní události:  
  
```csharp
public class SimpleTask : ITask  
{  
    private IBuildEngine buildEngine;  
    public IBuildEngine BuildEngine  
    {  
        get{ return buildEngine; }  
        set{ buildEngine = value; }  
    }  
  
    public override bool Execute()  
    {  
        TaskEventArgs taskEvent =  
            new TaskEventArgs(BuildEventCategory.Custom,  
            BuildEventImportance.High, "Important Message",  
           "SimpleTask");  
        BuildEngine.LogBuildEvent(taskEvent);  
        return true;  
    }  
}  
```  
  
## <a name="requiring-task-parameters-to-be-set"></a>Vyžadování parametry úlohy nastavení  
 Některé vlastnosti úlohy jako "požadované" můžete označit tak, aby všechny soubory projektu, které spouští úlohy musí nastavit hodnoty pro tyto vlastnosti nebo sestavení selže. Použít `[Required]` atribut vlastnost úlohu v rozhraní .NET následujícím způsobem:  
  
```csharp
private string requiredProperty;  
  
[Required]  
public string RequiredProperty  
{  
    get { return requiredProperty; }  
    set { requiredProperty = value; }  
}  
```  
  
 `[Required]` Je definován atribut <xref:Microsoft.Build.Framework.RequiredAttribute> v <xref:Microsoft.Build.Framework> oboru názvů.  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Níže [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] třída ukazuje úlohu odvozování z <xref:Microsoft.Build.Utilities.Task> pomocná třída. Tato úloha vrátí `true`, což indikuje, že ho byla úspěšná.  
  
### <a name="code"></a>Kód  
  
```csharp
using System;  
using Microsoft.Build.Utilities;  
  
namespace SimpleTask1  
{  
    public class SimpleTask1: Task  
    {  
        public override bool Execute()  
        {  
            // This is where the task would presumably do its work.  
            return true;  
        }  
    }  
}  
```  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Níže [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] třída ukazuje úloh implementace <xref:Microsoft.Build.Framework.ITask> rozhraní. Tato úloha vrátí `true`, což indikuje, že ho byla úspěšná.  
  
### <a name="code"></a>Kód  
  
```csharp
using System;  
using Microsoft.Build.Framework;  
  
namespace SimpleTask2  
{  
    public class SimpleTask2: ITask  
    {  
        //When implementing the ITask interface, it is necessary to  
        //implement a BuildEngine property of type  
        //Microsoft.Build.Framework.IBuildEngine. This is done for  
        //you if you derive from the Task class.  
        private IBuildEngine buildEngine;  
        public IBuildEngine BuildEngine  
        {  
            get  
            {  
                return buildEngine;  
            }  
            set  
            {  
                buildEngine = value;  
            }  
         }  
  
        // When implementing the ITask interface, it is necessary to  
        // implement a HostObject property of type Object.  
        // This is done for you if you derive from the Task class.  
        private Object hostObject;  
        public Object HostObject  
        {  
            get  
            {  
                return hostObject;  
            }  
  
            set  
            {  
                hostObject = value;  
            }  
        }  
  
        public bool Execute()  
        {  
            // This is where the task would presumably do its work.  
            return true;  
        }  
    }  
}  
```  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 To [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] třída ukazuje úlohu, která je odvozena z <xref:Microsoft.Build.Utilities.Task> pomocná třída. Má vlastnost požadovaný řetězec a vyvolá událost, která se zobrazí všechny registrované protokolovacích nástrojů.  
  
### <a name="code"></a>Kód  
 [!code-csharp[msbuild_SimpleTask3#1](../msbuild/codesnippet/CSharp/task-writing_1.cs)]  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje soubor projektu vyvolání předchozí příklad úloha SimpleTask3.  
  
### <a name="code"></a>Kód  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <UsingTask TaskName="SimpleTask3.SimpleTask3"   
        AssemblyFile="SimpleTask3\bin\debug\simpletask3.dll"/>  
  
    <Target Name="MyTarget">  
        <SimpleTask3 MyProperty="Hello!"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)