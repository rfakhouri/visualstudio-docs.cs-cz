---
title: Parametry šablony projektů a položek
ms.date: 01/02/2018
ms.topic: reference
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 90035e99c13484bd1b49e59350489ed1090b5f4e
ms.sourcegitcommit: 673b9364fc9a96b027662dcb4cf5d61cab60ef11
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/21/2019
ms.locfileid: "69891272"
---
# <a name="template-parameters"></a>Parametry šablony

Při vytváření instance šablony, můžete v šabloně nahraďte hodnoty. Chcete-li nastavit tuto funkci, použijte *parametry šablony*. Parametry šablony lze použít k nahrazení hodnoty, jako jsou názvy tříd a obory názvů v šabloně. Průvodce šablonou, která běží na pozadí, když uživatel přidá nová položka nebo projektu nahradí tyto parametry.

## <a name="declare-and-enable-template-parameters"></a>Deklarace a povolení parametrů šablony

Parametry šablon jsou deklarovány ve formátu $*parametr*$. Příklad:

- $safeprojectname$

- $guid1$

- $guid5$

### <a name="enable-parameter-substitution-in-templates"></a>Povolit substituci parametrů v šablonách

1. V *.vstemplate* soubor šablony, vyhledejte `ProjectItem` element, který odpovídá položce, pro kterou chcete povolit náhradu parametrů.

1. Nastavte `ReplaceParameters` atribut `ProjectItem` elementu `true`.

1. V souboru kódu pro položku projektu zahrnují parametry, kde je to vhodné. Například následující parametr určuje, že se používá bezpečný název projektu pro obor názvů v souboru:

    ```csharp
    namespace $safeprojectname$
    ```

## <a name="reserved-template-parameters"></a>Vyhrazené parametry šablon

Následující tabulka uvádí seznam rezervovaných parametrů šablony, které mohou být použity libovolnou šablonou:

|Parametr|Popis|
|---------------|-----------------|
|clrversion|Aktuální verze modulu common language runtime (CLR).|
|ext_*|`ext_` Přidejte předponu do libovolného parametru pro odkazování na proměnné nadřazené šablony. Například, `ext_safeprojectname`.|
|identifikátor GUID [1-10]|GUID, který se používá k nahrazení identifikátoru GUID projektu v souboru projektu. Můžete zadat až 10 jedinečných identifikátorů GUID (například `guid1`).|
|Název položky|Název souboru, ve kterém se parametr používá|
|MachineName|Aktuální název počítače (například Computer01).|
|název projektu|Jméno, které uživatel zadal při vytvoření projektu.|
|RegisteredOrganization|Hodnotu klíče registru z HKLM\Software\Microsoft\Windows NT\CurrentVersion\RegisteredOrganization.|
|RootNamespace|Kořenový obor názvů aktuálního projektu. Tento parametr platí pouze pro šablony položek.|
|safeitemname|Stejné jako `itemname` ale všechny nezabezpečené znaky a mezery nahrazují znaky podtržítka.|
|safeitemrootname|Stejné jako `safeitemname`.|
|safeprojectname|Název zadaný uživatelem při vytvoření projektu, ale všechny nezabezpečené znaky a mezery byly odebrány.|
|čas|Aktuální čas ve formátu DD/MM/RRRR 00:00:00.|
|SpecificSolutionName|Název řešení. Pokud je zaškrtnuto políčko „vytvořit adresář řešení“, `SpecificSolutionName` obsahuje název řešení. Pokud není zaškrtnuto políčko „vytvořit adresář řešení“, `SpecificSolutionName` je prázdné.|
|USERDOMAIN|Aktuální uživatel domény.|
|uživatelské jméno|Aktuální uživatelské jméno.|
|webnamespace|Název aktuální webové stránky. Tento parametr se používá v šabloně webového formuláře zajistit jedinečné názvy tříd. Pokud webová stránka se v kořenovém adresáři webového serveru, tento parametr šablony přeloží do kořenového adresáře na webovém serveru.|
|Rok|Aktuální rok ve formátu RRRR.|

> [!NOTE]
> Parametry šablony jsou malá a velká písmena.

## <a name="custom-template-parameters"></a>Parametry vlastní šablony

Můžete určit vlastní parametry a hodnoty šablony, kromě vyhrazených výchozích parametrů šablony, které se používají při nahrazení parametru. Další informace najdete v tématu [CustomParameters – element (šablony sady Visual Studio)](../extensibility/customparameters-element-visual-studio-templates.md).

## <a name="example-use-the-project-name-for-a-file-name"></a>Příklad: Pro název souboru použít název projektu

Můžete zadat různé názvy souborů pro položky projektu pomocí parametru `TargetFileName` atribut.

Následující příklad určuje, že název spustitelného souboru používá název projektu, určené `$projectname$`.

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

## <a name="example-use-the-safe-project-name-for-the-namespace-name"></a>Příklad: Použijte název bezpečného projektu pro název oboru názvů.

Pokud chcete použít bezpečný název projektu pro obor názvů v souboru třídy C#, použijte následující syntaxi:

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

V *.vstemplate* soubor šablony projektu, zahrnují `ReplaceParameters="true"` atribut při odkazování na soubor:

```xml
<TemplateContent>
    <ProjectItem ReplaceParameters="true">
        Class1.cs
    </ProjectItem>
    ...
</TemplateContent>
```

## <a name="see-also"></a>Viz také:

- [Postupy: Nahrazení parametrů v šabloně](how-to-substitute-parameters-in-a-template.md)
- [Přizpůsobení šablony](../ide/customizing-project-and-item-templates.md)
- [Postupy: Vytvoření šablon projektů](../ide/how-to-create-project-templates.md)
- [Odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
