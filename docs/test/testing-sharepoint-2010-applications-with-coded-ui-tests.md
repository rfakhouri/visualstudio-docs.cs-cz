---
title: "Testování aplikací pro SharePoint 2010 pomocí programových testů uživatelského rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51b53778-469c-4cc9-854c-4e4992d6389b
caps.latest.revision: "30"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 4cf5eac9600be44405142666e1f94408c44b0a13
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="testing-sharepoint-2010-applications-with-coded-ui-tests"></a>Testování aplikací pro SharePoint 2010 pomocí programových testů uživatelského rozhraní
Včetně programové testy uživatelského rozhraní v aplikaci SharePoint umožňuje ověřit, zda je správně funguje celou aplikaci, včetně jeho ovládacích prvků uživatelského rozhraní. Programové testy uživatelského rozhraní můžete také ověřit, hodnoty a logiku v uživatelském rozhraní.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
## <a name="what-else-should-i-know-about-coded-ui-tests"></a>Co je třeba vědět o programové testy uživatelského rozhraní?  
 Další informace o výhodách pomocí programových testů uživatelského rozhraní, najdete v části [uživatelského rozhraní automatizace k testu si kód použití](../test/use-ui-automation-to-test-your-code.md) a [testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 5 automatizace systémových testů](http://go.microsoft.com/fwlink/?LinkID=255196).  
  
 **Poznámky**  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") testy programového uživatelského rozhraní aplikací služby SharePoint jsou podporovány pouze pro SharePoint 2010.  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") není dostupná podpora pro ovládací prvky aplikace Visio a PowerPoint 2010 v aplikaci služby SharePoint.  
  
## <a name="creating-a-coded-ui-test-for-your-sharepoint-app"></a>Vytvoření programového testu uživatelského rozhraní pro aplikaci služby SharePoint  
 [Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate) pro vaše aplikace SharePoint 2010 je stejný jako vytváření testů pro jiné typy aplikací. Záznam a přehrávání jsou podporovány pro všechny ovládací prvky v rozhraní Web úpravy. Rozhraní pro výběr kategorie a webové části jsou všechny standardní ovládací prvky.  
  
 ![Webové části služby SharePoint](../test/media/cuit_sharepoint.png "CUIT_SharePoint")  
  
> [!NOTE]
>  Pokud nahráváte akce, ověření akce před generování kódu. Vzhledem k tomu, že existují různé chování přidružené hover myš, je ve výchozím nastavení. Pečlivě redundantní umístění ukazatele odebrání programové testy uživatelského rozhraní. To provedete tak, že upravíte kód pro test, nebo pomocí [programového Editor testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
## <a name="including-testing-of-office-2010-controls-within-your-sharepoint-app"></a>Včetně testování Office 2010 ovládacích prvků v aplikaci služby SharePoint  
 Jak povolit automatizaci pro některé office 2010 webové části v aplikaci služby SharePoint, budete muset provést některé změny menší kódu.  
  
> [!WARNING]
>  Podpora pro ovládací prvky aplikace Visio a PowerPoint 2010 není podporována.  
  
### <a name="excel-2010-cell-controls"></a>Ovládací prvky aplikace Excel 2010 buňky  
 Zahrnout ovládací prvky aplikace Excel buněk, je nutné provést některé změny v kódu programového testu uživatelského rozhraní.  
  
> [!WARNING]
>  Zadávání textu v libovolnou buňku aplikace Excel, následuje klíče akce šipku, nezaznamenává správně. Výběr buněk pomocí myši.  
  
 Záznamu akcí na prázdné buňky, je třeba upravit kód double klepnutím na buňku a následnému provedením operace set text. To je nutné, protože se aktivuje a klikněte na buňku, následuje žádnou akci klávesnice `textarea` v rámci buňky. Jednoduše zaznamenávání `setvalue` na prázdné buňky by Hledat `editbox` které není přítomno, dokud klepnutí na buňky. Příklad:  
  
```csharp  
Mouse.DoubliClick(uiItemCell,new Point(31,14));  
uiGridKeyboardInputEdit.Text=value;  
```  
  
 Pokud jsou zaznamenávání akcí v buňce není prázdná, pak záznam získá trochu složitější, protože v okamžiku přidat text buňky s hodnotou, nový \<div > ovládací prvek přidán jako podřízená položka buňky. Nové \<div > ovládací prvek obsahuje text, který jste právě zadali. Záznam musí zaznamenat akce na novém \<div > řízení; však nelze protože nové \<div > ovládací prvek neexistuje až po zadání test. Musíte ručně proveďte následující změny kódu pro uložení tohoto problému.  
  
1.  Přejděte do buňky inicializace a ujistěte se, `RowIndex` a `ColumnIndex` primární vlastnosti:  
  
    ```csharp  
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. RowIndex] = "3";   
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. ColumnIndex] = "3";  
    ```  
  
2.  Najít `HtmlDiv` podřízená položka buňky:  
  
    ```csharp  
    private UITestControl getControlToDoubleClick(HtmlCell cell)   
    {   
         if (String.IsNullOrEmpty(cell.InnerText)) return cell;   
         HtmlDiv pane = new HtmlDiv(cell);   
         pane.FilterProperties[HtmlDiv.PropertyNames.InnerText] = cell.InnerText;   
         // Class is an important property in finding pane   
         pane.FilterProperties[HtmlDiv.PropertyNames.Class] = "cv-nwr";   
         UITestControlCollection panes = pane.FindMatchingControls();   
         return panes[0];   
    }  
  
    ```  
  
3.  Přidat kód pro myš dvakrát klikněte na akci na `HtmlDiv`:  
  
    ```csharp  
    Mouse.DoubleClick(uIItemPane, new Point(31, 14)); )  
    ```  
  
4.  Přidejte kód pro nastavení text na `TextArea`:  
  
    ```csharp  
    uIGridKeyboardInputEdit.Text = value; }  
    ```  
  
## <a name="enabling-coded-ui-testing-of-silverlight-web-parts-in-your-sharepoint-2010-app"></a>Povolení programového testování uživatelského rozhraní pro webové části Silverlight v aplikaci SharePoint 2010  
 Testování Silverlight není podporována v sadě Visual Studio 2012 a novější. Ale pokud chcete testovat webové části Silverlight v aplikaci SharePoint 2010, můžete nainstalovat samostatný modul plug-in aplikace Silverlight z Galerie Visual Studio.  
  
#### <a name="setting-up-your-machine"></a>Nastavení vašeho počítače  
  
1.  Ujistěte se, že máte Visual Studio 2012.1 nebo novější.  
  
2.  Nainstalujte [zásuvný modul pro sadu Microsoft Visual Studio uživatelského rozhraní testování pro Silverlight](http://visualstudiogallery.msdn.microsoft.com/28312a61-9451-451a-990c-c9929b751eb4).  
  
3.  Nainstalujte [Fiddler](http://www.fiddler2.com/fiddler2/). Toto je jednoduše nástroj, který zachytí a zaznamenává provoz protokolu HTTP.  
  
4.  Stažení [fiddlerXap projektu](http://blogs.msdn.com/cfs-file.ashx/__key/communityserver-components-postattachments/00-10-36-48-70/FiddlerXapProxy.zip). Rozbalte ji, ho sestavte a spusťte skript "CopySLHelper.bat", který chcete nainstalovat pomocné knihovny DLL, která je vyžadována k otestování webové části Silverlight, když použijete nástroj Fiddler.  
  
 Po nastavení počítače, spusťte testování vaší aplikace SharePoint 2010 pomocí webové části Silverlight, postupujte takto:  
  
#### <a name="testing-silverlight-web-parts"></a>Testování webové části Silverlight  
  
1.  Spusťte aplikaci Fiddler.  
  
2.  Vymazání mezipaměti prohlížeče. To je nezbytné, protože soubor XAP, který obsahuje knihovnu DLL pomocníka automatizace uživatelského rozhraní Silverlight, je obvykle ukládají do mezipaměti. Máme a ujistěte se, že je převzata změněný soubor XAP, takže jsme Vymazat mezipaměti prohlížeče.  
  
3.  Otevřete webovou stránku.  
  
4.  Spusťte program záznam a generování kódu jako pro testování regulární webové aplikace.  
  
5.  Ověřte, zda zda generovaný kód odkazuje Microsoft.VisualStudio.TestTools.UITest.Extension.Silverlight.dll.  
  
     Další informace najdete v tématu [sadou Visual Studio 2012 testování uživatelského rozhraní SharePoint 2010](http://blogs.msdn.com/b/visualstudioalm/archive/2012/11/01/ui-testing-sharepoint-2010-with-visual-studio-2012.aspx)  
  
## <a name="external-resources"></a>Externí zdroje  
  
### <a name="blogs"></a>Blogy  
 [Testování SharePoint 2010 s Visual Studio 2012 uživatelského rozhraní](http://blogs.msdn.com/b/visualstudioalm/archive/2012/11/01/ui-testing-sharepoint-2010-with-visual-studio-2012.aspx)  
  
 [Principy vyhledávání logiku pro ovládací prvky Silverlight v programového testu uživatelského rozhraní](http://blogs.msdn.com/b/tapas_sahoos_blog/archive/2010/11/16/understanding-the-search-logic-for-silverlight-controls-in-coded-ui-test.aspx)  
  
 [Načítání vlastností ovládacího prvku Silverlight](http://blogs.msdn.com/b/tapas_sahoos_blog/archive/2010/11/16/fetching-property-of-a-silverlight-control.aspx)  
  
 [Index obsahu pro programového testu uživatelského rozhraní](http://blogs.msdn.com/b/mathew_aniyan/archive/2010/02/11/content-index-for-coded-ui-test.aspx)  
  
### <a name="guidance"></a>Doprovodné materiály  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – 5 kapitoly automatizace systémových testů](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
### <a name="forum"></a>Fórum  
 [Visual Studio ALM a Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=254496)  
  
## <a name="see-also"></a>Viz také  
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Výkonnosti webů a zátěžové testování aplikací služby SharePoint 2010 a 2013](/devops-test-docs/test/web-performance-and-load-testing-sharepoint-2010-and-2013-applications)   
 [Vytvoření řešení služby SharePoint](/office-dev/office-dev/create-sharepoint-solutions)   
 [Zobrazení a ladění kódu služby SharePoint](/office-dev/office-dev/verifying-and-debugging-sharepoint-code)   
 [Sestavování a ladění řešení služby SharePoint](/office-dev/office-dev/building-and-debugging-sharepoint-solutions)   
 [Profilace výkonu aplikací služby SharePoint](/office-dev/office-dev/profiling-the-performance-of-sharepoint-applications)
