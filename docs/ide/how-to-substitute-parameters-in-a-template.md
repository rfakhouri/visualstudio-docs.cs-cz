---
title: Přidání parametrů název šablon projektů a položek v sadě Visual Studio
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- template parameters
- template parameters, substituting
- Visual Studio templates, using parameters
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 26802b7b5293fd43eb1546290560c5300c360003
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945932"
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Postupy: nahrazení parametrů v šabloně

Parametry šablony umožňují nahradit identifikátory například názvy tříd a obory názvů, když dojde k vytvoření souboru ze šablony. Můžete přidat parametry šablony do stávající šablony, nebo vytvořit vlastní šablony s parametry šablony.

Parametry šablony jsou zapsány ve formátu $*parametr*$. Úplný seznam parametrů šablony, najdete v části [parametry šablony](../ide/template-parameters.md).

Následující části se dozvíte, jak upravit šablonu, která má nahradit název oboru názvů s názvem"bezpečné projektu".

## <a name="to-use-a-parameter-to-replace-the-namespace-name"></a>Pomocí parametru nahradit název oboru názvů

1. Vložte parametr v jednom nebo více souborů kódu v šabloně. Příklad:

    ```csharp
    namespace $safeprojectname$
    ```

1. V *vstemplate* souboru šablony, vyhledejte `ProjectItem` element, který obsahuje tento soubor.

1. Nastavte `ReplaceParameters` atribut `true` pro `ProjectItem` element:

    ```xml
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>
    ```

## <a name="see-also"></a>Viz také

- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [ProjectItem – element (šablony sady Visual Studio položky)](../extensibility/projectitem-element-visual-studio-item-templates.md)