---
title: "Vytváření položek šablony a šablony projektů pro položky projektu služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, creating custom templates
- .spdata files
- projects [SharePoint development in Visual Studio], creating custom templates
- SharePoint projects, creating custom templates
- SharePoint development in Visual Studio, creating custom project and item templates
- project items [SharePoint development in Visual Studio], creating custom templates
ms.assetid: c95b5e35-76c4-4f0a-b645-0467ae683659
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e7ea1c76cda46313458dcac01b415e7541732a26
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-item-templates-and-project-templates-for-sharepoint-project-items"></a>Vytváření šablon položek a projektů pro položky projektu služby SharePoint
  Když definujete vlastní typu položky projektu služby SharePoint, můžete přidružit pomocí šablony položky nebo šablona projektu tak, aby ostatní vývojáři mohou použít položka projektu v sadě Visual Studio. Můžete také vytvořit průvodce pro šablony.  
  
 Například Visual Studio nezahrnuje projektu šablony nebo šablony položky pro přidání pole na web služby SharePoint. Můžete definovat typu položky projektu služby SharePoint, která představuje pole a pak vytvořit šablonu položky, které ostatní vývojáři mohou použít k přidání položky pole do projektu služby SharePoint. Nebo můžete vytvořit šablony projektu, takže vývojáři můžou vytvářet nové projektu služby SharePoint, který obsahuje položky pole. V obou případech můžete zadat taky průvodce, který se zobrazí, když vývojáři pomocí šablony. Tento průvodce může shromažďovat informace z vývojářům konfigurovat novou položku nebo projektu.  
  
 Šablony položek a projektů jsou soubory .zip, které obsahují soubory, které se používají Visual Studio k vytvoření položky projektu nebo projektu. Další informace o základní informace o šablon položek a projektů najdete v tématu [vytváření projektů a šablon položek](/visualstudio/ide/creating-project-and-item-templates).  
  
##  <a name="creatingitemtemplates"></a>Vytváření šablon položek  
 Když vytvoříte šablonu položky pro položky projektu služby SharePoint, nejsou některé soubory, které jsou vždy požadované a volitelné soubory, které by mohly používat určitých typů položek projektu. Návod, které ukazuje, jak k definování typu položky projektu služby SharePoint a vytvořit šablonu položky pro něj najdete v tématu [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  
  
 Následující tabulka uvádí požadované soubory k vytvoření šablony položky pro položky projektu služby SharePoint.  
  
|Požadovaný soubor|Popis|  
|-------------------|-----------------|  
|Soubor .spdata|Toto je soubor XML, který určuje obsah a výchozí chování položky projektu. Tento soubor musí být součástí šablony položky. Další informace o obsahu soubory .spdata najdete v tématu [referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md).|  
|Soubor .vstemplate.|Tento soubor poskytuje informace potřebné k zobrazení šablony v sadě Visual Studio **přidat novou položku** dialogové okno a vytvoření položky projektu ze šablony. Tento soubor musí být součástí šablony položky. Další informace najdete v tématu [soubory metadat šablony Visual Studio](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961).|  
|Rozšíření sestavení sady Visual Studio, který implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní.|Toto sestavení definuje chování běhu položky projektu. Toto sestavení musí být součástí balíčku VSIX pomocí šablony položky. Další informace najdete v tématu [definování vlastní SharePoint typů položek projektu](../sharepoint/defining-custom-sharepoint-project-item-types.md) a [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).|  
  
 Následující tabulka uvádí některé z nejběžnějších volitelné soubory, které můžou být součástí šablony položky. Některé typy položek projektu může vyžadovat další soubory, které zde nejsou uvedeny.  
  
|Volitelný soubor|Popis|  
|-------------------|-----------------|  
|Elements.XML|A *element funkce* souboru. Tento soubor definuje uživatelského rozhraní a chování přizpůsobení vytvořená položka projektu. Každý typ vlastního nastavení, jako je například seznam instancí, typy obsahu nebo vlastní akce má jiné schéma, které definuje obsah tohoto souboru. Další informace najdete v tématu [stavebním blokem: funkce](http://go.microsoft.com/fwlink/?LinkId=169183) a [funkce schémata](http://go.microsoft.com/fwlink/?LinkId=169192).|  
|Schema.XML|Soubor schématu pro seznam definic. Další informace najdete v tématu [stavebním blokem: seznamy a knihovny dokumentů](http://go.microsoft.com/fwlink/?LinkId=177792) a [Schema.xml](http://go.microsoft.com/fwlink/?LinkId=177793).|  
|.WebPart|A *webovou část definice* souboru. Tento soubor obsahuje nastavení vlastností pro webové části. Další informace najdete v tématu [stavebním blokem: webové části](http://go.microsoft.com/fwlink/?LinkId=177791).|  
|.ascx|Soubor ASP.NET UserControl. Tento soubor definuje uživatelské rozhraní Visual webové části.|  
|.aspx|Soubor stránky ASP.NET. Tento soubor obsahuje kód XML, který definuje stránky aplikace.|  
|soubory CS nebo VB|Tyto soubory kódu zadejte chování při přizpůsobení SharePoint, které mají programovací model, který je přístupný z Visual C# nebo kód jazyka Visual Basic, například stránky aplikací, webové části a pracovních postupů.|  
  
## <a name="creating-project-templates"></a>Vytváření šablon projektů  
 Když vytvoříte šablonu projektu služby SharePoint, nejsou některé soubory, které jsou vždy požadované a volitelné soubory, které by mohly používat určité typy projektů. Projekty SharePoint obvykle obsahovat alespoň jednu položku projektu služby SharePoint. Není to však vyžaduje. Můžete třeba definovat šablonu projektu služby SharePoint, která má být použit pouze k nasazení řešení služby SharePoint, které jsou vytvořené v jiné projekty.  
  
 Návod, které ukazuje, jak k definování typu položky projektu služby SharePoint a vytvořit šablona projektu pro něj najdete v tématu [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).  
  
 Následující tabulka uvádí soubory, které musí být součástí šablona projektu služby SharePoint.  
  
|Požadovaný soubor|Popis|  
|-------------------|-----------------|  
|Soubor .vstemplate|Tento soubor poskytuje informace potřebné k zobrazení šablony v sadě Visual Studio **nový projekt** dialogové okno a vytvořte projekt ze šablony. Další informace najdete v tématu [soubory metadat šablony Visual Studio](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961).|  
|Soubor csproj nebo VBPROJ|Toto je soubor projektu. Definuje obsah a nastavení konfigurace projektu.|  
|Package.Package|Tento soubor definuje balíčku pro nasazení pro projekt. Při přizpůsobení balíčku řešení pro váš projekt pomocí návrháře balíčků, Visual Studio ukládá data o balíčku pro řešení v tomto souboru.<br /><br /> Když vytvoříte vlastní šablona projektu služby SharePoint, doporučujeme, abyste zahrnete jen minimální požadovaná obsah v souboru Package.package a nakonfigurovat pomocí rozhraní API v balíčku řešení <xref:Microsoft.VisualStudio.SharePoint.Packages> oboru názvů v rozšíření, které je přidružená k šabloně projektu. Pokud to uděláte, vaše šablona projektu je chráněný před budoucími změnami na strukturu Package.package souboru. Příklad, který ukazuje, jak vytvořit soubor Package.package se jenom minimálně obsahu, najdete v části [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).<br /><br /> Pokud chcete upravit soubor Package.package přímo, můžete ověřit obsah, pomocí schéma v % Program Files (11.0\Xml\Schemas\PackageModelSchema.xsd x86)%\Microsoft Visual Studio.|  
|Package.Template.xml|Tento soubor poskytuje základ pro řešení v souboru manifestu (manifest.xml) balíčku řešení SharePoint (WSP), aby se vygenerovala z projektu. Obsah můžete přidat do tohoto souboru, pokud chcete zadat některé chování, která není určená změnit, a uživatelé typ vašeho projektu. Další informace najdete v tématu [stavebním blokem: řešení](http://go.microsoft.com/fwlink/?LinkId=169186) a [řešení schématu](http://go.microsoft.com/fwlink/?LinkId=177794).<br /><br /> Při sestavování řešení balíčků z projektu sady Visual Studio sloučí obsah Package.package a soubor manifestu Package.Template.xml soubory do řešení. Další informace o vytváření balíčků řešení najdete v tématu [postupy: vytvoření balíčku řešení služby SharePoint (wsp)](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b).|  
  
 Následující tabulka uvádí volitelné soubory, které můžou být součástí šablona projektu.  
  
|Volitelný soubor|Popis|  
|-------------------|-----------------|  
|SharePoint – položky projektu|Můžete zahrnout jeden nebo více souborů .spdata, které definují typů položek projektu služby SharePoint. Každý soubor .spdata musí mít odpovídající <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> implementace v rozšíření sestavení, které je součástí balíčku VSIX pomocí šablony projektu. Další informace najdete v tématu [vytváření šablon položek](#creatingitemtemplates).<br /><br /> Projekty SharePoint obvykle obsahovat alespoň jednu položku projektu služby SharePoint. Není to však vyžaduje.|  
|*featureName*.feature|Tento soubor definuje funkce služby SharePoint, která slouží k seskupení několik položek projektu pro nasazení. Při použití návrháře funkce pro přizpůsobení funkce ve vašem projektu, Visual Studio ukládá data o funkci v tomto souboru. Pokud chcete seskupit položky projektu do různých funkcí, můžete zahrnout více .feature souborů.<br /><br /> Když vytvoříte vlastní šablona projektu služby SharePoint, doporučujeme, abyste zahrnout pouze minimální požadovaný obsah do každého souboru .feature, a nakonfigurovat pomocí rozhraní API v funkce <xref:Microsoft.VisualStudio.SharePoint.Features> oboru názvů v rozšíření, které je přidružen Šablona projektu. Pokud to uděláte, vaše šablona projektu je chráněný před budoucími změnami na strukturu .feature souboru. Příklad, který ukazuje, jak vytvořit soubor .feature se jenom minimálně obsahu, najdete v části [návod: vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).<br /><br /> Pokud chcete změnit soubor .feature přímo, můžete ověřit obsah, pomocí schéma v % Program Files (11.0\Xml\Schemas\FeatureModelSchema.xsd x86)%\Microsoft Visual Studio.|  
|*featureName*. Template.XML|Tento soubor poskytuje základ pro souboru manifestu funkce (souboru funkce.XML) pro jednotlivé funkce, které se generují z projektu. Obsah můžete přidat do tohoto souboru, pokud chcete zadat některé chování, která není určená změnit, a uživatelé typ vašeho projektu. Další informace najdete v tématu [stavebním blokem: funkce](http://go.microsoft.com/fwlink/?LinkId=169183) a [souboru funkce.xml](http://go.microsoft.com/fwlink/?LinkId=177795) soubory.<br /><br /> Při sestavování řešení balíčků z projektu sady Visual Studio sloučí obsah každý pár *featureName*.feature souboru a *featureName*. Template.XML soubory do souboru manifestu funkce. Další informace o vytváření balíčků řešení najdete v tématu [postupy: vytvoření balíčku řešení služby SharePoint (wsp)](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b).|  
  
## <a name="creating-wizards-for-item-templates-and-project-templates"></a>Vytváření průvodců pro šablony položek a šablony projektů  
 Po definování typu položky projektu služby SharePoint a přidružte ji k šabloně položku nebo projektu, můžete také vytvořit průvodce. Průvodce zobrazí, když vývojář používá k přidání položky projektu služby SharePoint do projektu šablony položky, nebo když vývojář použije šablona projektu pro vytvoření nového projektu, který obsahuje položky projektu služby SharePoint. Průvodce lze použít ke shromažďování informací od vývojářů a k inicializaci nové položky projektu služby SharePoint.  
  
 Návody, které ukazují, jak vytvořit průvodců pro šablony položek a projektů, najdete v části [návod: vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md) a [návod: vytvoření webu Položky projektu sloupce pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
## <a name="see-also"></a>Viz také  
 [Definování typů položek projektu služby SharePoint vlastní](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Vytváření šablon projektů a položek](/visualstudio/ide/creating-project-and-item-templates)  
  
  