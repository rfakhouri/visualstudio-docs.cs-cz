---
title: Vytváření šablon položek pro Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/02/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- item templates [Visual Studio], creating
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: c5c29dde308c4e3720195924bd40db4e880e4b2e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-item-templates"></a>Postupy: vytváření šablon položek

Tento článek ukazuje, jak vytvořit šablonu položky pomocí **Průvodce exportem šablony**. Pokud vaše šablona se skládají z více souborů, najdete v části [postupy: vytváření šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md).

## <a name="to-add-a-user-item-template-to-the-add-new-item-dialog-box"></a>Chcete-li přidat šablonu položky uživatele do dialogového okna Přidat novou položku

1. Vytvořte nebo otevřete projekt v sadě Visual Studio.

1. Přidání položky do projektu a upravit ho, pokud chcete.

1. Upravte soubor kódu k označení, kde by měl proběhnout nahrazení parametru. Další informace najdete v tématu [postupy: nahrazení parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).

1. Na **projektu** nabídce zvolte **exportovat šablonu**.

1. Na **výběr typu šablony** vyberte **šablony položky**, vyberte projekt, který obsahuje položky a pak zvolte **Další**.

1. Na **vyberte položky, které chcete exportovat** stránky, vyberte položku, kterou chcete vytvořit šablonu pro a potom zvolte **Další**.

1. Na **vyberte odkazy na položku** vyberte odkazy na sestavení do šablony zahrnout, a potom zvolte **Další**.

1. Na **vyberte možnosti šablony** stránky, zadejte název šablony a nepovinný popis, obrázku ikony a náhled obrázku a potom vyberte **Dokončit**.

    Přidání souborů šablony do *.zip* souborů a zkopírovat do adresáře, který jste zadali v průvodci. Výchozí umístění je *%USERPROFILE%\Documents\Visual Studio \<verze\>šablony exportovat \My*.

1. Pokud jste nevybrali možnost **automaticky importovat šablonu do sady Visual Studio** v **Průvodce exportem šablony**, vyhledejte vyexportované šablony. Potom zkopírujte jej do adresáře uživatelů položky šablony. Výchozí umístění je *%USERPROFILE%\Documents\Visual Studio \<verze\>\Templates\ItemTemplates*.

1. Zavřete Visual Studio a pak ho znovu otevřít.

1. Vytvořte nový projekt nebo otevřít existující projekt a zvolte **projektu** > **přidat novou položku** nebo stiskněte klávesu **Ctrl** +  **Posunutí**+**A**.

   Šablony položky se zobrazí v **přidat novou položku** dialogové okno. Pokud jste přidali popis v **Průvodce exportem šablony**, popis se zobrazí na pravé straně dialogového okna.

## <a name="to-enable-the-item-template-to-be-used-in-a-universal-windows-app-project"></a>Chcete-li povolit šablony položky, které mají být použity v projektu univerzální aplikace pro Windows

Průvodce provádí většinu činností, které chcete vytvořit šablonu základní, ale v mnoha případech musíte ručně upravit *.vstemplate* souboru po exportu šablony. Například, pokud chcete položku zobrazit v **přidat novou položku** dialogové okno pro projekt univerzální aplikace pro Windows, je třeba provést několik kroků navíc.

1. Postupujte podle kroků v předchozí části Export šablony položky.

1. Extrahování *.zip* soubor, který vytvořil, a otevřete *.vstemplate* souborů v sadě Visual Studio.

1. Pro projekt C# Universal Windows, přidejte následující kód XML uvnitř `<TemplateData>` element:

   ```xml
   <TemplateID>Microsoft.CSharp.Class</TemplateID>
   ```

1. V sadě Visual Studio, uložte *.vstemplate* souboru a zavřete ho.

1. Zkopírujte a vložte *.vstemplate* zpět do souboru *.zip* souboru.

     Pokud **kopírovat soubor** se zobrazí dialogové okno, vyberte **zkopírujte a nahraďte** možnost.

Nyní můžete přidat položky na základě této šablony do projektu Universal Windows z **přidat novou položku** dialogové okno.

## <a name="to-enable-templates-for-specific-project-subtypes"></a>Chcete-li povolit šablon pro konkrétní projekt podtypů

Můžete zadat, že vaše šablona by se jenom zobrazit u jenom určité projektu podtypů, například Windows, Office, databázi nebo webové.

1. Vyhledejte `ProjectType` element v *.vstemplate* souboru šablony položky.

1. Přidat [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) element ihned po `ProjectType` elementu.

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

## <a name="to-manually-create-an-item-template-without-using-the-export-template-wizard"></a>Ruční vytvoření šablony položky bez použití Průvodce šablony exportu.

V některých případech můžete ručně vytvořit šablonu položky od začátku.

1. Vytvořte projekt a položka projektu.

1. Položka projektu změnit, dokud je připraven k uložit jako šablonu.

1. Upravte soubor kódu k označení, kde nahrazení parametru by měl nastat, pokud kdekoli. Další informace o nahrazení parametru najdete v tématu [postupy: nahrazení parametrů v šabloně.](../ide/how-to-substitute-parameters-in-a-template.md)

1. Vytvořte soubor XML a uložte ho s *.vstemplate* příponu souboru ve stejném adresáři jako soubor položky projektu.

1. Upravit *.vstemplate* soubor XML k poskytnutí metadat šablony položky. Další informace najdete v tématu [odkaz na schéma šablon (rozšiřitelnost)](../extensibility/visual-studio-template-schema-reference.md) a v příkladu v předchozí části.

1. Uložit *.vstemplate* souboru a zavřete ho.

1. V **Průzkumníka Windows**, vyberte soubory, které chcete zahrnout do šablony. Klikněte pravým tlačítkem na výběr a zvolte **poslat** > **komprimované složky (ZIP)**. Do jsou komprimované soubory, které jste vybrali *.zip* souboru.

1. Kopírování *.zip* soubor a vložte ji do umístění šablony položky uživatele. Ve Visual Studio 2017, je výchozí adresář *%USERPROFILE%\Documents\Visual Studio 2017\Templates\ItemTemplates*. Další informace najdete v tématu [postupy: hledání a organizace šablon projektů a položek](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="see-also"></a>Viz také

[Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)  
[Postupy: vytváření šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md)  
[Visual Studio odkaz na schéma šablon (rozšíření)](../extensibility/visual-studio-template-schema-reference.md)
