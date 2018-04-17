---
title: Vytvoření webových šablon pro Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: dca5d5439b18fdb377dfe530af81331dd6e5c3fa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-manually-create-web-templates"></a>Postupy: ruční vytvoření webových šablon

Vytvoření šablony se liší od vytvoření jiných druhů šablony. Protože šablony webových projektů zobrazeny **přidat nový web** dialogové okno a položky projektu webové jsou klasifikovány podle programovací jazyk, musíte zadat šablonu jako šablonu a identifikovat programování souboru .vstemplate jazyk.

> [!NOTE]
> Webové šablony musí obsahovat soubor prázdný .webproj a musí být odkazovány v souboru .vstemplate v `File` atribut `Project` elementu. I když webové projekty nevyžadují. \*proj soubor projektu, je nutné k vytvoření tohoto souboru se zakázaným inzerováním pro šablonu webových fungovat správně.

### <a name="to-manually-create-a-web-template"></a>Chcete-li ručně vytvořit šablonu

1. Vytváření webového projektu.

1. Upravit nebo odstranit soubory v projektu nebo přidejte nové soubory do projektu.

1. Vytvořte soubor XML a uložit s příponou názvu souboru .vstemplate ve stejném adresáři jako projektu. Nepřidávejte jej do projektu v sadě Visual Studio.

1. Upravte soubor XML .vstemplate k poskytnutí metadat šablony projektu. Další informace najdete v tématu [příklad, který následuje](#example).

1. Vyhledejte `ProjectType` element v souboru .vstemplate a nastavte hodnotu na text `Web`.

1. Následující `ProjectType` elementu, přidejte `ProjectSubType` elementu a nastavte textovou hodnotu na programovací jazyk šablony. Programovací jazyk může být jedna z následujících hodnot:

    - CSharp
    - VisualBasic

    Příklad:

    ```xml
    <TemplateData>
        ...
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        ...
    </TemplateData>
    ```

1. Vyberte soubory v této šabloně (to zahrnuje soubor .vstemplate), klikněte pravým tlačítkem na výběr a zvolte **poslat** > **komprimované složky (ZIP)**. Soubory jsou komprimovány do souboru ZIP.

1. Soubor .zip šablony uvést v adresáři projektu šablony sady Visual Studio. Ve výchozím nastavení je tento adresář %USERPROFILE%\Documents\Visual Studio \<verze\>\ProjectTemplates.

## <a name="example"></a>Příklad

Následující příklad ukazuje základní .vstemplate soubor pro šablonu projektu:

```xml
<VSTemplate Version="2.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple Web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také

[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Odkaz na schéma šablon sady Visual Studio (rozšíření)](../extensibility/visual-studio-template-schema-reference.md)