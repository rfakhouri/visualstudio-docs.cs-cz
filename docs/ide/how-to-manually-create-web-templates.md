---
title: Vytvoření webových šablon pro Visual Studio
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: aeaeea5ee4d1d8e65cdc13ca11192a70e0459be1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-manually-create-web-templates"></a>Postupy: ruční vytvoření webových šablon

Vytvoření šablony se liší od vytvoření jiných druhů šablony. Protože šablony webových projektů zobrazují v **přidat nový web** dialogové okno a webového projektu položky, které jsou klasifikovány podle programovacího jazyka *vstemplate* soubor musí určit šablonu jako šablonu a identifikovat programovací jazyk.

> [!NOTE]
> Webové šablony musí obsahovat prázdnou *.webproj* soubor a musí být odkazováno v *vstemplate* v soubor `File` atribut `Project` element. I když webové projekty nevyžadují *.proj* soubor projektu, je nutné k vytvoření tohoto souboru se zakázaným inzerováním pro šablonu webových fungovat správně.

## <a name="to-manually-create-a-web-template"></a>Chcete-li ručně vytvořit šablonu

1. Vytváření webového projektu.

1. Upravit nebo odstranit soubory v projektu nebo přidejte nové soubory do projektu.

1. Vytvořte soubor XML a uložte ho s *vstemplate* příponu názvu souboru ve stejném adresáři jako projektu. Nepřidávejte jej do projektu v sadě Visual Studio.

1. Upravit *vstemplate* soubor XML k poskytnutí metadat šablony projektu. Další informace najdete v tématu [příklad, který následuje](#example).

1. Vyhledejte `ProjectType` element v *vstemplate* souborů a nastavte ji na hodnotu text `Web`.

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

1. Vyberte soubory, které ve vaší šabloně (to zahrnuje *vstemplate* soubor), klikněte pravým tlačítkem na výběr a zvolte **poslat** > **komprimované složky (ZIP)**. Soubory jsou komprimované do *.zip* souboru.

1. Umístit *.zip* soubor šablony v adresáři projektu šablony sady Visual Studio. Ve výchozím nastavení je tento adresář *%USERPROFILE%\Documents\Visual Studio \<verze\>\ProjectTemplates*.

## <a name="example"></a>Příklad

Následující příklad ukazuje základní *vstemplate* Šablona webového projektu v souboru:

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

- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Visual Studio odkaz na schéma šablon (rozšíření)](../extensibility/visual-studio-template-schema-reference.md)