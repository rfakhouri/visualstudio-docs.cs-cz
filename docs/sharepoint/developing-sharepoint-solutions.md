---
title: "Vývoj řešení služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.Project.ProjectProperties
- VS.SharePointTools.Project.ProjectItemProperties
dev_langs:
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, overview
ms.assetid: 059bce0f-c301-4234-a0b4-9c14b7cdfa3e
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 836568ff9c8b18c944ed2fe9e1e407c2176b48c1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="developing-sharepoint-solutions"></a>Vývoj řešení služby SharePoint
  Několik šablon typ projektu služby SharePoint jsou k dispozici v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pro vytváření webů služby SharePoint a prvky webu. Seznam dostupné typy projektů, naleznete v části [projektu služby SharePoint a šablony položek projektu](../sharepoint/sharepoint-project-and-project-item-templates.md). Následuje popis elementy a vlastnosti projektu služby SharePoint.  
  
 Informace o SharePoint 2013 a doplňky SharePoint najdete v tématu [SharePoint 2013](http://msdn.microsoft.com/library/jj162979.aspx) a [doplňky sestavení SharePoint](http://msdn.microsoft.com/library/office/apps/jj163230%28v=office.15%29.aspx).  
  
## <a name="elements-of-a-sharepoint-project"></a>Prvky projektu služby SharePoint  
 Uzly v rámci projektu služby SharePoint se označují jako *SharePoint – položky*. SharePoint – položky může také obsahovat jeden nebo více podsoubory, označuje jako *souborů položek služby SharePoint*, jako například [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] konfigurační soubory, formulářů .aspx a další.  
  
 Místo vytváření projektů pomocí šablony projektu, které jsou už vyplněné souborů projektu položek, můžete použít **prázdný projekt** šablony pro vytvoření prázdného projektu služby SharePoint a poté ručně přidejte položky projektu. Projekty SharePoint může volitelně obsahovat jeden nebo více souborů funkcí (pro aktivaci ve službě SharePoint) a soubor balíčku, ve které chcete distribuovat projektu.  
  
### <a name="special-nodes"></a>Speciální uzly  
 Každý projekt SharePoint obsahuje dva uzly, které nelze přejmenovat, odstranit, Vyjmout, kopírovat nebo přetažením z projektu. Tyto uzly jsou následující:  
  
-   Funkce  
  
-   Balíček  
  
 Oba uzly se vždy zobrazují v všechny projekty SharePoint i v případě, že jsou definována žádná funkce nebo balíčků pro projekt.  
  
#### <a name="features-node"></a>Funkce uzlu  
 **Funkce** uzel obsahuje jeden nebo více funkcí projektu služby SharePoint. Funkce je kontejner rozšíření pro službu SharePoint. Po nasazení funkce na server služby SharePoint, můžete zahrnout do definice webů nebo aktivovat jednotlivě správci služby SharePoint na webech služby SharePoint. Další informace najdete v tématu [práci s funkcemi](http://go.microsoft.com/fwlink/?LinkID=147704).  
  
 Při přidání položky, jako je například typ obsahu nebo seznamu instanci, do projektu služby SharePoint, je přidán do funkcí **funkce** uzlu. Rozsah položka určuje, zda je přidána do nové nebo stávající funkce. Pokud nová položka má stejný obor jako existující funkce, se přidá do této funkce. Položka, jinak se přidá do nové funkce.  
  
 Pokud chcete ručně přidat funkce, spusťte **přidat funkce** příkaz v místní nabídce uzlu funkce. Můžete zobrazit nebo změnit obsah funkci pomocí návrháře funkce. Další informace najdete v tématu [postupy: přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md).  
  
 Pokud funkce přidá do projektu služby SharePoint, zobrazí se v **Průzkumníku řešení** jako uzel s výchozím názvem funkce*x*.feature, kde *x* je jedinečné číslo. Po nasazení funkce na server služby SharePoint, Správce služby SharePoint můžete aktivovat, zpřístupnění uživatele webů služby SharePoint.  
  
#### <a name="package-node"></a>Uzel balíčku  
 **Balíček** uzel obsahuje jeden soubor, který slouží jako mechanismus distribuce pro projektu služby SharePoint. Tento soubor, označuje jako *řešení**balíček*, je. Na základě souboru CAB s. WSP rozšíření. Balíček řešení je nasadit, opakovaně použitelný soubor, který obsahuje sadu funkcí, definice webů a sestavení, která platí pro weby služby SharePoint a která můžete povolit nebo zakázat jednotlivě. **Balíček** uzel obsahuje také vždy souboru, který je pojmenován Package.wspdef, [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] definiční soubor balíčku. Jakmile balíček je nasazen na serveru se systémem SharePoint, Správce služby SharePoint můžete ho nainstalovat a aktivovat jeho funkce.  
  
 Můžete zobrazit nebo změnit obsah balíčku v Návrháři balíček dvojitým kliknutím na uzel balíček nebo otevřením jeho místní nabídky a pak vyberete **otevřete**. Další informace najdete v tématu [vytváření balíčků řešení služby SharePoint](../sharepoint/creating-sharepoint-solution-packages.md).  
  
## <a name="sharepoint-project-and-project-item-properties"></a>Projektu služby SharePoint a vlastnosti položky projektu  
 Projekty SharePoint, stejně jako jiné [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projekty, zobrazí vlastnosti v okně vlastností a stránky vlastností. Vlastnosti, které se zobrazují závisí na uzlu, který je vybraný.  
  
 Vybrání projektu služby SharePoint, položka projektu nebo uzel souboru položky projektu v **Průzkumníku**, v okně Vlastnosti a na stránce vlastností zobrazovat následující vlastnosti:  
  
### <a name="project-properties"></a>Vlastnosti projektu  
  
|Název vlastnosti|Popis|  
|-------------------|-----------------|  
|Aktivní nasazení konfigurace|Určuje řadu kroků prováděných během nasazení. Další informace najdete v tématu [postupy: Úprava konfigurace nasazení služby SharePoint](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md).|  
|Cíl nasazení sestavení|Určuje, kde *sestavení aplikace SharePoint* nacházejí. Platné sestavení umístění hodnoty jsou buď *GlobalAssemblyCache* (výchozí), nebo *WebApplication*.<br /><br /> Pokud *řešení v izolovaném prostoru* je nastavena na **true**, pak tato vlastnost je vypnuta.|  
|Automaticky odvolat po ladění|Určuje, zda nasazené řešení automaticky odvolá ze služby SharePoint po spuštění aplikace v režimu ladění v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Při výběru řešení odvolá při IDE přejde zpět do návrhového zobrazení po ladění. Není-li zaškrtnuto, není odvolat řešení. Další informace najdete v tématu [výsuvné řešení](http://go.microsoft.com/fwlink/?LinkId=183819).|  
|Úprava konfigurací|Určuje konfiguraci nasazení pro projekt. Další informace najdete v tématu [postupy: Úprava konfigurace nasazení služby SharePoint](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md) a [nasazení, publikování a upgradování balíčků řešení služby SharePoint](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md).|  
|Povolit ladění aplikací Silverlight (namísto ladění skriptů)|Při výběru ladicí program Silverlight se připojí k procesu ladění. Při zaškrtnutí políčka zrušeno, Script debugger připojí k procesu ladění. Další informace najdete v tématu [Přehled ladění Silverlight](http://go.microsoft.com/fwlink/?LinkId=179826).|  
|Zahrnout sestavení v balíčku|Určuje, zda je sestavení projektu zabalené v čase vytvoření buildu, nebo ne.|  
|Po nasazení příkazového řádku|Určuje příkazy ke spuštění po nasazení řešení služby SharePoint. Tento řádek podporuje všechny příkazy batch, jakož i řešení MSBuild proměnných. Další informace najdete v tématu [postupy: nastavení příkazů nasazení služby SharePoint](../sharepoint/how-to-set-sharepoint-deployment-commands.md).|  
|Před nasazením příkazového řádku|Určuje příkazů pro spuštění před nasazením řešení služby SharePoint. Tento řádek podporuje všechny příkazy batch, jakož i řešení MSBuild proměnných. Další informace najdete v tématu [postupy: nastavení příkazů nasazení služby SharePoint](../sharepoint/how-to-set-sharepoint-deployment-commands.md).|  
|Soubor projektu|Název souboru, který obsahuje sestavení, konfiguraci a další informace o projektu.|  
|Složky projektu|Umístění souboru projektu v systému. (Jen pro čtení.)|  
|Řešení v izolovaném prostoru|Určuje, zda by měl být projekt nasazen jako *řešení v izolovaném prostoru*, také známé jako *vytvořené uživatelem řešení*. Řešení v izolovaném prostoru nejsou nezbytně důvěryhodný. Hodnota **true** znamená, že projekt je nasazený jako řešení v izolovaném prostoru hodnotu **false** znamená, že je projekt nasazen jako řešení farmy. Další informace najdete v tématu [v izolovaném prostoru aspekty řešení](../sharepoint/sandboxed-solution-considerations.md) a [rozdíly mezi řešeními v izolovaném prostoru a řešení ve farmách](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).|  
|Adresa URL webu|Určuje, [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] cílového webu pro tento projekt.|  
|Položku při spuštění|Určuje první položku v projektu ke spuštění.|  
  
 Když vyberete soubor položky SharePoint (například pracovního postupu nebo funkce v uzlu funkce), se zobrazí v okně Vlastnosti následující vlastnosti:  
  
### <a name="project-item-properties"></a>Vlastnosti položky projektu  
  
|Název vlastnosti|Popis|  
|-------------------|-----------------|  
|Řešení konfliktů při nasazení|Určuje akci, která se má provést při nasazení položka projektu, jehož vlastnosti jsou stejné jako položky již na serveru. Další informace najdete v tématu [řešení potíží s balení a nasazení SharePoint](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).|  
|Vlastnosti funkcí|Určuje sadu hodnot (uložené jako páry klíč – hodnota), která je součástí funkce při nasazování do služby SharePoint. Po nasazení funkce můžete přistupovat hodnoty vlastností v kódu. Další informace najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|Příjemce funkce|Poskytuje kód, který provede při určité události položka projektu obsahující funkce. Další informace najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|Název složky|Název složky položky projektu služby SharePoint.|  
|Odkazy na výstup projektu|Určuje závislost, například sestavení, která položka vašeho projektu je potřeba spustit. Další informace najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|Bezpečné ovládací prvek položky|Určuje ovládací prvky, které jsou bezpečné pro přístup z nedůvěryhodným uživatelům upravit. Další informace najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
  
### <a name="project-item-file-properties"></a>Položka projektu vlastnosti souboru  
  
|Název vlastnosti|Popis|  
|-------------------|-----------------|  
|Akce sestavení|Určuje, jak soubor souvisí s procesy sestavení a nasazení. Další informace najdete v tématu [vlastnosti souboru](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Kopírovat do výstupního adresáře|Určuje, zda zdrojové soubory budou zkopírovány do výstupního adresáře. Může být jedna z následujících hodnot:<br /><br /> -   *Nekopírujte*<br />-   *Vždy kopírovat*<br />-   *Kopírovat, pokud je novější*<br /><br /> Další informace najdete v tématu [vlastnosti souboru](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Vlastní nástroj|Určuje název nějaký nástroj, pokud existuje, který transformuje soubor v době návrhu a umístí výstup transformace do jiného souboru. Například datové sady (.[!INCLUDE[TLA2#tla_xsd](../sharepoint/includes/tla2sharptla-xsd-md.md)]) soubor má výchozí vlastní nástroj. Další informace najdete v tématu [vlastnosti souboru](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Namespace vlastní nástroj|Obor názvů, do kterého se zkopíruje výstup vlastního nástroje. Další informace najdete v tématu [vlastnosti souboru](http://msdn.microsoft.com/library/0c6xyb66(v=vs.100).aspx).|  
|Umístění nasazení|Plně kvalifikovanou cestu k souboru na serveru SharePoint. Tato cesta se skládá z dílčí vlastnosti nasazení kořenové a cesta pro nasazení.|  
|Cesta pro nasazení|Relativní cestu k souboru na soubor SharePoint Server, jako je například Workflow1\\. Plně kvalifikovaná cesta k souboru se vytvoří zřetězením *Cesta nasazení* hodnotu na konec *nasazení kořenové* hodnotu.<br /><br /> Vyberte hodnotu *RootFile* pro *typ nasazení* změny vlastností *nasazení kořenové* vlastnost {SharePointRoot}\\, což plně kvalifikovaná cesta {SharePointRoot} \Workflow1\\. Další informace najdete v tématu [balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md).|  
|Nasazení kořenové|Řetězec. Kořenové složky, kde je nainstalován na serveru SharePoint. Například {SharePointRoot} \Template\Features\\{FeatureName}\\.<br /><br /> Hodnota *nasazení kořenové* vlastnost je dáno *typ nasazení* nastavení.|  
|Typ nasazení|Typ nasazení v souboru, který určuje jeho *nasazení kořenové* hodnotu. Může být jedna z následujících hodnot:<br /><br /> NoDeployment: \<žádná hodnota ><br /><br /> ElementManifest: {SharePointRoot} \Template\Features\\{FeatureName}\\<br /><br /> ElementFile: {SharePointRoot} \Template\Features\\{FeatureName}\\<br /><br /> TemplateFile: {SharePointRoot} \Template\\<br /><br /> RootFile: {SharePointRoot}\\<br /><br /> GlobalResource: {SharePointRoot} \Resources\\<br /><br /> ClassResource: {ClassResourcePath}\\<br /><br /> Další informace naleznete v tématu <xref:Microsoft.VisualStudio.SharePoint.DeploymentType>.|  
|Název souboru|Název souboru nebo složky pro soubor položky.|  
|Úplná cesta|Umístění souboru pro položku. (Jen pro čtení.)|  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Projektu služby SharePoint a šablony položek projektu](../sharepoint/sharepoint-project-and-project-item-templates.md)|Popisuje projektu služby SharePoint a šablony položek projektu, které jsou k dispozici v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|  
|[Postupy: přidání položek do projektu služby SharePoint](../sharepoint/how-to-add-items-to-a-sharepoint-project.md)|Popisuje, jak přidat nové nebo existující položky do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu služby SharePoint.|  
|[Návod: Vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)|Vás krok za krokem při vytváření zákazníka pole, typu obsahu, definice seznamu a instanci seznamu.|  
|[Postupy: vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)|Popisuje postup přidání přijímače událostí pro projekt vytvořené v [návod: vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).|  
|[Vytváření řešení pracovního postupu služby SharePoint](../sharepoint/creating-sharepoint-workflow-solutions.md)|Popisuje postup vytvoření projekty workflow, který obsahuje formuláře přidružení pracovního postupu a formuláře inicializace pracovního postupu.|  
|[Vytváření stránek pro službu SharePoint](../sharepoint/creating-pages-for-sharepoint.md)|Popisuje, jak můžete vytvořit například stránky aplikací, weby, hlavní stránky a stránky rozložení stránek pro službu SharePoint.|  
|[Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)|Popisuje postup přidání ovládacích prvků, které umožňují uživatelům přímo upravit obsah, vzhled a chování stránek webu služby SharePoint pomocí prohlížeče.|  
|[Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)|Popisuje, jak vytvořit uživatelské ovládací prvky, které mohou být spotřebovávána stránky aplikací a webových částí, které používají ve službě SharePoint.|  
|[Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)|Popisuje, jak integrovat data z webové služby a serveru back-end aplikace do aplikace SharePoint.|  
|[Vytváření definic webu pro službu SharePoint](../sharepoint/creating-site-definitions-for-sharepoint.md)|Popisuje postup vytvoření definice webů: šablony, které se používají k vytváření webů služby SharePoint.|  
|[Import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)|Popisuje, jak importovat z existující stránky SharePoint do položek, jako jsou typy obsahu a moduly [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu služby SharePoint.|  
|[Vložené soubory v řešení pomocí modulů](../sharepoint/using-modules-to-include-files-in-the-solution.md)|Popisuje, jak používat moduly pro nasazení soubory z vaší [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu na web služby SharePoint.|  
|[Procházení připojení služby SharePoint pomocí Průzkumníka serveru](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)|Popisuje, jak procházet místních webů služby SharePoint pomocí Průzkumníka serveru.|  
|[Poskytnutí balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)|Popisuje, jak používat vlastnosti položky projektu k zadání informací o balení a nasazení pro projekty, například položky bezpečné řízení, odkazy na výstup projektu a vlastnosti funkcí.|  
|[Postupy: Přidání a odebrání mapovaných složek](../sharepoint/how-to-add-and-remove-mapped-folders.md)|Popisuje, jak mapované složky lze přidat do projektu vám umožňuje snadnější přístup k prostředkům služby SharePoint.|  
|[Aspekty řešení v izolovaném prostoru](../sharepoint/sandboxed-solution-considerations.md)|Popisuje problémy související s řešení v izolovaném prostoru.|  
|[Zabezpečení pro řešení služby SharePoint](../sharepoint/security-for-sharepoint-solutions.md)|Popisuje důležité informace o zabezpečení pro vývoj řešení služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].|  
|[Dialogové okno pro výběr adresy URL &#40; Vývoj pro SharePoint v sadě Visual Studio &#41;](../sharepoint/url-picker-dialog-box-sharepoint-development-in-visual-studio.md)|Popisuje dialogové okno, které můžete použít k přidání odkazů na cestu k prostředkům ve vašem projektu nebo na místním serveru SharePoint.|  
  
## <a name="see-also"></a>Viz také  
 [Začínáme &#40; Vývoj pro SharePoint v sadě Visual Studio &#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)   
 [Procházení připojení služby SharePoint pomocí Průzkumníka serveru](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [Sestavování a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  