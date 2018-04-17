---
title: Visual Studio projektů a položek parametry šablony | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: c49514aeb164040ea374371cae6a61d1f7eb8948
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="template-parameters"></a>Parametry šablony

Pomocí parametrů v šablonách lze při vytváření instance šablony nahradit hodnoty nejdůležitějších částí šablony, jako jsou názvy tříd a obory názvů. Tyto parametry jsou nahrazovány Průvodce šablonou, která běží na pozadí, když uživatel vybere **OK** nebo **přidat** v **nový projekt** nebo **přidat novou položku**  dialogová okna.

## <a name="declaring-and-enabling-template-parameters"></a>Deklarace a povolení parametry šablony

Parametry šablony jsou deklarovány ve formátu $*parametr*$. Příklad:

- $safeprojectname$

- $ $guid1

- $ $guid5

### <a name="to-enable-parameter-substitution-in-templates"></a>Povolit nahrazení parametrů v šablonách

1. V souboru .vstemplate šablony vyhledejte prvek `ProjectItem`, který odpovídá položce, pro kterou chcete povolit náhradu parametrů.

1. Nastavte `ReplaceParameters` atribut `ProjectItem` element `true`.

1. V souboru kódu pro položku projektu zahrňte odpovídající parametry. Například následující parametr určuje, že název bezpečné projektu používat pro obor názvů v souboru:

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

## <a name="example-using-the-project-name-for-a-file-name"></a>Příklad: Pomocí názvu projektu k názvu souboru

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

## <a name="example-using-the-safe-project-name-for-the-namespace-name"></a>Příklad: Pomocí názvu bezpečné projektu pro obor názvů

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

V souboru .vstemplate šablony projektu, zahrnují `ReplaceParameters="true"` atribut když odkazujete soubor:

```xml
<TemplateContent>
    <ProjectItem ReplaceParameters="true">
        Class1.cs
    </ProjectItem>
    ...
</TemplateContent>
```

## <a name="see-also"></a>Viz také

[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)  
[Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md)