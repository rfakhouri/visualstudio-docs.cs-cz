---
title: "Postupy: vytváření šablon položek s více soubory | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, creating multi-file item templates
- multi-file item templates
- item templates, creating multi-file item templates
ms.assetid: fe3c4257-e383-4c80-b8af-c5c521959c33
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e3e1f6c6e62494f040e2f52180c5588688f460db
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-multi-file-item-templates"></a>Postupy: Tvorba šablon položek s více soubory
Šablony položek může určovat jenom jednu položku, ale v některých případech se položka se skládá z více souborů. Například šablonu položky Windows Forms v jazyce Visual Basic vyžaduje následující tři soubory:  
  
-   VB soubor, který obsahuje kód pro formulář.  
  
-   A. Designer.vb, který obsahuje informace o návrháři pro daný formulář.  
  
-   Soubor .resx, která obsahuje vložené prostředky pro daný formulář.  
  
 Šablony položek s více soubory vyžadují parametry zajistit správné přípony se používají při vytváření položky v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Pokud vytvoříte pomocí šablony položky **exportovat šablonu** průvodce, tyto parametry se automaticky vygenerují a žádné další úpravy se vyžaduje. Následující kroky popisují, jak používat parametry zajistit, že jsou vytvořeny správné přípony.  
  
### <a name="to-manually-create-a-multi-file-item-template"></a>Chcete ručně vytvořit šablonu položek s více soubory  
  
1.  Vytvoření šablony položky způsobem jako šablonu položky jeden soubor. Další informace najdete v tématu [postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md).  
  
2.  Přidat `TargetFileName` atributy ke každému `ProjectItem` elementu. Nastavte hodnoty `TargetFileName` atributy na $fileinputname$. *FileExtension*, kde *FileExtension* je soubor příponu názvu souboru, který bude zahrnut v šabloně. Příklad:  
  
    ```  
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
  
     Když je položka odvozená z této šablony se přidá do projektu, názvy souborů se podle názvu, který uživatel zadal v **přidat novou položku** dialogové okno.  
  
3.  Vyberte soubory, které chcete zahrnout do vaší šablony, klikněte pravým tlačítkem na výběr, klikněte na **odeslat**a potom klikněte na **komprimované složky (ZIP)**. Do souboru .zip jsou komprimované soubory, které jste vybrali.  
  
4.  Umístěte soubor .zip do umístění šablony položky uživatele. Ve výchozím nastavení, adresář je Documents\Visual Studio *verze*\Templates\ItemTemplates\\. Další informace najdete v tématu [postupy: vyhledání a uspořádání šablony](../ide/how-to-locate-and-organize-project-and-item-templates.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Windows Forms šablony. Při vytváření položky na základě této šablony zadaný v název bude shodovat s názvy tři soubory vytvořené **přidat novou položku** dialogové okno.  
  
```  
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
 [Postupy: vytváření šablon položek](../ide/how-to-create-item-templates.md)   
 [Parametry šablony](../ide/template-parameters.md)   
 [Postupy: nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md)