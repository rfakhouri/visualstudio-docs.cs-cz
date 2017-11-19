---
title: "Postupy: vytváření šablon položek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project item templates, XML reference
- project item templates, custom template locations
- project item templates, creating
- project item templates, metadata files
ms.assetid: 77bc53d4-d607-4820-a032-7e3b365891b5
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2ecd17694e65c6273f8e73a321a72bc209038922
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-item-templates"></a>Postupy: Vytváření šablon položek
Kroky v [první postup](../ide/how-to-create-item-templates.md#export_template) v tomto tématu popisují, jak vytvořit šablonu položky pomocí **exportovat šablonu** průvodce. Pokud vaše šablona se skládají z více souborů, najdete v části [postupy: vytváření šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md).  

 Průvodce nepodporuje velké množství pracovních vytvořit základní šablony, ale v mnoha případech je nutné ručně upravit soubor .vstemplate po exportu šablony. Například, pokud chcete položku zobrazit v **přidat novou položku** dialogové okno pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] projekt aplikace, budete muset provést několik kroků navíc. [Druhé postup](../ide/how-to-create-item-templates.md#modify_template) v tomto tématu vám dá tento úkol provést pomůže.  

 Chcete-li zadat, aby vaše šablona by měla pouze pro jenom určité dílčí typy projektů, jako je Office, databáze nebo Web, přečtěte si téma [v této části](#enable_templates).  

 V některých případech může má nebo muset ručně vytvořit šablonu položky od začátku. [Třetí postup](../ide/how-to-create-item-templates.md#create_template) ukazuje, jak to udělat.  

 Najdete v článku [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md) informace o prvky, které lze použít v souboru .vstemplate.  

### <a name="to-add-a-custom-project-item-template-to-the-add-new-item-dialog-box"></a>Chcete-li přidat šablonu vlastních projektů položky do dialogového okna Přidat novou položku  

1.  Vytvořit nebo otevřít projekt v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  

2.  Přidání položky do projektu, pokud chcete změnit.  

3.  Upravte soubor kódu k označení, kde by měl proběhnout nahrazení parametru. Další informace najdete v tématu [postup: Substitute parametrů v šabloně](../ide/how-to-substitute-parameters-in-a-template.md).  

4.  Na **projektu** nabídky, klikněte na tlačítko **exportovat šablonu**.  

5.  Klikněte na tlačítko **šablony položky**, vyberte projekt, který obsahuje položku a klikněte na tlačítko **Další**.  

6.  Vyberte položku, pro který chcete vytvořit šablonu a klikněte na tlačítko **Další**.  

7.  Vyberte odkazy na sestavení do šablony zahrnout, a klikněte na **Další**.  

8.  Zadejte název souboru ikony, náhled obrázku, název šablony a popis šablony a klikněte na tlačítko **Dokončit**.  

     Soubory šablony jsou přidány do souboru ZIP a zkopírovat ať adresáře, zadejte v dialogovém okně. Výchozí umístění je **... \Users\\< uživatelské jméno\>\Documents\Visual Studio \<verze > šablony pro export \My\\**  složky.  

    > [!WARNING]
    >  V dřívějších verzích sady Visual Studio, výchozím umístěním je **... \Users\\< uživatelské jméno\>\Documents\Visual Studio \<verze > \Templates\ItemTemplates**.  

### <a name="to-enable-the-item-template-to-be-used-in-a-store-project"></a>Chcete-li povolit šablony položky, které mají být použity v projektu úložiště  

1.  Postupujte podle kroků v postupu výše pro export šablony položky.  

2.  Extrahujte soubor .vstemplate ze souboru .zip, který byl zkopírován do... \Users\\*uživatelské jméno*\Documents\Visual Studio *verze*\Templates\ItemTemplates\ (nebo **Export šablony**) složky.  

3.  Otevřete soubor .vstemplate v sadě Visual Studio.  

4.  Pro Universal Windows C# projektu v souboru .vstemplate, přidejte následující kód XML v rámci otevření `<TemplateData>` značky: `<TemplateID>Microsoft.CSharp.Class</TemplateID>`. 

    Pro Windows 8.1 uložení projektu C#, v souboru .vstemplate, přidejte následující kód XML v rámci otevření a zavření `<TemplateData>` značky: `<TemplateGroupID>WinRT-Managed</TemplateGroupID>`.  

    Úložiště projektu C++ Windows 8.1 používá hodnotu `WinRT-Native-6.3`. Windows 10 a jiné typy projektů najdete v tématu [templategroupid – Element (šablony sady Visual Studio)](../extensibility/templategroupid-element-visual-studio-templates.md).  

    Následující příklad ukazuje celý obsah souboru .vstemplate po řádku kódu XML `<TemplateGroupID>WinRT-Managed</TemplateGroupID>` přidala do ní. V tomto příkladu je specifická pro projekty C#. Můžete upravit <ProjectTpe> a \< [templategroupid –](../extensibility/templategroupid-element-visual-studio-templates.md)> elementy k určení dalších typů jazyka a projekt.  

    ```xml  
    <VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
      <TemplateData>  
        <DefaultName>MyItemStoreTemplate.xaml</DefaultName>  
        <Name>MyItemStoreTemplate</Name>  
        <Description>This is an example itemtemplate</Description>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>10</SortOrder>  
        <Icon>__TemplateIcon.ico</Icon>  
        <TemplateGroupID>WinRT-Managed</TemplateGroupID>  
      </TemplateData>  
      <TemplateContent>  
        <References />  
        <ProjectItem SubType="Designer" TargetFileName="$fileinputname$.xaml" ReplaceParameters="true">MyItemTemplate.xaml</ProjectItem>  
        <ProjectItem SubType="Code" TargetFileName="$fileinputname$.xaml.cs" ReplaceParameters="true">MyItemTemplate.xaml.cs</ProjectItem>  
      </TemplateContent>  
    </VSTemplate>  
    ```  

     Další možné templategroupid – hodnoty, najdete v části [templategroupid – Element (šablony sady Visual Studio)](../extensibility/templategroupid-element-visual-studio-templates.md)). Odkaz na dokončení .vstemplate naleznete v části [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)  

5.  V sadě Visual Studio .vstemplate soubor uložte a zavřete ho.  

6.  Zkopírujte a vložte soubor .vstemplate zpět do souboru ZIP, který je umístěný v... \Users\\*uživatelské jméno*\Documents\Visual Studio *verze*\Templates\ItemTemplates\ složky.  

     Pokud **kopírovat soubor** se zobrazí dialogové okno, vyberte **zkopírujte a nahraďte** možnost.  

 Nyní můžete přidat položky na základě této šablony do [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] projektu pomocí **přidat novou položku** dialogové okno.  

 Další informace o názvy parametrů najdete v tématu [parametry šablony](../ide/template-parameters.md).  
  
 
### <a name="enable_templates"></a>Chcete-li povolit šablon pro konkrétní dílčí typy projektů  

1.  Vývojové prostředí umožňuje zpřístupnit položky projektu z dialogového okna Přidat položku pro určité projekty. Pomocí tohoto postupu zpřístupnit vlastní položky pro Windows, Web, Office nebo databázové projekty.  

     ProjectType – element vyhledejte v souboru .vstemplate položky šablony.  

     Přidat [ProjectSubType](../extensibility/projectsubtype-element-visual-studio-templates.md) element ihned po ProjectType – element.  

2.  Hodnota textového elementu nastavte na jedno z následujících hodnot:  

    1.  Windows  

    2.  Office  

    3.  Databáze  

    4.  Web  

     Příklad: `<ProjectSubType>Database</ProjectSubType>`.  

     Následující příklad ukazuje šablony položky, která je k dispozici pro projekty Office.  

    ```  
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

### <a name="to-manually-create-an-item-template-without-using-the-export-template-wizard"></a>Ruční vytvoření šablony položky bez použití Průvodce šablony exportu.  

1.  Vytvořte projekt a položka projektu.  

2.  Položka projektu změnit, dokud je připraven k uložit jako šablonu.  

3.  Podle potřeby upravte soubor kódu k označení, kde má probíhat nahrazení parametru. Další informace o nahrazení parametru najdete v tématu [postup: Substitute parametrů v šabloně.](../ide/how-to-substitute-parameters-in-a-template.md)

4.  Vytvořte soubor XML a uložte ji pomocí příponu názvu souboru .vstemplate ve stejném adresáři jako novou šablonu položky.  

5.  Autor .vstemplate soubor XML k poskytnutí metadat šablony položky. Další informace najdete v tématu [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md) a v příkladu v předchozí části.  

6.  .Vstemplate soubor uložte a zavřete ho.  

7.  V Průzkumníku Windows vyberte soubory, které chcete do šablony zahrnout, klikněte pravým tlačítkem na výběr, klikněte na tlačítko Odeslat a potom klikněte na komprimované složky. Do souboru .zip jsou komprimované soubory, které jste vybrali.  

8.  Zkopírujte soubor .zip a vložte ji do umístění šablony položky uživatele. Ve Visual Studio 2017 je výchozí adresář... \Users\\< uživatelské jméno\>\Documents\Visual Studio 2017\Templates\ItemTemplates\\. Další informace najdete v tématu Postupy: vyhledání a uspořádání šablon projektů a položek.  

## <a name="see-also"></a>Viz také  
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Postupy: vytváření šablon položek s více soubory](../ide/how-to-create-multi-file-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
