---
title: Vytváření webových šablon
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 21c44587d3398313993e0e65bb32b1dbbbb98dc2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54955918"
---
# <a name="how-to-manually-create-web-templates"></a>Postupy: Ruční vytvoření webových šablon

Vytvoření šablony webu se liší od vytvoření jiných typů šablon. Vzhledem k tomu, že šablony webových projektů se zobrazí v **přidat nový web** dialogové okno a webového projektu položky jsou zařazené do kategorií pomocí programovacího jazyka, *vstemplate* souboru musíte určit, která šablona jako šablonu a identifikovat programovací jazyk.

> [!NOTE]
> Webové šablony musí obsahovat prázdnou *.webproj* souboru a musí se odkazovat v *vstemplate* soubor `File` atribut `Project` element. I když se nevyžadují žádné webové projekty *souborů .proj* souboru projektu, je potřeba vytvořit tento soubor zástupné procedury pro šablony webové zajištění správného fungování.

## <a name="to-manually-create-a-web-template"></a>Ruční vytvoření webových šablon

1. Vytvoření webového projektu.

2. Upravit nebo odstranit soubory v projektu nebo přidejte nové soubory do projektu.

3. Vytvořte soubor XML a uložit ji *vstemplate* příponu názvu souboru ve stejném adresáři jako váš projekt. Nepřidávejte jej do projektu v sadě Visual Studio.

4. Upravit *vstemplate* soubor XML k poskytování metadat šablony projektu. Další informace najdete v tématu [příkladu, který následuje](#example).

5. Vyhledejte `ProjectType` prvek *vstemplate* souboru a nastavit textové hodnoty `Web`.

6. Následující `ProjectType` elementu, přidejte `ProjectSubType` elementu a nastaví hodnotu text pro programovací jazyk šablony. Programovací jazyk může být jeden z následujících hodnot:

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

7. Vyberte soubory v šabloně (jedná se o *vstemplate* souboru), klikněte pravým tlačítkem na výběr a zvolte **odeslat** > **komprimovanou složku (ZIP)**. Soubory jsou komprimované do *ZIP* souboru.

8. Vložit *ZIP* soubor šablony v adresáři projektu šablony sady Visual Studio. Ve výchozím nastavení, je tento adresář *%USERPROFILE%\Documents\Visual Studio \<verze\>\ProjectTemplates*.

## <a name="example"></a>Příklad

Následující příklad ukazuje základní *vstemplate* Šablona webového projektu v souboru:

```xml
<VSTemplate Version="2.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple web template</Description>
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

## <a name="see-also"></a>Viz také:

- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Visual Studio odkaz na schéma šablon (rozšiřitelnost)](../extensibility/visual-studio-template-schema-reference.md)
