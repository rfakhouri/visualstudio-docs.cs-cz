---
title: Vytváření šablon položek s více soubory pro sadu Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, creating multi-file item templates
- multi-file item templates
- item templates, creating multi-file item templates
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: d80c0a604455d8c6e76d9c55bdf3a0d2dacfe743
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-multi-file-item-templates"></a>Postupy: vytváření šablon položek s více soubory

Šablony položek může určovat jenom jednu položku, ale v některých případech se položka se skládá z více souborů. Například šablonu položky Windows Forms vyžaduje následující tři soubory:

- Soubor, který obsahuje kód pro formulář

- Soubor, který obsahuje informace o návrháři pro daný formulář

- Soubor, který obsahuje vložené prostředky pro daný formulář

Šablony položek s více soubory vyžadují parametry k zajištění toho, že správný soubor rozšíření se používají při vytváření položky. Pokud vytvoříte šablonu položek s více soubory pomocí **Průvodce exportem šablony**, tyto parametry se automaticky vygenerují a žádné další úpravy se vyžaduje.

## <a name="to-create-a-multi-file-item-template-by-using-the-export-template-wizard"></a>Vytvoření šablony položek s více soubory pomocí šablony Průvodce exportem

Můžete vytvořit šablonu položek s více soubory stejným způsobem, jako šablonu položky jeden soubor. V tématu [postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md). Na **vyberte položky, které chcete exportovat** stránku průvodce, vyberte soubor, který má závislé soubory (například soubor ve formátu Windows Forms). Průvodce automaticky zahrne závislé soubory, jako je například designer a soubory prostředků v šabloně.

## <a name="to-manually-create-a-multi-file-item-template"></a>Chcete ručně vytvořit šablonu položek s více soubory

1. Vytvoření šablony položky, jako jste by ručně vytvořit šablonu položky jedním souborem, ale zahrnout každý soubor, který představuje položek s více soubory.

1. V souboru XML .vstemplate, přidejte `ProjectItem` element pro každého uživatele souboru a přidejte `TargetFileName` atributu do tohoto elementu. Nastavte hodnotu `TargetFileName` atribut $fileinputname$. *FileExtension*, kde *FileExtension* je příponu souboru, který bude zahrnut v šabloně. Příklad:

    ```xml
    <ProjectItem TargetFileName="$fileinputname$.vb">
        Form1.vb
    </ProjectItem>
    <ProjectItem TargetFileName="$fileinputname$.Designer.vb">
        Form1.Designer.vb
    </ProjectItem>
    <ProjectItem TargetFileName="$fileinputname$.resx">
        Form1.resx
    </ProjectItem>
    ```

     > [!NOTE]
     > Když je položka odvozená z této šablony se přidá do projektu, názvy souborů odvodí z název, který uživatel zadá **přidat novou položku** dialogové okno.

1. Vyberte soubory, které chcete zahrnout v šabloně, klikněte pravým tlačítkem na výběr a zvolte **poslat** > **komprimované složky (ZIP)**.

   Do souboru .zip jsou komprimované soubory, které jste vybrali.

1. Zkopírujte soubor .zip do umístění šablony položky uživatele. Ve výchozím nastavení, adresář je %USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ItemTemplates. Další informace najdete v tématu [postupy: vyhledání a uspořádání šablony](../ide/how-to-locate-and-organize-project-and-item-templates.md).

1. Zavřete Visual Studio a pak ho znovu otevřít.

1. Vytvořte nový projekt nebo otevřít existující projekt a zvolte **projektu** > **přidat novou položku...**  nebo stiskněte klávesu **Ctrl** + **Shift** + **A**.

   Šablony položek s více soubory se zobrazí v **přidat novou položku** dialogové okno.

## <a name="example"></a>Příklad

Následující příklad ukazuje šablonu Windows Forms. Při vytváření položky na základě této šablony zadaný v název bude shodovat s názvy tři soubory vytvořené **přidat novou položku** dialogové okno.

```xml
<VSTemplate Version="2.0.0" Type="Item"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-file Item Template</Name>
        <Icon>Icon.ico</Icon>
        <Description>An example of a multi-file item template</Description>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectItem TargetFileName="$fileinputname$.vb" SubType="Form">
            Form1.vb
        </ProjectItem>
        <ProjectItem TargetFileName="$fileinputname$.Designer.vb">
            Form1.Designer.vb
        </ProjectItem>
        <ProjectItem TargetFileName="$fileinputname$.resx">
            Form1.resx
        </ProjectItem>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také

[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Postupy: Vytváření šablon položek](../ide/how-to-create-item-templates.md)  
[Parametry šablony](../ide/template-parameters.md)  
[Postupy: Nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md)