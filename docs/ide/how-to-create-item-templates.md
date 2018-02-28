---
title: "Vytváření šablon položek pro Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8fd5d7fba092df5accfaad9d26cfc05f196981ba
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="how-to-create-item-templates"></a>Postupy: vytváření šablon položek

Toto téma ukazuje, jak vytvořit šablonu položky pomocí **Průvodce exportem šablony**. Pokud vaše šablona se skládají z více souborů, najdete v části [postupy: vytváření šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md).

## <a name="to-add-a-user-item-template-to-the-add-new-item-dialog-box"></a>Chcete-li přidat šablonu položky uživatele do dialogového okna Přidat novou položku

1. Vytvořte nebo otevřete projekt v sadě Visual Studio.

1. Přidání položky do projektu a upravit ho, pokud chcete.

1. Upravte soubor kódu k označení, kde by měl proběhnout nahrazení parametru. Další informace najdete v tématu [postupy: nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).

1. Na **projektu** nabídce zvolte **exportovat šablonu...** .

1. Na **výběr typu šablony** vyberte **šablony položky**, vyberte projekt, který obsahuje položky a pak zvolte **Další**.

1. Na **vyberte položky, které chcete exportovat** stránky, vyberte položku, kterou chcete vytvořit šablonu pro a potom zvolte **Další**.

1. Na **vyberte odkazy na položku** vyberte odkazy na sestavení do šablony zahrnout, a potom zvolte **Další**.

1. Na **vyberte možnosti šablony** stránky, zadejte název šablony a nepovinný popis, obrázku ikony a náhled obrázku a potom vyberte **Dokončit**.

    Soubory pro šablonu jsou přidány do souboru ZIP a zkopírovat do adresáře, který jste zadali v průvodci. Výchozí umístění je %USERPROFILE%\Documents\Visual Studio \<verze\>\My Export šablony.

1. Pokud jste nevybrali možnost **automaticky importovat šablonu do sady Visual Studio** v **Průvodce exportem šablony**, vyhledejte vyexportované šablony a zkopírujte jej do adresáře uživatelů položky šablony. Výchozí umístění je %USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ItemTemplates.

1. Zavřete Visual Studio a pak ho znovu otevřít.

1. Vytvořte nový projekt nebo otevřít existující projekt a zvolte **projektu** > **přidat novou položku...**  nebo stiskněte klávesu **Ctrl** + **Shift** + **A**.

   Šablony položky se zobrazí v **přidat novou položku** dialogové okno. Pokud jste přidali popis v **Průvodce exportem šablony**, popis se zobrazí na pravé straně dialogového okna.

## <a name="to-enable-the-item-template-to-be-used-in-a-universal-windows-app-project"></a>Chcete-li povolit šablony položky, které mají být použity v projektu univerzální aplikace pro Windows

Průvodce nepodporuje většinu činností, které chcete vytvořit šablonu základní, ale v mnoha případech musíte ručně upravit soubor .vstemplate po exportu šablony. Například, pokud chcete položku zobrazit v **přidat novou položku** dialogové okno pro projekt univerzální aplikace pro Windows, je třeba provést několik kroků navíc.

1. Postupujte podle kroků v předchozí části Export šablony položky.

1. Rozbalte soubor .zip, který byl vytvořen a otevřete soubor .vstemplate v sadě Visual Studio.

1. Pro projekt C# Universal Windows, přidejte následující kód XML uvnitř `<TemplateData>` element:

   ```xml
   <TemplateID>Microsoft.CSharp.Class</TemplateID>
   ```

1. V sadě Visual Studio .vstemplate soubor uložte a zavřete ho.

1. Zkopírujte a vložte soubor .vstemplate zpět do souboru ZIP.

     Pokud **kopírovat soubor** se zobrazí dialogové okno, vyberte **zkopírujte a nahraďte** možnost.

Nyní můžete přidat položky na základě této šablony do projektu Universal Windows z **přidat novou položku** dialogové okno.

## <a name="to-enable-templates-for-specific-project-subtypes"></a>Chcete-li povolit šablon pro konkrétní projekt podtypů

Můžete zadat, že vaše šablona by se jenom zobrazit u jenom určité projektu podtypů, například Windows, Office, databázi nebo webové.

1. ProjectType – element vyhledejte v souboru .vstemplate položky šablony.

1. Přidat [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) element ihned po ProjectType – element.

1. Hodnota textového elementu nastavte na jedno z následujících hodnot:

    - Windows
    - Office
    - Databáze
    - Web

Příklad: `<ProjectSubType>Database</ProjectSubType>`.

Následující příklad ukazuje šablony položky pro **Office** projekty.

```xml
<VSTemplate Version="2.0.0" Type="Item" Version="2.0.0">
   <TemplateData>
      <Name>Class</Name>
      <Description>An empty class file</Description>
      <Icon>Class.ico</Icon>
      <ProjectType>CSharp</ProjectType>
      <ProjectSubType>Office</ProjectSubType>
      <DefaultName>Class.cs</DefaultName>
   </TemplateData>
   <TemplateContent>
      <ProjectItem>Class1.cs</ProjectItem>
   </TemplateContent>
</VSTemplate>
```

## <a name="to-manually-create-an-item-template-without-using-the-export-template-wizard"></a>Ruční vytvoření šablony položky bez použití Průvodce exportem šablony

V některých případech můžete ručně vytvořit šablonu položky od začátku.

1. Vytvořte projekt a položka projektu.

1. Položka projektu změnit, dokud je připraven k uložit jako šablonu.

1. Upravte soubor kódu k označení, kde nahrazení parametru by měl nastat, pokud kdekoli. Další informace o nahrazení parametru najdete v tématu [postup: Substitute parametrů v šabloně.](../ide/how-to-substitute-parameters-in-a-template.md)

1. Vytvořte soubor XML a uložit s příponou souboru .vstemplate ve stejném adresáři jako soubor položky projektu.

1. Upravte soubor XML .vstemplate k poskytnutí metadat šablony položky. Další informace najdete v tématu [odkaz na schéma šablon (rozšiřitelnost)](../extensibility/visual-studio-template-schema-reference.md) a v příkladu v předchozí části.

1. .Vstemplate soubor uložte a zavřete ho.

1. V Průzkumníku Windows, vyberte soubory, které chcete do šablony zahrnout, klikněte pravým tlačítkem na výběr a zvolte **poslat** > **komprimované složky (ZIP)**. Do souboru .zip jsou komprimované soubory, které jste vybrali.

1. Zkopírujte soubor .zip a vložte ji do umístění šablony položky uživatele. V aplikaci Visual Studio 2017 je výchozí adresář %USERPROFILE%\Documents\Visual Studio 2017\Templates\ItemTemplates. Další informace najdete v tématu [postupy: vyhledání a uspořádání šablon projektů a položek](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Viz také

[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Postupy: Tvorba šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md)  
[Odkaz na schéma šablon sady Visual Studio (rozšíření)](../extensibility/visual-studio-template-schema-reference.md)
