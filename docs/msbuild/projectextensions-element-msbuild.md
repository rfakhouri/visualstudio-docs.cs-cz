---
title: Projectextensions – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ProjectExtensions
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ProjectExtensions> element [MSBuild]
- ProjectExtensions element [MSBuild]
ms.assetid: f95f312f-ff92-41eb-9469-ad99e236a307
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 318ca02899632fb4499010cc348f73379a2a562d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002409"
---
# <a name="projectextensions-element-msbuild"></a>Projectextensions – element (MSBuild)
Umožňuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory tak, aby obsahovala jinou hodnotu než projektu[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] informace. Cokoli uvnitř sady `ProjectExtensions` element se bude ignorovat ve [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].

 \<Project> \<ProjectExtensions>

## <a name="syntax"></a>Syntaxe

```xml
<ProjectExtensions>
    Non-MSBuild information to include in file.
</ProjectExtensions>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

| Prvek | Popis |
| - | - |
| [Projekt](../msbuild/project-element-msbuild.md) | Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu. |

## <a name="remarks"></a>Poznámky
 Pouze jeden `ProjectExtensions` může být použit element v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje informace z integrovaného vývojového prostředí uložené v `ProjectExtensions` elementu.

```xml
<ProjectExtensions>
    <VSIDE>
        <External>
            <!--
            Raw XML passed to the IDE by an external source
            -->
        </External>
    </VSIDE>
</ProjectExtensions>
```

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
- [MSBuild](../msbuild/msbuild.md)
