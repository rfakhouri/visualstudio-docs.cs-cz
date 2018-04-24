---
title: Vytváření šablon vícenásobného projektu pro Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, creating multi-project
- project templates, multi-project
- multi-project templates
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: b3902dd2b6f4dfac72d61d2c4d81937dcbbfdd07
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-multi-project-templates"></a>Postupy: vytváření šablon vícenásobného projektu

Šablony vícenásobných projektů slouží jako kontejnery pro dva nebo více projektů. Když vytvoříte projekt, který je založený na šabloně vícenásobného projektu z **nový projekt** dialogové okno, všechny projekty v šabloně je přidán do řešení.

Šablona vícenásobného projektu má dvě nebo více šablon projektu a šablonu kořenové typu `ProjectGroup`.

Šablon vícenásobného projektu chovat jinak než jeden projektu šablony. Mají následující jedinečné vlastnosti:

- Názvy v nelze přiřadit jednotlivých projektů v šabloně vícenásobného projektu **nový projekt** dialogové okno. Místo toho použijte `ProjectName` atributu u `ProjectTemplateLink` element v *.vstemplate* souboru k zadání názvu pro každý projekt.

- Šablon vícenásobného projektu může obsahovat projekty pro různé jazyky, ale celá samotná šablona může být uvedena pouze v jedné kategorii. Zadejte kategorii šablony v `ProjectType` element *.vstemplate* souboru.

Šablonu vícenásobného projektu musí zahrnovat následující položky, komprimované do *.zip* souboru:

- Kořenové *.vstemplate* soubor pro celou šablonu vícenásobného projektu. Tohoto kořenového adresáře *.vstemplate* soubor obsahuje metadata, která **nový projekt** dialogové okno zobrazí a určuje, kde najít *.vstemplate* soubory pro projekty v Šablona. Musí být tento soubor nachází v kořenovém adresáři *.zip* souboru.

- Dvě nebo více složek, které obsahují soubory, které jsou požadovány pro šablonu dokončený projekt. Složky zahrnují všechny soubory kódu pro projekt a také *.vstemplate* soubor projektu.

Například šablonu vícenásobného projektu *.zip* soubor, který má dva projekty může mít následující soubory a adresáře:

- *MultiProjectTemplate.vstemplate*
- *\Project1\Project1.vstemplate*
- *\Project1\Project1.vbproj*
- *\Project1\Class.vb*
- *\Project2\Project2.vstemplate*
- *\Project2\Project2.vbproj*
- *\Project2\Class.vb*

Kořenové *.vstemplate* soubor pro šablonu vícenásobného projektu se liší od jednoprojektové šablony následujícími způsoby:

- `Type` Atribut `VSTemplate` element má hodnotu `ProjectGroup` místo `Project`. Příklad:

    ```xml
    <VSTemplate Version="2.0.0" Type="ProjectGroup"
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    ```

- `TemplateContent` Obsahuje element `ProjectCollection` element, který má jeden nebo více `ProjectTemplateLink` prvky, které definují cest k *.vstemplate* souborů zahrnutých projektů. Příklad:

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

1. Na **projektu** nabídce zvolte **exportovat šablonu**.

   **Průvodce exportem šablony** otevře.

1. Na **výběr typu šablony** vyberte **šablona projektu**. Vyberte projekt, který chcete exportovat do šablony a potom vyberte **Další**.

1. Na **vyberte možnosti šablony** stránky, zadejte název a nepovinný popis, ikona a náhled obrázku pro vaši šablonu. Zvolte **Dokončit**.

   Projekt je exportován do *.zip* souborů a jejich umísťování v zadané výstupní umístění.

   > [!NOTE]
   > Každý projekt, musí být exportovány do šablony samostatně, takže opakujte předchozí kroky pro každý projekt v řešení.

1. Vytvořte adresář pro vaši šablonu s podadresáři pro každý projekt.

1. Extrahujte obsah každý projekt *.zip* soubor do odpovídající podadresáři, kterou jste vytvořili.

1. V adresáři základní vytvořte soubor XML s *.vstemplate* příponu souboru. Tento soubor obsahuje metadata pro šablony vícenásobného projektu. Podívejte se na příklad, který následuje pro strukturu souboru. Nezapomeňte zadat relativní cestu do každého projektu *.vstemplate* souboru.

1. Vyberte adresář, základní a v nabídce klikněte pravým tlačítkem nebo kontextu zvolte **poslat** > **komprimované složky (ZIP)**.

   Soubory a složky jsou komprimovány do *.zip* souboru.

1. Kopírování *.zip* soubor do adresáře uživatele projektu šablony. Ve výchozím nastavení je tento adresář *%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ProjectTemplates*.

1. V sadě Visual Studio, otevřete **nový projekt** dialogové okno pole a ověřte, zda se šablony zobrazí.

## <a name="two-project-example"></a>Příklad dvou projektu

Tento příklad ukazuje základní kořenové vícenásobného projektu *.vstemplate* souboru. V tomto příkladu šablony má dva projekty `My Windows Application` a `My Class Library`. `ProjectName` Atributu u `ProjectTemplateLink` element určuje název, který je přiřazen k projektu.

> [!TIP]
> Pokud `ProjectName` atribut nezadá, název *.vstemplate* soubor se používá jako název projektu.

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

Tento příklad používá `SolutionFolder` elementu, který chcete rozdělit do dvou skupin, projektů `Math Classes` a `Graphics Classes`. Šablona má čtyři projekty, dvě z nich jsou umístěny ve složce každé řešení.

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
