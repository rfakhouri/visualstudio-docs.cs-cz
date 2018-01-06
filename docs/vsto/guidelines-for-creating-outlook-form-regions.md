---
title: "Pokyny pro vytváření Outlook formuláři oblasti | Microsoft Docs"
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
- form regions [Office development in Visual Studio], guidelines
- icons [Office development in Visual Studio]
ms.assetid: 47ad59d3-5cb7-4d27-a314-9c09937143d7
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 197da04c42b97f274979e46a2ba4691747365362
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="guidelines-for-creating-outlook-form-regions"></a>Pokyny pro vytváření oblastí formulářů aplikace Outlook
  Následující informace vám může pomoct optimalizovat vaší oblasti formuláře a vyhnout se potenciální problémy:  
  
-   [Pomocí názvů oblasti formuláře](#UsingFormRegions).  
  
-   [Zakázat dědičnost oblasti formuláře](#DisablingInheritance).  
  
-   [Principy typů a zpráva třídy názvy](#ClassNames).  
  
-   [Navrhování sousedících oblasti formuláře podokna čtení](#ReadingPane).  
  
-   [Pomocí optimální ikonu velikosti](#UsingOptimal).  
  
 Další informace o oblasti formuláře najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
##  <a name="UsingFormRegions"></a>Pomocí názvů oblasti formuláře  
 Existuje několik názvů používaných k popisu oblasti formuláře. Je důležité si uvědomit rozdíl mezi tyto názvy a jejich vliv na oblasti formuláře. Následující tabulka popisuje každý název.  
  
|Název oblasti formuláře|Popis|  
|----------------------|-----------------|  
|Název položky oblasti formuláře|Název, který zadáte pro **oblasti formuláře aplikace Outlook** položky v **přidat novou položku** dialogové okno. Toto je název souboru kódu oblasti formuláře, který se zobrazí v **Průzkumníku řešení**.|  
|<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A>Vlastnost|Zadejte název v **zadejte popisný text a vybrat vaše předvolby zobrazení** stránky **nové oblasti formuláře aplikace Outlook** průvodce. Tento název se zobrazí jako **FormRegionName** vlastnost **vlastnosti** okno.<br /><br /> Použití <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> vlastnosti k určení štítek, který identifikuje oblasti formuláře v uživatelském rozhraní (UI) aplikace Outlook. Tento název se zobrazí jako tlačítka na pásu karet položky aplikace Outlook pro oblasti samostatné formuláře.<br /><br /> Tento název se zobrazí jako text záhlaví výše oblasti formuláře pro sousedících oblasti formuláře.|  
|Atribut Microsoft.Office.Tools.Outlook.FormRegionName|Když přidáte **oblasti formuláře aplikace Outlook** položku do projektu sady Visual Studio nastaví tato vlastnost na plně kvalifikovaný název oblasti formuláře. Plně kvalifikovaný název výchozí je název doplňku VSTO připojeným k názvu oblasti formuláře tečkou – například `OutlookAddIn1.FormRegion1`.<br /><br /> Tento plně kvalifikovaný název se zobrazí jako atribut v horní části třídu objektů factory oblasti formuláře.<br /><br /> Pomocí atributu Microsoft.Office.Tools.Outlook.FormRegionName jednoznačně identifikovat oblasti formuláře na všech doplňků VSTO pro Outlook. Nelze změnit hodnotu atributu Microsoft.Office.Tools.Outlook.FormRegionName, přejmenování položky oblasti formuláře nebo změnou <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> vlastnost. Chcete-li změnit tento název, musíte upravit atribut Microsoft.Office.Tools.Outlook.FormRegionName v souboru kódu oblasti formuláře.|  
  
##  <a name="DisablingInheritance"></a>Zakázání oblast dědičnost formulářů  
 Ve výchozím nastavení vlastní zprávu třídy dědí všechna přidružení oblasti formuláře třídy base zprávy. Například třída zprávu s názvem `IPM.Task.Contoso` je odvozena z IPM. Úloha. Proto `IPM.Task.Contoso` dědí přidružení oblasti formuláře IPM. Úloha.  
  
 Pokud nechcete, aby oblasti formuláře, který se má přidružit všechny třídy odvozených zpráv, nastavte <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> vlastnost oblasti formuláře k **true**. Například Pokud přidružíte sousedících oblasti formuláře IPM. Úlohy a nastavte <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> vlastnost **true**, oblasti formuláře pouze, připojí se k dolnímu okraji formuláře standardní úlohy. Oblasti formuláře nebudou připojí k dolnímu okraji všechny přizpůsobené verze formuláře standardní úlohy.  
  
##  <a name="ClassNames"></a>Principy typů a názvy zpráv – třída  
 Název typu položky aplikace Outlook se liší od názvu třídy zpráva položky aplikace Outlook. Název typu položky RSS je například Microsoft.Office.Interop.Outlook.PostItem. Název třídy zpráva položky RSS je IPM. Post.RSS.  
  
 Chcete-li položku aplikace Outlook v kódu použijte název typu. Seznam názvů typu, najdete v části [přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
 Použijte název třídy zpráv aplikace Outlook položek v **nové oblasti formuláře aplikace Outlook** Průvodce pro přidružení oblasti formuláře položky. Seznam zpráv platné názvy tříd, naleznete v části [přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
##  <a name="ReadingPane"></a>Návrh oblasti formuláře sousedících podokna pro čtení  
 Zobrazte náhled položky aplikace Outlook bez otevření položky můžete podokně čtení aplikace Outlook. V podokně čtení je určená jen pro čtení. Proto nemusí vstupní ovládací prvky, které přidáte do sousedících oblasti formuláře, jako je například textové pole, chovat podle očekávání, když jsou otevřené v podokně čtení oblasti položky a formuláře.  
  
 Například pokud položku, která obsahuje oblast sousedících formuláře je otevřen v podokně pro čtení, následující situaci je možné:  
  
1.  Vyberte nějaký text do textového pole, která je v oblasti formuláře.  
  
2.  Stiskněte klávesu DELETE.  
  
3.  Místo text do textového pole je odstranit položku celou e-mailu.  
  
 Pokud navrhujete sousedících oblasti formuláře, který obsahuje vstupní ovládací prvky, otestujte ovládací prvky v podokně čtení a ujistěte se, že fungují správně. Zvažte přidání vlastní kód, který zakáže ovládacích prvků, které není chovat podle očekávání.  
  
 Alternativně můžete nastavit <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ShowInspectorRead%2A> vlastnost oblasti formuláře k **False**. Tímto způsobem oblasti formuláře nelze použít v podokně čtení.  
  
##  <a name="UsingOptimal"></a>Pomocí optimální ikonu velikosti  
 Můžete určit, které ikony mají oblasti formuláře k nastavením vlastností ikony v zobrazení **ikony** vlastnost skupiny **vlastnosti** okno. K dosažení nejlepší vizuální kvalitu pomocí následujících pokynů:  
  
-   Pro **stránky** ikonu, použijte soubor Portable Network Graphics (PNG).  
  
-   **Okno** ikony musí být 32 x 32 pixelů.  
  
-   Všechny ostatní ikony musí být 16 x 16 pixelů.  
  
 **Stránky** se zobrazí ikona na pásu karet Inspector pro položky, které mají samostatné, náhrada nebo oblastí formulářů nahradit all.  
  
 **Okno** ikonu se zobrazí v oznamovací oblasti a v dialogovém okně ALT + TAB pro otevřete položky nahrazení nebo oblastí formulářů nahradit all.  
  
## <a name="see-also"></a>Viz také  
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Postupy: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Postupy: přidání oblasti formuláře do projektu doplňku aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  