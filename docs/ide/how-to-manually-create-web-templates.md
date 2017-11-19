---
title: "Postupy: ruční vytvoření webových šablon | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
ms.assetid: 731c4027-a152-48c5-bfc4-93490bf1949f
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5d5f34e421160e8cca56897e6530ff47da7b1a84
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-manually-create-web-templates"></a>Postupy: Ruční vytvoření webových šablon
Vytvoření šablony se liší od vytvoření jiných druhů šablony. Protože šablony webových projektů zobrazeny **přidat nový web** dialogové okno a položky projektu webové jsou klasifikovány podle programovací jazyk, musíte zadat šablonu jako šablonu a identifikovat programování souboru .vstemplate jazyk.  
  
> [!NOTE]
>  Webové šablony musí obsahovat prázdný .webproj soubor, který je zadán pomocí `File` atribut `Project` elementu. I když webové projekty nevyžadují soubory projektu, tento soubor je vyžadován, že šablonu pracuje správně.  
  
### <a name="to-manually-create-a-web-template"></a>Chcete-li ručně vytvořit šablonu  
  
1.  Vytváření webového projektu.  
  
2.  Upravit nebo odstranit soubory v projektu nebo přidejte nové soubory do projektu.  
  
3.  Vytvořte soubor XML a uložte ji pomocí příponu názvu souboru .vstemplate ve stejném adresáři jako projektu. Nepřidávejte jej do projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
4.  Autor .vstemplate soubor XML k poskytnutí metadat šablony projektu. Další informace podívejte se na příklad v následující části.  
  
5.  Vyhledejte `ProjectType` element v souboru .vstemplate a nastavte hodnotu na text `Web`.  
  
6.  Následující `ProjectType` elementu, přidejte `ProjectSubType` elementu a nastavte textovou hodnotu na programovací jazyk šablony. Programovací jazyk může být jedna z následujících hodnot:  
  
    -   CSharp  
  
    -   VisualBasic  
  
     Příklad:  
  
    ```  
    <TemplateData>  
        ...  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        ...  
    </TemplateData>  
    ```  
  
7.  Vyberte soubory, které ve vaší šabloně (to zahrnuje soubor .vstemplate), klikněte pravým tlačítkem na výběr, klikněte na **odeslat**a potom klikněte na **komprimované složky (ZIP)**. Soubory jsou komprimovány do souboru ZIP.  
  
8.  Vložte soubor .zip šablony do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adresáře šablony projektu. Ve výchozím nastavení, je tento adresář Documents\Visual Studio *verze*šablony exportovat \My\\.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje základní .vstemplate soubor pro šablonu webového projektu.  
  
```  
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
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)