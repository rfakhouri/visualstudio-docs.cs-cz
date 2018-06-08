---
title: 'Návod: Návrh oblasti formuláře aplikace Outlook'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3c1868768cd2d79392dbdde749f27b8716aa8c2f
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845181"
---
# <a name="walkthrough-design-an-outlook-form-region"></a>Návod: Návrh oblasti formuláře aplikace Outlook
  Oblasti formuláře vlastní rozšířit standardní nebo vlastní formuláře aplikace Microsoft Office Outlook. V tomto návodu se navrhnout vlastní formulář oblasti, která se zobrazí jako nová stránka v okně Inspector kontaktní položky. Této oblasti formuláře zobrazí mapu každou adresu, která je uvedena získáte, posílejte informace o adresy na Windows Live místní vyhledávací web. Informace o oblasti formuláře najdete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření nového projektu doplňku VSTO v Outlooku.  
  
-   Přidání oblasti formuláře do projektu doplňku VSTO.  
  
-   Návrh rozložení oblasti formuláře.  
  
-   Přizpůsobení chování oblasti formuláře.  
  
-   Testování oblasti formuláře aplikace Outlook.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)] nebo [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)].  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") video verzi tohoto tématu naleznete v části [Video postupy: Návrh oblasti formuláře aplikace Outlook](http://go.microsoft.com/fwlink/?LinkID=140824).  
  
## <a name="create-a-new-outlook-vsto-add-in-project"></a>Vytvoření nového projektu doplňku VSTO pro Outlook  
 Nejprve vytvořte základní projekt doplňku VSTO.  
  
### <a name="to-create-a-new-outlook-vsto-add-in-project"></a>K vytvoření nového projektu doplňku VSTO pro Outlook  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvoření projektu doplňku VSTO pro Outlook s názvem **MapItAddIn**.  
  
2.  V **nový projekt** dialogové okno, vyberte **vytvořit adresář pro řešení**.  
  
3.  Uložte do libovolného adresáře projektu.  
  
     Další informace najdete v tématu [postupy: vytvoření Office projekty v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="add-a-form-region-to-the-outlook-vsto-add-in-project"></a>Přidání oblasti formuláře do projektu doplňku VSTO pro Outlook  
 Řešení doplňku VSTO pro Outlook může obsahovat jednu nebo více položek oblasti formuláře aplikace Outlook. Přidat položku oblasti formuláře do projektu s použitím **nové oblasti formuláře aplikace Outlook** průvodce.  
  
### <a name="to-add-a-form-region-to-the-outlook-vsto-add-in-project"></a>Přidání oblasti formuláře do projektu doplňku VSTO pro Outlook  
  
1.  V **Průzkumníku řešení**, vyberte **MapItAddIn** projektu.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, vyberte **oblasti formuláře aplikace Outlook**, název souboru **MapIt**a potom klikněte na **přidat**.  
  
     **Oblasti formuláře NewOutlook** spustí se průvodce.  
  
4.  Na **vyberte způsob vytvoření oblasti formuláře** klikněte na tlačítko **návrhu nové oblasti formuláře**a potom klikněte na **Další**.  
  
5.  Na **vyberte typ oblasti formuláře, které chcete vytvořit** klikněte na tlačítko **samostatné**a pak klikněte na **Další**.  
  
     A *samostatné* oblasti formuláře přidá novou stránku pomocí formuláře aplikace Outlook. Další informace o typech oblasti formuláře najdete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).  
  
6.  Na **zadejte popisný text a vybrat vaše předvolby zobrazení** zadejte **mapy ho** v **název** pole.  
  
     Tento název se zobrazí na pásu karet okna Inspector v otevřeném položky kontaktu.  
  
7.  Vyberte **tvoří kontroly, které jsou v režimu** a **kontroly, které jsou v režimu pro čtení**a potom klikněte na **Další**.  
  
8.  Na **identifikovat zpráva třídy, které se zobrazí tato oblasti formuláře** zrušte zaškrtnutí políčka **e-mailovou zprávu**, vyberte **kontaktujte**a pak klikněte na tlačítko **Dokončit**.  
  
     A *MapIt.cs* nebo *MapIt.vb* soubor je přidán do projektu.  
  
## <a name="design-the-layout-of-the-form-region"></a>Návrh rozložení oblasti formuláře  
 Vývoj oblasti formuláře vizuálně pomocí *Návrhář oblasti formuláře*. Spravované ovládací prvky můžete přetáhnout na plochu návrháře oblasti formuláře. Použít Návrháře dotazů a **vlastnosti** okno Upravit rozložení ovládacích prvků a vzhledu.  
  
### <a name="to-design-the-layout-of-the-form-region"></a>Při návrhu rozložení oblasti formuláře  
  
1.  V **Průzkumníku řešení**, rozbalte **MapItAddIn** projektu a potom dvakrát klikněte na *MapIt.cs* nebo *MapIt.vb* otevřete oblasti formuláře Návrhář.  
  
2.  Klikněte pravým tlačítkem designer a pak klikněte na **vlastnosti**.  
  
3.  V **vlastnosti** nastavte **velikost** k **664, 469**.  
  
     To zajistí, že oblasti formuláře bude dost velká pro zobrazení mapy.  
  
4.  Na **zobrazení** nabídky, klikněte na tlačítko **sada nástrojů**.  
  
5.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přidejte **WebBrowser** oblasti formuláře.  
  
     **WebBrowser** zobrazí mapu každou adresu, která je uvedena kontaktu.  
  
## <a name="customize-the-behavior-of-the-form-region"></a>Přizpůsobení chování oblasti formuláře  
 Přidáte kód pro obslužné rutiny událostí oblasti formuláře lze upravit způsob oblasti formuláře chová za běhu. Pro tuto oblast formuláře kód prozkoumá vlastnosti položky aplikace Outlook a určuje, zda se zobrazení oblasti formuláře mapy ho. Pokud se zobrazí oblasti formuláře, kód přejde na Windows Live místní vyhledávání a načte mapu každou adresu uvedené v položce kontaktů aplikace Outlook.  
  
### <a name="to-customize-the-behavior-of-the-form-region"></a>Chcete-li přizpůsobit chování oblasti formuláře  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na *MapIt.cs* nebo *MapIt.vb*a potom klikněte na **kód zobrazení**.  
  
     *MapIt.cs* nebo *MapIt.vb* otevře v editoru kódu.  
  
2.  Rozbalte **Factory oblasti formuláře** kód oblasti.  
  
     Třídu objektů factory oblasti formuláře s názvem `MapItFactory` zpřístupněn.  
  
3.  Přidejte následující kód, který `MapItFactory_FormRegionInitializing` obslužné rutiny události. Tuto obslužnou rutinu události je volána, když uživatel otevře položce kontaktu. Následující kód určuje, zda položky kontaktu obsahuje adresu. Pokud položky kontaktu neobsahuje adresu, nastaví tento kód <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> vlastnost <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> třídy k **true** a oblasti formuláře se nezobrazí. Jinak vyvolá doplňku VSTO <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> událostí a zobrazí oblasti formuláře.  
  
     [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
     [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
4.  Přidejte následující kód, který <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> obslužné rutiny události. Tento kód provede následující:  
  
    -   Zřetězí každou adresu kontaktů položky a vytvoří řetězce adresy URL.  
  
    -   Volání <xref:System.Windows.Forms.WebBrowser.Navigate%2A> metodu <xref:System.Windows.Forms.WebBrowser> objektu a předá řetězce adresy URL jako parametr.  
  
     Místní vyhledávání webové stránky se zobrazí v oblasti formuláře mapy ho a uvede všechny adresy v pracovní blok.  
  
     [!code-csharp[Trin_Outlook_FR_Separate#2](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#2)]
     [!code-vb[Trin_Outlook_FR_Separate#2](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#2)]  
  
## <a name="test-the-outlook-form-region"></a>Testování oblasti formuláře aplikace Outlook  
 Při spuštění projektu sady Visual Studio otevře aplikace Outlook. Otevřete položku kontaktní zobrazení oblasti formuláře mapy ho. Oblasti formuláře mapy ho se zobrazí na stránce ve formě libovolnou kontaktní položku, která obsahuje adresu.  
  
### <a name="to-test-the-map-it-form-region"></a>K testování oblasti formuláře mapy ho  
  
1.  Stiskněte klávesu **F5** spustit projekt.  
  
     Otevře se aplikace Outlook.  
  
2.  V aplikaci Outlook na **Domů** , klikněte na **nové položky**a pak klikněte na **kontaktujte**.  
  
3.  Ve formuláři kontaktu zadejte **Ann Beebe** jako kontakt název a potom zadejte následující tři adresy.  
  
    |Typ adresy|Adresa|  
    |------------------|-------------|  
    |**Firmy**|**Svatý hlavní 4567 Buffalo, NY**|  
    |**domácí**|**Svatý severní 1234 Buffalo, NY**|  
    |**Jiné**|**Svatý hlavní 3456 Seattle, WA**|  
  
4.  Uložte a zavřete položky kontaktu.  
  
5.  Znovu ho otevřete **Ann Beebe** kontaktní položky.  
  
6.  V **zobrazit** skupiny z pásu karet položku, klikněte na tlačítko **mapy ho** oblasti formuláře mapy ho otevřete.  
  
     Oblasti formuláře mapy se zobrazí se místní vyhledávací web. **Obchodní**, **Domů**, a **jiných** adresy zobrazí v pracovní blok. V pracovní blok vyberte adresu, která chcete namapovat.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak přizpůsobit uživatelského rozhraní aplikace Outlook z těchto témat:  
  
-   Další informace o tom, jak přizpůsobit na pásu karet položky aplikace Outlook najdete v tématu [přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md).  
  
## <a name="see-also"></a>Viz také:  
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Pokyny k vytváření oblastí formulářů aplikace Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Návod: Importujte oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Postupy: přidání oblasti formuláře do projektu doplněk aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [Vlastní akce v oblastí formulářů aplikace Outlook](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Postupy: zabránění zobrazení oblasti formuláře aplikace Outlook](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)  
  
  