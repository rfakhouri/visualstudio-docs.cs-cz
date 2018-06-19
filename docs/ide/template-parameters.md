---
title: Visual Studio projektů a položek parametry šablony
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: abac68ff371040a7f121a885065c8c3eaf9af8ff
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2018
ms.locfileid: "32066531"
---
# <a name="template-parameters"></a>Parametry šablony

V šabloně můžete nahradit hodnoty při vytváření instance šablony. Chcete-li tuto funkci nastavit, použijte *parametry šablony*. Parametry šablony můžete použít k nahrazení hodnot, jako jsou názvy tříd a obory názvů v šabloně. Průvodce šablonou, která se spouští na pozadí při přidání nové položky nebo projektu nahradí tyto parametry.

## <a name="declaring-and-enabling-template-parameters"></a>Deklarace a povolení parametry šablony

Parametry šablony jsou deklarovány ve formátu $*parametr*$. Příklad:

- $safeprojectname$

- $ $guid1

- $ $guid5

### <a name="to-enable-parameter-substitution-in-templates"></a>Povolit nahrazení parametrů v šablonách

1. V *.vstemplate* soubor šablony, vyhledejte `ProjectItem` element, který odpovídá položce, pro který chcete povolit nahrazení parametru.

1. Nastavte `ReplaceParameters` atribut `ProjectItem` element `true`.

1. V souboru kódu pro položku projektu zahrňte odpovídající parametry. Například následující parametr určuje, že je název bezpečné projektu používá pro obor názvů v souboru:

    ```csharp
    namespace $safeprojectname$
    ```

## <a name="reserved-template-parameters"></a>Vyhrazené parametry šablon

Následující tabulka uvádí parametry vyhrazené šablony, které můžete používat všechny šablony.

|Parametr|Popis|
|---------------|-----------------|
|clrversion|Aktuální verze common language runtime (CLR).|
|identifikátor GUID [1 – 10]|Identifikátor GUID, používá k nahrazení identifikátoru GUID projektu v souboru projektu. Můžete zadat až 10 jedinečné identifikátory GUID (například `guid1`).|
|Název položky|Název zadaný uživatelem v **přidat novou položku** dialogové okno.|
|MachineName|Aktuální název počítače (například Computer01).|
|název projektu|Název zadaný uživatelem v **nový projekt** dialogové okno.|
|RegisteredOrganization|Hodnota klíče registru z HKLM\Software\Microsoft\Windows NT\CurrentVersion\RegisteredOrganization.|
|RootNamespace|Kořenový obor názvů aktuálního projektu. Tento parametr platí pouze pro šablony položek.|
|safeitemname|Název zadaný uživatelem v **přidat novou položku** dialogové okno, se všemi nebezpečné znaky a odebrány mezery.|
|safeprojectname|Název zadaný uživatelem v **nový projekt** dialogové okno, se všemi nebezpečné znaky a odebrány mezery.|
|čas|Aktuální čas ve formátu DD/MM/RRRR 00:00:00.|
|SpecificSolutionName|Název řešení. Pokud je zaškrtnuto políčko „vytvořit adresář řešení“, `SpecificSolutionName` obsahuje název řešení. Pokud není zaškrtnuto políčko „vytvořit adresář řešení“, `SpecificSolutionName` je prázdné.|
|USERDOMAIN|Aktuální uživatel domény.|
|Uživatelské jméno|Aktuální uživatelské jméno.|
|webnamespace|Název aktuální webové stránky. Tento parametr se používá v šabloně webové formuláře zaručit jedinečné názvy tříd. Pokud webová stránka je v kořenovém adresáři webového serveru, tento parametr šablony přeloží na kořenový adresář webového serveru.|
|Rok|Ve formátu RRRR do aktuálního roku.|

> [!NOTE]
> Parametry šablony rozlišují velká a malá písmena.

## <a name="custom-template-parameters"></a>Parametry vlastní šablony

Můžete zadat vlastní parametry šablony a hodnoty, kromě vyhrazené výchozí parametry šablony, které se používají při nahrazení parametru. Další informace najdete v tématu [CustomParameters – element (šablony sady Visual Studio)](../extensibility/customparameters-element-visual-studio-templates.md).

## <a name="example-use-the-project-name-for-a-file-name"></a>Příklad: Použití názvu projektu k názvu souboru

Můžete zadat různé názvy souborů pro položky projektu pomocí parametru v `TargetFileName` atribut.

Následující příklad určuje, že název spustitelného souboru používá jako název projektu určeného `$projectname$`.

```xml
<TemplateContent>
    <ProjectItem
        ReplaceParameters="true"
        TargetFileName="$projectname$.exe">
            File1.exe
    </ProjectItem>
      ...
</TemplateContent>
```

## <a name="example-use-the-safe-project-name-for-the-namespace-name"></a>Příklad: Použijte název bezpečné projektu pro obor názvů

Pokud chcete použít název bezpečné projektu pro obor názvů v souboru třídy jazyka C#, použijte následující syntaxi:

```csharp
namespace $safeprojectname$
{
    public class Class1
    {
        public Class1()
        { }
    }
}
```

V *.vstemplate* souboru šablony projektu, zahrnují `ReplaceParameters="true"` atribut když odkazujete soubor:

```xml
<TemplateContent>
    <ProjectItem ReplaceParameters="true">
        Class1.cs
    </ProjectItem>
    ...
</TemplateContent>
```

## <a name="see-also"></a>Viz také

- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md)
