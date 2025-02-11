---
title: 'Postupy: Řídicí znaky v nástroji MSBuild | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- special characters, escaping
- characters, escapes
- escape characters
- MSBuild, escaping special characters
ms.assetid: 1aa3669c-1647-4960-b770-752e2532102f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 983e10f26e6fd1d8b4b7ff18c73edd65cb4810f4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62968103"
---
# <a name="how-to-escape-special-characters-in-msbuild"></a>Postupy: Speciální řídicí znaky v nástroji MSBuild

Některé znaky mají speciální význam v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory projektu. Příklady znaků středníky (`;`) a hvězdičky (`*`). Úplný seznam těchto speciálních znaků, naleznete v tématu [speciální znaky nástroje MSBuild](../msbuild/msbuild-special-characters.md).

Chcete-li použít tyto speciální znaky jako literály v souboru projektu, se musí zadat pomocí syntaxe `%<xx>`, kde `<xx>` představuje znak šestnáctkové hodnoty ASCII.

## <a name="msbuild-special-characters"></a>Speciální znaky nástroje MSBuild

Jedna je například použití speciálních znaků v `Include` atribut položky seznamů. Například následující seznam položek deklaruje dvě položky: *MyFile.cs* a *MyClass.cs*.

```xml
<Compile Include="MyFile.cs;MyClass.cs"/>
```

Pokud chcete deklarovat, který obsahuje středníkem v názvu položky, je nutné použít `%<xx>` syntaxe řídicí středník a zabránit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] z deklarace dvou samostatných položek. Například následující položka řídicí sekvence středník a deklaruje jednu položku s názvem `MyFile.cs;MyClass.cs`.

```xml
<Compile Include="MyFile.cs%3BMyClass.cs"/>
```

Můžete také použít [vlastnost funkce](../msbuild/property-functions.md) řídicí řetězce. Například to je ekvivalentní k výše uvedený příklad.

```xml
<Compile Include="$([MSBuild]::Escape('MyFile.cs;MyClass.cs'))" />
```

### <a name="to-use-an-msbuild-special-character-as-a-literal-character"></a>Chcete-li použít speciální znak MSBuild jako literální znak

Použijte notaci `%<xx>` místo speciální znaky, kde `<xx>` představuje šestnáctkovou hodnotu znaku standardu ASCII. Například použijte hvězdičku (`*`) jako literální znak, použijte hodnotu `%2A`.

## <a name="see-also"></a>Viz také:
- [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
- [MSBuild](../msbuild/msbuild.md)
- [Položky](../msbuild/msbuild-items.md)
