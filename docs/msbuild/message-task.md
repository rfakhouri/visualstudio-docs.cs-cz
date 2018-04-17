---
title: Zpráva úlohy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Message
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Message task
- Message task [MSBuild]
ms.assetid: 2293309d-42b6-46dc-9684-8c146f66bc28
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f119f171afb462f55e95f7178e44eb8bbb682863
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="message-task"></a>Úlohy zpráv
Zaznamená zprávu během sestavení.  
  
## <a name="parameters"></a>Parametry  
 V následující tabulce jsou popsány parametry `Message` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Importance`|Volitelné `String` parametr.<br /><br /> Určuje význam zprávy. Tento parametr může mít hodnotu `high`, `normal` nebo `low`. Výchozí hodnota je `normal`.|  
|`Text`|Volitelné `String` parametr.<br /><br /> Text chyby do protokolu.|  
  
## <a name="remarks"></a>Poznámky  
 `Message` Úloha umožňuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektů problém zprávy protokolovacích nástrojů v různých kroků v procesu sestavení.  
  
 Pokud `Condition` vyhodnocen jako parametr `true`, hodnota `Text` parametr bude do protokolu a sestavení budou nadále provést. Pokud `Condition` parametr neexistuje, se do protokolu zapíše text zprávy. Další informace o protokolování naleznete v tématu [získání sestavení protokoly](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Ve výchozím nastavení je zpráva odeslána na protokolovacího nástroje MSBuild konzoly. To se dá změnit nastavením <xref:Microsoft.Build.Tasks.TaskExtension.Log%2A> parametr. Interpretuje protokolovacího nástroje `Importance` parametr.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu protokoly zprávy a všechny registrované protokolovacích nástrojů.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="DisplayMessages">  
        <Message Text="Project File Name = $(MSBuildProjectFile)" />  
        <Message Text="Project Extension = $(MSBuildProjectExtension)" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)