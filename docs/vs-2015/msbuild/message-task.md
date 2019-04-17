---
title: Zpráva úlohy | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
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
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 48e867cd0993106247f7105c1102f4e1407a4fed
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59662735"
---
# <a name="message-task"></a>Úlohy zpráv
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zaznamená zprávu během sestavení.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Message` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Importance`|Volitelné `String` parametru.<br /><br /> Určuje důležitost zprávy. Tento parametr může mít hodnotu `high`, `normal` nebo `low`. Výchozí hodnota je `normal`.|  
|`Text`|Volitelné `String` parametru.<br /><br /> Text chyby do protokolu.|  
  
## <a name="remarks"></a>Poznámky  
 `Message` Úloha umožňuje [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projekty se mají problém zprávy protokolovacích nástrojů na jiné kroky v procesu sestavení.  
  
 Pokud `Condition` vyhodnotí jako parametr `true`, hodnota `Text` parametr se zaznamenají a sestavení budou i nadále spouštět. Pokud `Condition` neexistuje parametr, se do protokolu zapíše text zprávy. Další informace o protokolování naleznete v tématu [získávání protokolů sestavení](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Ve výchozím nastavení je zpráva odeslána k protokolovací nástroj konzoly nástroje MSBuild. To se dá změnit tak, že nastavíte <xref:Microsoft.Build.Tasks.TaskExtension.Log%2A> parametru. Protokolovací nástroj interpretuje `Importance` parametru.  
  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu zprávy protokolu pro všechna registrovaná protokolovacích nástrojů.  
  
```  
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
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)
