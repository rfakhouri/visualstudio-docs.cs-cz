---
title: Taskextension – základní třída | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, tool task base class
- tool task base class [MSBuild]
ms.assetid: 08bb8059-b7e2-4565-89ba-d9034d4f0e16
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5e39b6a785b6542d95477dec761c1857c4222be
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603206"
---
# <a name="taskextension-base-class"></a>Taskextension – základní třída
Dědí celou řadu úloh <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Tento řetězec dědičnosti přidá několik parametrů do úlohy, které jsou odvozeny z nich. Tyto parametry jsou uvedeny v tomto dokumentu.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry základní třídy.

|Parametr|Popis|
|---------------|-----------------|
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine> parametru.<br /><br /> Určuje rozhraní modul sestavení k dispozici pro úlohy. Stroj sestavení automaticky nastaví tento parametr umožnit, aby zpětné volání do ní úlohy.|
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine2> parametru.<br /><br /> Určuje rozhraní modul sestavení k dispozici pro úlohy. Stroj sestavení automaticky nastaví tento parametr umožnit, aby zpětné volání do ní úlohy.<br /><br /> Toto je vlastnost pohodlí, takže autoři úloh dědění z této třídy nemají k přetypování hodnoty z `IBuildEngine` k `IBuildEngine2`.|
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Volitelné <xref:Microsoft.Build.Framework.IBuildEngine3> parametru.<br /><br /> Určuje rozhraní modul sestavení poskytovány tímto hostitelem.|
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Volitelné <xref:Microsoft.Build.Framework.ITaskHost> parametru.<br /><br /> Určuje instanci objektu hostitele (může mít hodnotu null). Stroj sestavení nastaví tuto vlastnost, pokud hostitel integrovaného vývojového prostředí přidružené k objekt hostitele tuto konkrétní úlohu.|
|<xref:Microsoft.Build.Tasks.TaskExtension.Log%2A>|Volitelné <xref:Microsoft.Build.Utilities.TaskLoggingHelper> parametr jen pro čtení.<br /><br /> Získá `TaskLoggingHelperExtension` objekt, který obsahuje metody protokolování úloh.|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Úlohy](../msbuild/msbuild-tasks.md)