---
title: Vytvoření webové části pro službu SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Microsoft.SharePoint.WebControls.DateTimeControl
- Microsoft.SharePoint.WebControls.CssLink
- Microsoft.SharePoint.WebControls.RssLink
- Microsoft.SharePoint.WebControls.Theme
- Microsoft.SharePoint.WebControls.AspMenu
- Microsoft.SharePoint.WebControls.ListProperty
- Microsoft.SharePoint.WebControls.ProjectProperty
- Microsoft.SharePoint.WebControls.FormsDigest
- Microsoft.SharePoint.WebControls.ScriptLink
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, Web Parts
- Web Parts [SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 52f35f095c91422f8882724074c54ad48edd88f9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="creating-web-parts-for-sharepoint"></a>Vytváření webových částí pro službu SharePoint
  Pomocí webové části můžete upravit obsah, vzhled a chování stránek webu služby SharePoint pomocí prohlížeče. Webové části jsou serverové ovládací prvky, které běží v stránku webové části: jsou stavební bloky stránek, které se zobrazují na web služby SharePoint. V tématu [stavebním blokem: webové části](http://go.microsoft.com/fwlink/?LinkID=182097).  
  
 Můžete vytvořit a ladit webové části na web služby SharePoint pomocí šablony ze sady Visual Studio.  
  
## <a name="creating-a-web-part-in-visual-studio"></a>Vytvoření webové části v sadě Visual Studio  
 Vytvoření webové části přidáním **webovou část** položky žádné projektu služby SharePoint. Můžete použít **webovou část** položky v řešení v izolovaném prostoru nebo řešení farmy.  
  
 Pokud chcete pro vizuální návrh webové části pomocí návrháře vytvořte **Visual webovou část** projektu nebo přidejte **Visual webovou část** položky žádné projektu služby SharePoint. Můžete použít **Visual webovou část** položky v řešení farmy jenom.  
  
### <a name="web-part-item"></a>Položka webové části  
 A **webovou část** položka obsahuje soubory, které můžete použít k návrhu webové části pro web služby SharePoint. Když přidáte **webovou část** položky, Visual Studio vytvoří složku ve vašem projektu a potom přidá několik souborů do složky. Následující tabulka popisuje každý soubor.  
  
|Soubor|Popis|  
|----------|-----------------|  
|Elements.XML|Obsahuje informace, které soubor definice funkce v projektu používá k nasazení webové části.|  
|soubor .webpart|Poskytuje informace, které je potřeba zobrazení webové části v galerii webových částí služby SharePoint.|  
|Souboru kódu|Obsahuje metody, která přidání ovládacích prvků do webové části a který generovat vlastní obsah v rámci webové části.|  
  
 Další informace najdete v tématu [postupy: vytvoření webové části služby SharePoint](../sharepoint/how-to-create-a-sharepoint-web-part.md).  
  
### <a name="visual-web-part-item"></a>Položka vizuální webové části  
 Visual webová část je webová část, kterou vytvoříte pomocí návrháře Visual Web Developer v sadě Visual Studio. Visual webovou část funguje stejně jako jiné webové části. K přidávání ovládacích prvků, jako jsou tlačítka a textová pole, do webové části, přidat kód do souboru XML. Však přidání ovládacích prvků do visual webové části pomocí přetažením nebo zkopírováním do webové části ze sady Visual Studio **sada nástrojů**. Návrháře poté generuje požadované kód v souboru XML. V tématu [postupy: vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md).  
  
## <a name="sharepoint-controls"></a>Ovládací prvky SharePoint  
 Visual Studio poskytuje některé ovládací prvky pro vytváření stránek služby SharePoint, jako je například stránky aplikací. Tyto ovládací prvky se zobrazí v **sada nástrojů** pod **ovládací prvky služby SharePoint**. Funkce pro tyto ovládací prvky je odvozena z [Microsoft.SharePoint.WebControls](http://go.microsoft.com/fwlink/?LinkId=235315) obor názvů, který obsahuje serverových ovládacích prvků ASP.NET, které se používají na stránkách lokality a seznamu služby SharePoint.  
  
|Název ovládacího prvku|Popis|  
|------------------|-----------------|  
|[AspMenu](http://go.microsoft.com/fwlink/?LinkId=235307)|Vloží nabídce ASP. Další informace najdete v tématu [– Přehled ovládacího prvku nabídka](http://go.microsoft.com/fwlink/?LinkId=235316).|  
|[CssLink](http://go.microsoft.com/fwlink/?LinkId=235308)|Vloží **odkaz** prvku do stránky .aspx a použije jeden nebo více externí šablony stylů definované **CssRegistration**.|  
|[DateTimeControl](http://go.microsoft.com/fwlink/?LinkId=235306)|Vloží data a času ovládacího prvku do stránky .aspx.|  
|[FormDigest](http://go.microsoft.com/fwlink/?LinkId=235309)|Vloží do stránky .aspx ověření zabezpečení|  
|[ListProperty](http://go.microsoft.com/fwlink/?LinkId=235310)|Vrátí hodnotu vlastnosti zadaného seznamu.|  
|[ProjectProperty](http://go.microsoft.com/fwlink/?LinkId=235311)|Vrátí globální vlastnost aktuální webové stránky.|  
|[RssLink](http://go.microsoft.com/fwlink/?LinkId=235312)|Vloží odkaz informačního kanálu RSS na stránce .aspx.|  
|[Žádost ScriptLink](http://go.microsoft.com/fwlink/?LinkId=235313)|Poskytuje vlastnosti a metody pro registraci prostředky, například skripty, na stránce tak, aby mohou být požadována při vykreslení stránky.|  
|[Motiv](http://go.microsoft.com/fwlink/?LinkId=235314)|Použije motiv na stránku .aspx.|  
  
## <a name="debugging-a-web-part"></a>Ladění webové části  
 Můžete ladit projektu služby SharePoint, který obsahuje webovou část stejně, jako by ladění jiných projektů sady Visual Studio. Při spuštění ladicího programu sady Visual Studio, Visual Studio otevře web služby SharePoint.  
  
 Pokud chcete spustit ladění kódu, přidáte webovou část na stránku webové části služby SharePoint.  
  
 Další informace o ladění projektů služby SharePoint, naleznete v části [řešení potíží s řešení služby SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
## <a name="visual-web-part-limitations"></a>Omezení vizuálních webových částí  
 Spouštění v sadě Visual Studio, můžete přidat visual webové části na řešení v izolovaném prostoru služby SharePoint a řešení ve farmách. Visual webové části, ale mají následující omezení:  
  
-   Visual webové části nepodporují nahraditelné parametry. Další informace najdete v tématu [nahraditelné parametry](../sharepoint/replaceable-parameters.md).  
  
-   Uživatelské ovládací prvky nebo visual webové části nelze přetáhnout a vyřadit ani zkopírovat na ni visual webové části. Tato akce způsobí, že chyby sestavení.  
  
-   Visual webové části nepodporují přímo tokeny serveru SharePoint například $SPUrl. Další informace najdete v tématu "Token omezení v v izolovaném prostoru Visual webové části" v tématu [řešení potíží s řešení služby SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
-   Visual webových částí v řešení v izolovaném prostoru občas zobrazí chybová zpráva, "žádost o spuštění kódu v izolovaném prostoru byla odmítnuta, protože byl příliš zaneprázdněn pro zpracování požadavku hostitelskou službu v izolovaném prostoru kód." Další informace o této chybě naleznete v části v tomto příspěvku [Blog týmu služby SharePoint Developer](http://go.microsoft.com/fwlink/?LinkId=225932).  
  
-   Ladění jazyka JavaScript na straně serveru není podporována v sadě Visual Studio, ale ladění jazyka JavaScript na straně klienta je podporována.  
  
     Přestože vložené JavaScript můžete přidat do souboru kódu na straně serveru, se nepodporuje ladění pro zarážky přidaným do značky. Ladění jazyka JavaScript, odkazovat na externí soubor JavaScript v souboru kódu a pak nastavte zarážky v souboru jazyka JavaScript.  
  
-   Ladění vloženého [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] kód je třeba provést v souboru generovaného kódu místo v souboru kódu.  
  
-   Visual webové části nepodporují použití `<@ Assembly Src=` – direktiva.  
  
-   Web služby SharePoint ovládací prvky a některé [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] ovládací prvky nejsou podporovány v prostředí služby SharePoint v izolovaném prostoru. Pokud nepodporované ovládací prvky se používají na visual webovou část v řešení v izolovaném prostoru v chybě, zobrazí se typ nebo obor názvů jméno, které 'Motiv' neexistuje v oboru názvů 'Microsoft.SharePoint.WebControls' ".  
  
 Další informace o řešení v izolovaném prostoru najdete v tématu [rozdíly mezi řešeními v izolovaném prostoru a řešení ve farmách](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).  
  
## <a name="creating-older-style-sharepoint-based-web-parts"></a>Vytváření webových částí staršího stylu pro SharePoint  
 Šablony v sadě Visual Studio můžete použít k vytvoření vlastních [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)] webových částí služby SharePoint. [!INCLUDE[vstecasplong](../sharepoint/includes/vstecasplong-md.md)] webové části je postavený na [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] infrastruktura webové části a jsou doporučené typ pro nové projekty.  
  
 Ve velmi málo případů může mít k vytvoření webové části pomocí starší styl založený na Sharepointu webové části. Visual Studio můžete vytvořit tyto typy webových částí, ale Visual Studio neposkytuje žádné šablony, které jsou určeny konkrétně pro vám pomůže vytvořit je.  
  
 Další informace o při můžete chtít vytvořit starší styl založený na Sharepointu webovou část najdete v tématu [infrastruktury webové části služby Windows SharePoint Services](http://go.microsoft.com/fwlink/?LinkId=169290). Další informace o tom, jak vytvořit webovou část pomocí starší styl založený na Sharepointu webovou část najdete v tématu [návod vytvoření základní webové části služby SharePoint](http://go.microsoft.com/fwlink/?LinkId=169288).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Postupy: Vytvoření webové části služby SharePoint](../sharepoint/how-to-create-a-sharepoint-web-part.md)|Ukazuje, jak k vytvoření webové části pro stránky služby SharePoint.|  
|[Postupy: Vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)|Ukazuje, jak k vytvoření webové části pro službu SharePoint pomocí návrhové ploše.|  
|[Postupy: Vytvoření uživatelského ovládacího prvku pro stránku aplikace nebo webovou část služby SharePoint](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|Ukazuje, jak vytvořit vlastní, opakovaně použitelné ovládací prvky, které mohou být spotřebovávána stránky aplikací a webových částí, které běží v SharePoint.|  
|[Návod: Vytvoření webové části pro službu SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)|Popisuje postup návrhu webové části pro službu SharePoint.|  
|[Návod: Vytvoření webové části pro službu SharePoint pomocí návrháře](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)|Popisuje postup návrhu webové části pro službu SharePoint tak, že přetáhnete ovládací prvky na návrhové ploše.|  
|[Návod: Vytvoření webové části Silverlight, která zobrazuje data OData pro SharePoint](../sharepoint/walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint.md)|Popisuje postup návrhu webové části pro službu SharePoint, který je hostitelem aplikace Silverlight a zobrazí data z seznamy služby SharePoint.|  
  
  