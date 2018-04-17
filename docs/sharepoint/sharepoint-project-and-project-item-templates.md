---
title: Šablony položek projektu služby SharePoint a projekt | Microsoft Docs
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SPE.FirstWizardPage
- VS.SharePointTools.SPE.ListInstance
- VS.SharePointTools.SPE.ListDefinition
- VS.SharePointTools.SPE.ListDefFromContentType
- VS.SharePointTools.SPE.ContentType
- SPE.Wizard
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, project and project item templates
- SharePoint development in Visual Studio, templates
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d671c397f139cfaa51bd664e5324a32cce671361
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sharepoint-project-and-project-item-templates"></a>Šablony projektů a položek projektů služby SharePoint
  Následující části popisují dostupné projektu služby SharePoint a položek projektu šablony a způsobu jejich použití. 
  
##  <a name="project-and-project-item-templates-overview"></a>Projekt a Přehled šablon položek projektu  
 Při vytváření nového projektu služby SharePoint v sadě Visual Studio, projektu služby SharePoint se přidá k řešení společně s všechny položky projektu vyžadují tento typ projektu. Například pokud vytvoříte projekt webové části Silverlight, Visual Studio vytvoří řešení, které obsahuje položka projektu Visual webové části a položka projektu aplikace Silverlight spolu se všechny soubory, které vyžadují tyto položky projektu. Šablony položek projektu slouží k přidání položky projektu do existujícího projektu služby SharePoint, jako je například přidávání příjemce událostí, sloupec webu nebo v seznamu.  
  
 Informace o SharePoint základy najdete v tématu [SharePoint Foundation stavební bloky](http://go.microsoft.com/fwlink/?LinkId=179404). Pokročilí uživatelé mohou vytvářet vlastních projektů a šablon položek projektu. Další informace najdete v tématu [rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md).  
  
##  <a name="project-templates"></a>Šablony projektů  
 Následuje seznam šablon projektu služby SharePoint. K zobrazení šablon projektu služby SharePoint v sadě Visual Studio v **nový projekt** dialogové okno, rozbalte seznam **SharePoint** uzel v rámci buď **Visual C#** nebo  **Visual Basic**a potom zvolte **2010**.  
  
### <a name="sharepoint-2010-project"></a>Projekt služby SharePoint 2010  
 Obsah *projektu služby SharePoint 2010* jsou zahrnuty v každé šabloně projektu služby SharePoint. Projektu služby SharePoint 2010 obsahuje:  
  
-   Soubor projektu.  
  
-   Stránce vlastností projektu.  
  
-   A **odkazy** složku obsahující všechny odkazy na sestavení v projektu.  
  
-   A **funkce** složku, která obsahuje .feature konfigurační soubor, použít k nasazení funkcí na server služby SharePoint.  
  
-   A **balíček** složku, která obsahuje soubor Package.package použít k nasazení řešení do služby SharePoint.  
  
-   Soubor key.snk (silný název klíč), který se používá k podepsání sestavení silným názvem, pro rozšířené zabezpečení.  
  
### <a name="sharepoint-2010-silverlight-web-part"></a>SharePoint 2010 – webová část Silverlight  
 *Webové části služby SharePoint 2010 Silverlight* projekty umožňují vytvářet webové části pro službu SharePoint, který zobrazí aplikace Silverlight. Pokud vytvoříte tento projekt, můžete určit, zda přidat do něj novou aplikaci Silverlight, nebo odkaz některého ze stávajících. Další informace najdete v tématu [vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md) a [návod: vytvoření webové části Silverlight této zobrazí OData pro službu SharePoint](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md).  
  
### <a name="sharepoint-2010-visual-web-part"></a>Vizuální webová část služby SharePoint 2010  
 A *webové části služby SharePoint 2010 Visual* projekt obsahuje soubor definice Elements.xml **webovou část** položku a **uživatelský ovládací prvek** položky. Vzhled visual webové části můžete navrhnout přetažením nebo kopírování ovládacích prvků z panelu nástrojů Visual Studio na povrch uživatelského ovládacího prvku. Další informace najdete v tématu [postupy: vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) a [stavebním blokem: webové části](http://go.microsoft.com/fwlink/?LinkId=179438).  
  
### <a name="import-sharepoint-2010-solution-package"></a>SharePoint 2010 – Importovat balíček řešení  
 *Import balíčku řešení služby SharePoint 2010* projekty umožňují importovat nebo jeho část existující web služby SharePoint 2010, exportovat do souboru (WSP) řešení služby SharePoint, do sady Visual Studio. Po importu do sady Visual Studio, můžete přizpůsobit jeho položky a znovu je. Další informace najdete v tématu [import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).  
  
### <a name="import-reusable-sharepoint-2010-workflow"></a>SharePoint 2010 – Importovat znovu použitelný pracovní postup  
 *Import opakovaně použitelného pracovního postupu služby SharePoint 2010* projekty umožňují import opakovaně použitelný, deklarativní pracovní postup vytvořený v SharePoint Designer 2010 do sady Visual Studio. Pracovní postup se exportují z webu služby SharePoint jako soubor WSP. Po importu do sady Visual Studio, můžete přizpůsobit, přidejte do ní kód a pak je nasadit na web služby SharePoint. Další informace najdete v tématu [návod: Import opakovaně použitelného pracovního postupu služby SharePoint Designer do sady Visual Studio](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md).  
  
##  <a name="project-item-templates"></a>Šablony položek projektu  
 Následuje seznam šablony položek projektu služby SharePoint. Šablony položek projektu přidejte soubory do řešení služby SharePoint pro podporu funkcí služby SharePoint, jako je například sloupce webu, seznamy a typy obsahu. Přidání sloupce webu do vašeho řešení například přidá sloupec projekt lokality, který obsahuje soubor definice Elements.xml. Přidání visual webovou část přidá projekt visual část řešení, který obsahuje soubor Elements.xml, položky ovládacího prvku uživatele a položku visual webovou část.  
  
 Chcete-li zobrazit šablony položek projektu služby SharePoint, v **Průzkumníku řešení**, otevřete místní nabídky projektu služby SharePoint a potom zvolte **přidat**, **novou položku**. Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010**.  
  
### <a name="application-page-farm-solution-only"></a>Stránka aplikace (jenom řešení farmy)  
 **Stránky aplikace (jenom řešení farmy)** položka umožňuje návrh [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] webové stránky pro web služby SharePoint. Stránky aplikací můžete použít pouze v řešení ve farmách. Tato položka projektu můžete přidat pouze pro řešení ve farmách. Další informace najdete v tématu [postupy: vytvoření stránky aplikace](../sharepoint/how-to-create-an-application-page.md) a [aplikace _layouts typ stránky](http://go.microsoft.com/fwlink/?LinkId=179434).  
  
### <a name="business-data-connectivity-model-farm-solution-only"></a>Modelu připojení obchodních dat (pouze řešení farmy)  
 A **modelu připojení obchodních dat (pouze řešení farmy)** položka umožňuje integraci obchodních dat do služby SharePoint. Obchodní data mohou pocházet z back-end serverů aplikace, jako například [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)], Siebel a inzerování protokolu SAP (Service). Modelů připojení obchodních dat lze použít pouze v řešení ve farmách. Tato položka projektu můžete přidat pouze pro řešení ve farmách. Další informace najdete v tématu [postupy: vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md), [postupy: použití souboru prostředků k zadat lokalizované názvy, vlastnosti a oprávnění](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md), a [co je nového: Připojení obchodních Služby](http://go.microsoft.com/fwlink/?LinkId=179411).  
  
### <a name="content-type"></a>Typ obsahu  
 *Typ obsahu* položky umožňují vytvářet vlastní typy obsahu na základě existující (základní) obsahu typu například dokument, oznámení nebo úlohu. Vlastní typ obsahu poskytuje stejné atributy a pole jako základní typ obsahu společně s žádné lokality sloupce (pole), můžete definovat. Například můžete vytvořit vlastní typ kontaktujte obsahu, který je založený na základní obsahu typu kontaktu, který jste dostali se ve službě SharePoint. Typ obsahu, který můžete přizpůsobit existující sloupce webu změna nebo přidání více sloupců lokality k těm, které jsou již zahrnuty v základním typu obsahu.  
  
> [!NOTE]  
>  Z důvodu omezení služby SharePoint nelze vytvořit typ obsahu řešení farmy založený na typu obsahu řešení v izolovaném prostoru.  
  
 Další informace najdete v tématu [návod: vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) a [stavebním blokem: typ obsahu](http://go.microsoft.com/fwlink/?LinkId=179413).  
  
### <a name="empty-element"></a>Prázdný Element  
 *Prázdné prvky* se nejčastěji používají k definování položek projektu služby SharePoint, která nemají projektu nebo šablony položek projektu v sadě Visual Studio. Když přidáte prázdný element do projektu, uzel s názvem EmptyElement [x](where [x] is a unique number\) is created. EmptyElement [x] obsahuje jeden soubor s názvem Elements.xml. Použití [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] příkazy k definování požadované prvky v Elements.xml.  
  
### <a name="event-receiver"></a>Příjemce událostí  
 *Přijímače událostí* zpracování událostí pro položky na webu služby SharePoint, například když je položka přidána do seznamu, když je odstraněn položky webové nebo při spuštění pracovního postupu. Šablony položek projektu příjemce události umožňuje zpracovat  
  
-   Seznam událostí  
  
-   Položka seznamu události  
  
-   Seznam e-mailu události  
  
-   Webové události  
  
-   Seznam událostí pracovního postupu  
  
 Položky projektu přijímač událostí vytvoří **příjemce událostí** složku s jedné třídy soubor, který obsahuje obslužných rutin událostí pro všechny události, které jste zadali, když jste vytvořili projekt ve **přizpůsobení služby SharePoint Průvodce**. Event – třída příjemce může zpracovávat události na web služby SharePoint položek, jako jsou soubory, pole, položky, seznamy, přílohy, webové části a pracovní postupy jsou přidány, aktualizovat, odstranit, nebo odebrat. Další informace najdete v tématu [postupy: vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md) a [stavebním blokem: zpracování událostí](http://go.microsoft.com/fwlink/?LinkId=179416).  
  
### <a name="list"></a>Seznam  
 Seznam představuje instanci opakovaně použitelné základní SharePoint seznamu definici, jako je například kalendář nebo seznamu úloh. Po přidání seznamu do vašeho řešení, návrháře seznamu můžete přidat do seznamu sloupců webu a vytvořit vlastní seznam sloupců. To zahrnuje sloupce webu z typy obsahu. Můžete zadat *zobrazení* pro seznam, který určuje sloupce, které se zobrazí v seznamu. Další informace najdete v tématu [návod: vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) a [stavebním blokem: seznamy a knihovny dokumentů](http://go.microsoft.com/fwlink/?LinkId=179421).  
  
### <a name="module"></a>Modul  
 *Moduly* (Nezaměňovat s [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] moduly) obsahují všechny soubory, které chcete nasadit server služby SharePoint, například obrázky nebo poznámky. Položka projektu modulu obsahuje **modulu** uzlu. Uzel modul obsahuje dvě šablony položek projektu: soubor definice XML, který funguje jako manifestu modulu, a soubor ukázka.txt soubor zástupný symbol. Další informace najdete v tématu [pomocí modulů souborů v řešení](../sharepoint/using-modules-to-include-files-in-the-solution.md) a [moduly](http://go.microsoft.com/fwlink/?LinkId=179425).  
  
### <a name="sequential-workflow-farm-solution-only"></a>Sekvenční pracovní postup (pouze řešení farmy)  
 A *sekvenční pracovní postup* je posloupnost kroků obchodní logiky, provést v pořadí, až do dokončení poslední krok. Sekvenční pracovní postupy se používají ke správě procesů, které zahrnují SharePoint – položky například seznamy a dokumenty. Můžete vytvořit pracovní postupy (globální) úrovni webu nebo (místní) pracovních postupů na úrovni seznamu a můžete určit, zda spuštění pracovního postupu automaticky nebo ručně. Tato položka projektu lze použít pouze v řešení ve farmách. Tato položka projektu můžete přidat pouze pro řešení ve farmách. Další informace najdete v tématu [vytváření řešení pracovního postupu služby SharePoint](../sharepoint/creating-sharepoint-workflow-solutions.md), [pracovních postupů v produktu SharePoint Server 2010](http://go.microsoft.com/fwlink/?LinkId=260555), a [co je nového: pracovní postup vylepšení](http://go.microsoft.com/fwlink/?LinkId=179418).  
  
### <a name="silverlight-web-part"></a>Webové části Silverlight  
 *Webové části Silverlight* položky projektu umožňují vytvářet webové části pro službu SharePoint, který zobrazí aplikace Silverlight. Když přidáte tuto položku projekt pro vaše řešení, mohli vybrat, jestli přidejte novou aplikaci Silverlight, nebo odkaz stávající později. Další informace najdete v tématu [vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md) a [návod: vytvoření webové části Silverlight této zobrazí OData pro službu SharePoint](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md).  
  
### <a name="site-column"></a>Sloupec webu  
 A *sloupec lokality*, také známé jako *pole*, je jedním z nejzákladnější prvků přidáte do projektu služby SharePoint. Sloupec lokality představuje typ dat, například telefonní číslo, text komentáře nebo název města kontaktu, seznamu kontaktů. Další informace najdete v tématu [vytváření sloupců webu, typů obsahu a seznamů pro službu SharePoint](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md) a [sloupce](http://go.microsoft.com/fwlink/?LinkId=226840).  
  
### <a name="site-definition-farm-solution-only"></a>Definice webu (pouze řešení farmy)  
 *Lokalita definice* položky projektu obsahovat složky definice lokality, která zahrnuje následující soubory:  
  
-   Výchozí .aspx stránku, použít jako výchozí webové stránky pro tuto lokalitu.  
  
-   Soubor onet.xml, který definuje součásti lokality.  
  
-   Soubor xml webtemp, který určuje definici konfigurace lokality, které se zobrazují v **výběr šablony** části **nový web služby SharePoint** stránky.  
  
 Po přidání definici lokality přidáte kód a soubory funkci zavedou. Tato položka projektu lze použít pouze v řešení ve farmách. Tato položka projektu můžete přidat pouze pro řešení ve farmách. Další informace najdete v tématu [vytváření definic webu pro SharePoint](../sharepoint/creating-site-definitions-for-sharepoint.md) a [lokality definice a konfigurace](http://go.microsoft.com/fwlink/?LinkId=260554).  
  
### <a name="state-machine-workflow-farm-solution-only"></a>Pracovní postup stavového stroje (pouze řešení farmy)  
 A *pracovní postup stavového stroje* je sada stavů obchodní logiky, přechody a akce. Kroky v pracovním postupu stavu počítače nejsou prováděny postupně; Místo toho se spouštějí akcemi a stavy. Sekvenční pracovní postup, jako je stav počítače pracovních jsou přidruženy k SharePoint – položky například seznamy a dokumenty. Znovu můžete vytvořit pracovní postupy (globální) úrovni webu nebo (místní) pracovních postupů na úrovni seznamu. Můžete také vybrat, jestli spuštění pracovního postupu automaticky nebo ručně. Tato položka projektu lze použít pouze v řešení ve farmách. Tato položka projektu můžete přidat pouze pro řešení ve farmách. Další informace najdete v tématu [vytváření řešení pracovního postupu služby SharePoint](../sharepoint/creating-sharepoint-workflow-solutions.md), [pracovních postupů v produktu SharePoint Server 2010](http://go.microsoft.com/fwlink/?LinkId=260555), a [co je nového: pracovní postup vylepšení](http://go.microsoft.com/fwlink/?LinkId=179418).  
  
### <a name="user-control-farm-solution-only"></a>Uživatelský ovládací prvek (pouze řešení farmy)  
 A *uživatelský ovládací prvek* je vlastní, opakovaně použitelné ovládací prvek, do kterého můžete přidat další ovládací prvky ASP.NET a ovládací prvky služby SharePoint. Stránky aplikací a webových částí, které běží v SharePoint lze přidat uživatelský ovládací prvek. Tato položka projektu lze použít pouze v řešení ve farmách. Tato položka projektu můžete přidat pouze pro řešení ve farmách. Další informace najdete v tématu [vytváření opakovaně použitelného ovládacích prvků pro webové části nebo stránky aplikací](http://go.microsoft.com/fwlink/?LinkId=226841).  
  
### <a name="visual-web-part"></a>Visual webové části  
 A *visual webovou část* položka projektu zahrnuje soubor definice Elements.xml **webovou část** položku a **uživatelský ovládací prvek** položky. Vzhled visual webové části můžete navrhnout přetažením nebo kopírování ovládacích prvků z panelu nástrojů Visual Studio na povrch uživatelského ovládacího prvku. Další informace najdete v tématu [postupy: vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md) a [stavebním blokem: webové části](http://go.microsoft.com/fwlink/?LinkId=179438).  
  
### <a name="web-part"></a>Webová část  
 A *webovou část* serverové ovládací prvek, který běží v rámci zvláštním typem stránku s názvem stránku webové části. Jsou stavební bloky stránek, které se zobrazují na web služby SharePoint. Webová část položka obsahuje soubory, které vám umožní navrhnout webové části pro web služby SharePoint. Další informace najdete v tématu [postupy: vytvoření webové části služby SharePoint](../sharepoint/how-to-create-a-sharepoint-web-part.md) a [stavebním blokem: webové části](http://go.microsoft.com/fwlink/?LinkId=179438).  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Produkty a technologie SharePoint](http://go.microsoft.com/fwlink/?LinkId=178818)  
  
  
