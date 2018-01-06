---
title: "Vytváření šablon vícenásobného projektu pro Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, creating multi-project
- project templates, multi-project
- multi-project templates
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 86952d3b742abf3b73b22e17d695717ca8dac9bd
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-create-multi-project-templates"></a>Postupy: vytváření šablon vícenásobného projektu

Šablony vícenásobných projektů slouží jako kontejnery pro dva nebo více projektů. Když vytvoříte projekt, který je založený na šabloně vícenásobného projektu z **nový projekt** dialogové okno, všechny projekty v šabloně je přidán do řešení.

Šablonu vícenásobného projektu obsahuje dvě nebo více šablon projektu a šablonu kořenové typu `ProjectGroup`.

Šablon vícenásobného projektu chovat jinak než jeden projektu šablony. Mají následující jedinečné vlastnosti:

- Názvy v nelze přiřadit jednotlivých projektů v šabloně vícenásobného projektu **nový projekt** dialogové okno. Místo toho použijte `ProjectName` atributu u `ProjectTemplateLink` element v souboru .vstemplate k zadání názvu pro každý projekt.

- Šablon vícenásobného projektu může obsahovat projekty pro různé jazyky, ale celá samotná šablona může být uvedena pouze v jedné kategorii. Zadejte kategorii šablony v `ProjectType` prvek .vstemplate souboru.

Šablonu vícenásobného projektu musí zahrnovat následující položky, komprimované do souboru .zip:

- Kořenový soubor .vstemplate celý vícenásobného projektu šablony. Tento kořenový soubor .vstemplate obsahuje metadata, která **nový projekt** dialogové okno zobrazí a určuje, kde se mají hledat soubory .vstemplate pro projekty v šabloně. Tento soubor musí být umístěn v kořenovém adresáři souboru ZIP.

- Dvě nebo více složek, které obsahují soubory, které jsou požadovány pro šablonu dokončený projekt. To zahrnuje všechny soubory kódu pro projekt a také soubor .vstemplate pro projekt.

Například soubor .zip vícenásobného projektu šablony, která má dva projekty může mít následující soubory a adresáře:

- MultiProjectTemplate.vstemplate
- \Project1\Project1.vstemplate
- \Project1\Project1.vbproj
- \Project1\Class.vb
- \Project2\Project2.vstemplate
- \Project2\Project2.vbproj
- \Project2\Class.vb

V kořenovém souboru .vstemplate pro šablonu vícenásobného projektu se liší od jednoprojektové šablony následujícími způsoby:

- `Type` Atribut `VSTemplate` element má hodnotu `ProjectGroup` místo `Project`. Příklad:

    ```xml
    <VSTemplate Version="2.0.0" Type="ProjectGroup"
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    ```

- `TemplateContent` Obsahuje element `ProjectCollection` element, který má jeden nebo více `ProjectTemplateLink` prvků, které definují cesty k souborům .vstemplate zahrnutých projektů. Příklad:

    ```xml
    <TemplateContent>
        <ProjectCollection>
            <ProjectTemplateLink>
                Project1\Project1.vstemplate
            </ProjectTemplateLink>
            <ProjectTemplateLink>
                Project2\Project2.vstemplate
            </ProjectTemplateLink>
        </ProjectCollection>
    </TemplateContent>
    ```

## <a name="to-create-a-multi-project-template-from-an-existing-solution"></a>Vytvoření šablony vícenásobného projektu z existujícího řešení

1. Vytvoření řešení a přidejte dva nebo více projektů.

1. Přizpůsobení projektů, dokud nedojde k jejich připraven k exportu do šablony.

1. Na **projektu** nabídce zvolte **exportovat šablonu...** .

   **Průvodce exportem šablony** otevře.

1. Na **výběr typu šablony** vyberte **šablona projektu**. Vyberte projekt, který chcete exportovat do šablony a potom vyberte **Další**.

1. Na **vyberte možnosti šablony** stránky, zadejte název a nepovinný popis, ikona a náhled obrázku pro vaši šablonu. Zvolte **Dokončit**.

   Projekt je exportován do souboru ZIP a umístit do zadané výstupní umístění.

   > [!NOTE]
   > Každý projekt, musí být exportovány do šablony samostatně, takže opakujte předchozí kroky pro každý projekt v řešení.

1. Vytvořte adresář pro vaši šablonu s podadresáři pro každý projekt.

1. Extrahujte obsah souboru ZIP každý projekt do odpovídající podadresáři, kterou jste právě vytvořili.

1. V adresáři základní vytvořte soubor XML s **.vstemplate** příponu souboru. Tento soubor obsahuje metadata pro šablony vícenásobného projektu. Podívejte se na příklad, který následuje pro strukturu souboru. Nezapomeňte zadat relativní cestu k souboru .vstemplate každý projekt.

1. Vyberte adresář, základní a v nabídce klikněte pravým tlačítkem nebo kontextu zvolte **poslat** > **komprimované složky (ZIP)**.

   Soubory a složky jsou komprimovány do souboru ZIP.

1. Zkopírujte soubor ZIP do adresáře uživatele projektu šablony. Ve výchozím nastavení je tento adresář %USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates.

1. V sadě Visual Studio, otevřete **nový projekt** dialogové okno pole a ověřte, zda se šablony zobrazí.

## <a name="two-project-example"></a>Příklad dvou projektu

Tento příklad ukazuje základní kořenový vícenásobného projektu soubor .vstemplate. V tomto příkladu šablona obsahuje dva projekty `My Windows Application` a `My Class Library`. `ProjectName` Atributu u `ProjectTemplateLink` element určuje název, který je přiřazen k projektu.

> [!TIP]
> Pokud `ProjectName` atribut nezadá, název souboru .vstemplate slouží jako název projektu.

```xml
<VSTemplate Version="2.0.0" Type="ProjectGroup"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-Project Template Sample</Name>
        <Description>An example of a multi-project template</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectCollection>
            <ProjectTemplateLink ProjectName="My Windows Application">
                WindowsApp\MyTemplate.vstemplate
            </ProjectTemplateLink>
            <ProjectTemplateLink ProjectName="My Class Library">
                ClassLib\MyTemplate.vstemplate
            </ProjectTemplateLink>
        </ProjectCollection>
    </TemplateContent>
</VSTemplate>
```

## <a name="example-with-solution-folders"></a>Příklad se složkami řešení

Tento příklad používá `SolutionFolder` elementu, který chcete rozdělit do dvou skupin, projektů `Math Classes` a `Graphics Classes`. Šablona obsahuje čtyři projekty, dvě z nich jsou umístěny ve složce každé řešení.

```xml
<VSTemplate Version="2.0.0" Type="ProjectGroup"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-Project Template Sample</Name>
        <Description>An example of a multi-project template</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectCollection>
            <SolutionFolder Name="Math Classes">
                <ProjectTemplateLink ProjectName="MathClassLib1">
                    MathClassLib1\MyTemplate.vstemplate
                </ProjectTemplateLink>
                <ProjectTemplateLink ProjectName="MathClassLib2">
                    MathClassLib2\MyTemplate.vstemplate
                </ProjectTemplateLink>
            </SolutionFolder>
            <SolutionFolder Name="Graphics Classes">
                <ProjectTemplateLink ProjectName="GraphicsClassLib1">
                    GraphicsClassLib1\MyTemplate.vstemplate
                </ProjectTemplateLink>
                <ProjectTemplateLink ProjectName="GraphicsClassLib2">
                    GraphicsClassLib2\MyTemplate.vstemplate
                </ProjectTemplateLink>
            </SolutionFolder>
        </ProjectCollection>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také

[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Postupy: vytváření šablon projektu](../ide/how-to-create-project-templates.md)  
[Visual Studio odkaz na schéma šablon (rozšíření)](../extensibility/visual-studio-template-schema-reference.md)  
[SolutionFolder – element (šablony sady Visual Studio)](../extensibility/solutionfolder-element-visual-studio-templates.md)  
[ProjectTemplateLink – element (šablony sady Visual Studio)](../extensibility/projecttemplatelink-element-visual-studio-templates.md)
