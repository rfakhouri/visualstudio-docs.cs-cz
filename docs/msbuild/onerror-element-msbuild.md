---
title: Onerror – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#OnError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- OnError Element [MSBuild]
- <OnError Element [MSBuild]
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ff783c76595e1cc79d2520a4e27f5afa01b0a978
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62964063"
---
# <a name="onerror-element-msbuild"></a>Onerror – element (MSBuild)
Způsobí, že jeden nebo více cílů ke spuštění, pokud `ContinueOnError` atribut je `false` neúspěšné úlohy.

 \<Projekt > \<cíl > \<onerror – >

## <a name="syntax"></a>Syntaxe

```xml
<OnError ExecuteTargets="TargetName"
    Condition="'String A'=='String B'" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|
|`ExecuteTargets`|Požadovaný atribut.<br /><br /> Cílů ke spuštění neúspěšné úlohy. Několik cílů oddělte středníky. Několik cílů jsou spuštěny v uvedeném pořadí.|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

| Prvek | Popis |
| - | - |
| [Cíl](../msbuild/target-element-msbuild.md) | Prvek kontejneru pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy. |

## <a name="remarks"></a>Poznámky
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Spustí `OnError` element, pokud jeden z `Target` elementu úlohy nezdaří a zobrazí se `ContinueOnError` atribut nastaven na `ErrorAndStop` (nebo `false`). Pokud úloha selže, cíle zadané v `ExecuteTargets` atribut je proveden. Pokud existuje více než jeden `OnError` element v cíli, `OnError` prvky jsou spouštěny postupně, pokud se úloha nezdaří.

 Informace o tom, `ContinueOnError` atributu naleznete v tématu [Task – element (MSBuild)](../msbuild/task-element-msbuild.md). Informace o cílech naleznete v tématu [cíle](../msbuild/msbuild-targets.md).

## <a name="example"></a>Příklad
 Následující kód se provádí `TaskOne` a `TaskTwo` úlohy. Pokud `TaskOne` selže, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vyhodnotí `OnError` elementu a spustí `OtherTarget` cíl.

```xml
<Target Name="ThisTarget">
    <TaskOne ContinueOnError="ErrorAndStop">
    </TaskOne>
    <TaskTwo>
    </TaskTwo>
    <OnError ExecuteTargets="OtherTarget" />
</Target>
```

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
- [Cíle](../msbuild/msbuild-targets.md)
