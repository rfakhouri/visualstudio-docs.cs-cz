---
title: Úloha zprávy | Microsoft Docs
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5efcc41a82cab32172aa395b488535f2777b9e13
ms.sourcegitcommit: 5694c5236fa32ba7f5bc1236a853f725ec7557e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68681160"
---
# <a name="message-task"></a>úloha zprávy
Zaprotokoluje zprávu během sestavení.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `Message` úkolu.

|Parametr|Popis|
|---------------|-----------------|
|`Importance`|Volitelný `String` parametr.<br /><br /> Určuje důležitost zprávy. Tento parametr může mít hodnotu `high` `normal` nebo `low`. Výchozí hodnota je `normal`.|
|`Text`|Volitelný `String` parametr.<br /><br /> Chybový text, který se má protokolovat|

## <a name="remarks"></a>Poznámky
 `Message` Úloha umožňuje[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektům vystavovat zprávy do protokolovacích nástrojů v různých krocích procesu sestavení.

 Pokud se `Condition` parametr vyhodnotí `true`jako `Text` , hodnota parametru se zaprotokoluje a sestavení bude i nadále spuštěno. `Condition` Pokud parametr neexistuje, text zprávy se zaznamená do protokolu. Další informace o protokolování naleznete v tématu [získání protokolů sestavení](../msbuild/obtaining-build-logs-with-msbuild.md).

 Ve výchozím nastavení se zpráva pošle do protokolovacího nástroje konzoly MSBuild. To lze změnit nastavením <xref:Microsoft.Build.Tasks.TaskExtension.Log%2A> parametru. Protokolovací nástroj interpretuje `Importance` parametr. Zpráva nastavená na `high` se obvykle pošle, když je podrobnost protokolovacího nástroje <xref:Microsoft.Build.Framework.LoggerVerbosity> nastavená na `Minimal` nebo vyšší. Zpráva nastavená na `low` je odeslána, když je podrobnost protokolovacího nástroje <xref:Microsoft.Build.Framework.LoggerVerbosity>nastavena na `Detailed`.

 Kromě výše uvedených parametrů Tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, která sama dědí <xref:Microsoft.Build.Utilities.Task> z třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
 Následující příklad kódu protokoluje zprávy do všech registrovaných protokolovacích nástrojů.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="DisplayMessages">
        <Message Text="Project File Name = $(MSBuildProjectFile)" />
        <Message Text="Project Extension = $(MSBuildProjectExtension)" />
    </Target>
    ...
</Project>
```

## <a name="see-also"></a>Viz také:
- [Odkaz na úkol](../msbuild/msbuild-task-reference.md)
- [Získat protokoly sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)