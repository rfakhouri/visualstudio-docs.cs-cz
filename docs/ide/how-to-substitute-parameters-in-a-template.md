---
title: Přidání názvu parametrů do šablony projektů a položek
ms.date: 01/02/2018
ms.topic: conceptual
helpviewer_keywords:
- template parameters
- template parameters, substituting
- Visual Studio templates, using parameters
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cf9a990be3f5e87180967a4f9f274ec79fbc357e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946877"
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Postupy: Nahrazení parametrů v šabloně

Parametry šablony umožňují nahradit identifikátory, jako jsou názvy tříd a obory názvů, když se vytvoří soubor ze šablony. Můžete přidat parametry šablony do stávající šablony, nebo vytvořit vlastní šablony s parametry šablony.

Parametry šablony jsou napsané ve formátu $*parametr*$. Úplný seznam parametrů šablony, najdete v části [parametry šablony](../ide/template-parameters.md).

Následující části se dozvíte, jak upravit šablonu, která nahradit název oboru názvů s názvem"bezpečné projektu".

## <a name="example---namespace-name"></a>Příklad: název oboru názvů

1. Vložte parametr v jednom nebo více souborů s kódem v šabloně. Příklad:

    ```csharp
    namespace $safeprojectname$
    ```

1. V *vstemplate* soubor šablony, vyhledejte `ProjectItem` element, který obsahuje tento soubor.

1. Nastavte `ReplaceParameters` atribut `true` pro `ProjectItem` element:

    ```xml
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>
    ```

## <a name="see-also"></a>Viz také:

- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [ProjectItem – element (šablony sady Visual Studio položky)](../extensibility/projectitem-element-visual-studio-item-templates.md)