---
title: "Přehled modelu objektů aplikace Outlook | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.ProjectItem.OutlookAddin
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], object model overview
- object models [Office development in Visual Studio], Office
- objects [Office development in Visual Studio], Office object models
- object models [Office development in Visual Studio], Outlook
- Office object models
ms.assetid: 59704974-b7d9-46d6-949c-e97349c75279
caps.latest.revision: "59"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: cffce10e443b2605e29d800cb271c4a96dc70359
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="outlook-object-model-overview"></a>Přehled modelu objektů aplikace Outlook
  K vývoji doplňků VSTO pro aplikaci Microsoft Office Outlook, můžete pracovat s objekty, které jsou k dispozici ve model objektu aplikace. Objektový model aplikace Outlook poskytuje třídy a rozhraní, které představují položky v uživatelském rozhraní. Například <xref:Microsoft.Office.Interop.Outlook.Application> objekt představuje celou aplikaci <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> objekt představuje složku obsahující e-mailových zpráv nebo jiných položek a <xref:Microsoft.Office.Interop.Outlook.MailItem> objekt představuje e-mailové zprávy.  
  
 Toto téma obsahuje stručný přehled některé hlavní objekty v modelu objektů aplikace Outlook. Prostředky, kde můžete další informace o celý model objektů aplikace Outlook, najdete v části [pomocí dokumentace modelu objektů aplikace Outlook](#refdoc).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: pomocí aplikace Outlook vytvořit vlastní sestavu úkolů?](http://go.microsoft.com/fwlink/?LinkID=130315).  
  
## <a name="accessing-objects-in-an-outlook-project"></a>Přístup k objektům v projektech Outlook  
 Outlook poskytuje mnoho objektů, se kterými můžete pracovat. Objektový model efektivně používat, musí být obeznámeni s nejvyšší úrovně následující objekty:  
  
-   <xref:Microsoft.Office.Interop.Outlook.Application>  
  
-   <xref:Microsoft.Office.Interop.Outlook.Explorer>  
  
-   <xref:Microsoft.Office.Interop.Outlook.Inspector>  
  
-   <xref:Microsoft.Office.Interop.Outlook.MAPIFolder>  
  
-   <xref:Microsoft.Office.Interop.Outlook.MailItem>  
  
-   <xref:Microsoft.Office.Interop.Outlook.AppointmentItem>  
  
-   <xref:Microsoft.Office.Interop.Outlook.TaskItem>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ContactItem>  
  
### <a name="application-object"></a>Objekt aplikace  
 <xref:Microsoft.Office.Interop.Outlook.Application> Objekt představuje v aplikaci Outlook a je nejvyšší objekt v modelu objektů aplikace Outlook. Mezi nejdůležitější členů tohoto objektu, patří:  
  
-   [Createitem –](http://msdn.microsoft.com/en-us/771707fb-5f34-473d-9fdf-09a6a7f55ece) metodu, která vám pomůže vytvořit novou položku například e-mailová zpráva, úlohy nebo schůzku.  
  
-   <xref:Microsoft.Office.Interop.Outlook._Application.Explorers%2A> Vlastnosti, která můžete použít pro přístup k systému windows, které zobrazovat obsah složky v uživatelském rozhraní (UI) aplikace Outlook.  
  
-   <xref:Microsoft.Office.Interop.Outlook._Application.Inspectors%2A> Vlastnosti, která můžete použít pro přístup k systému windows, které zobrazení obsahu jednu položku, například e-mailové zprávy nebo žádost o schůzku.  
  
 Získat instanci <xref:Microsoft.Office.Interop.Outlook.Application> objektu, použijte pole aplikace `ThisAddIn` třídy ve vašem projektu. Další informace najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
> [!NOTE]  
>  Abyste se vyhnuli upozornění zabezpečení při použití vlastnosti a metody, která jsou blokovaná ochrana modelů objektů aplikace Outlook, získat z pole s aplikací Outlook objekty `ThisAddIn` třídy. Další informace najdete v tématu [specifické aspekty zabezpečení pro řešení Office](../vsto/specific-security-considerations-for-office-solutions.md).  
  
### <a name="explorer-object"></a>Průzkumník objektů  
 <xref:Microsoft.Office.Interop.Outlook.Explorer> Objekt představuje okno, které zobrazí obsah složky, která obsahuje položky, jako je například e-mailové zprávy, úlohy nebo události. <xref:Microsoft.Office.Interop.Outlook.Explorer> Objekt obsahuje metody a vlastnosti, které můžete použít k úpravě okna a události, které se vyvolá, když okno změní.  
  
 Chcete-li získat <xref:Microsoft.Office.Interop.Outlook.Explorer> objektu, proveďte jednu z následujících akcí:  
  
-   Použití <xref:Microsoft.Office.Interop.Outlook._Application.Explorers%2A> vlastnost <xref:Microsoft.Office.Interop.Outlook.Application> objekt, který má přístup k veškerým <xref:Microsoft.Office.Interop.Outlook.Explorer> objektů v aplikaci Outlook.  
  
-   Použití <xref:Microsoft.Office.Interop.Outlook._Application.ActiveExplorer%2A> metodu <xref:Microsoft.Office.Interop.Outlook.Application> objekt, který chcete získat <xref:Microsoft.Office.Interop.Outlook.Explorer> , má právě fokus.  
  
-   Použijte metodu GetExplorer <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> objekt, který chcete získat <xref:Microsoft.Office.Interop.Outlook.Explorer> pro aktuální složku.  
  
### <a name="inspector-object"></a>Objekt Inspector  
 <xref:Microsoft.Office.Interop.Outlook.Inspector> Objekt představuje okno, které zobrazí jednu položku například e-mailová zpráva, úlohy nebo schůzku. <xref:Microsoft.Office.Interop.Outlook.Inspector> Objekt obsahuje metody a vlastnosti, které můžete použít k úpravě okna a události, které se vyvolá, když okno změní.  
  
 Chcete-li získat <xref:Microsoft.Office.Interop.Outlook.Inspector> objektu, proveďte jednu z následujících akcí:  
  
-   Použití <xref:Microsoft.Office.Interop.Outlook._Application.Inspectors%2A> vlastnost <xref:Microsoft.Office.Interop.Outlook.Application> objekt, který má přístup k veškerým <xref:Microsoft.Office.Interop.Outlook.Inspector> objektů v aplikaci Outlook.  
  
-   Použití <xref:Microsoft.Office.Interop.Outlook._Application.ActiveInspector%2A> metodu <xref:Microsoft.Office.Interop.Outlook.Application> objekt, který chcete získat <xref:Microsoft.Office.Interop.Outlook.Inspector> , má právě fokus.  
  
-   Použít metodu GetInspector konkrétní položky, jako například <xref:Microsoft.Office.Interop.Outlook.MailItem> nebo <xref:Microsoft.Office.Interop.Outlook.AppointmentItem>, k načtení Inspector, který je k ní přidružena.  
  
### <a name="mapifolder-object"></a>Objekt MAPIFolder  
 <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> Objekt představuje složku obsahující e-mailových zpráv, kontakty, úkoly a další položky. Outlook poskytuje 16 výchozí <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> objekty.  
  
 Výchozí hodnota <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> objekty jsou definovány <xref:Microsoft.Office.Interop.Outlook.OlDefaultFolders> hodnot výčtu. Například  
  
 Microsoft.Office.Interop.Outlook.OlDefaultFolders.olFolderInbox odpovídá **doručené pošty** složky aplikace Outlook.  
  
 Pro příklad, který ukazuje, jak pro přístup k výchozí <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> a vytvořte novou <xref:Microsoft.Office.Interop.Outlook.MAPIFolder>, najdete v části [postupy: Programové vytvoření vlastní položky složek](../vsto/how-to-programmatically-create-custom-folder-items.md).  
  
### <a name="mailitem-object"></a>Objekt MailItem  
 <xref:Microsoft.Office.Interop.Outlook.MailItem> Objekt představuje e-mailové zprávy. <xref:Microsoft.Office.Interop.Outlook.MailItem>objekty jsou obvykle ve složkách, jako například **doručené pošty**, **Odeslaná pošta**, a **pošta k odeslání**. <xref:Microsoft.Office.Interop.Outlook.MailItem>Zpřístupní vlastnosti a metody, které slouží k vytvoření a odeslání e-mailových zpráv.  
  
 Příklad, který ukazuje, jak vytvořit e-mailu, najdete v části [postupy: vytváření položek e-mailu prostřednictvím kódu programu](../vsto/how-to-programmatically-create-an-e-mail-item.md).  
  
### <a name="appointmentitem-object"></a>Objekt částí AppointmentItem  
 <xref:Microsoft.Office.Interop.Outlook.AppointmentItem> Objekt představuje schůzek, schůzku jednorázové nebo opakované události nebo meeting v **kalendáře** složky. <xref:Microsoft.Office.Interop.Outlook.AppointmentItem> Objekt obsahuje metody, které provedení akcí, například neodpovídá na požadavky nebo předávání žádosti o schůzku a vlastnosti, které zadejte podrobné informace o schůzce jako je například umístění a čas.  
  
 Příklad, který ukazuje, jak vytvořit událost, naleznete v části [postupy: vytváření požadavku na schůzku prostřednictvím kódu programu](../vsto/how-to-programmatically-create-a-meeting-request.md).  
  
### <a name="taskitem-object"></a>Objekt TaskItem  
 <xref:Microsoft.Office.Interop.Outlook.TaskItem> Objekt představuje úlohu provést v rámci zadaného časového rámce. <xref:Microsoft.Office.Interop.Outlook.TaskItem>objekty umístěné ve **úlohy** složky.  
  
 Chcete-li vytvořit úlohu, použijte [createitem –](http://msdn.microsoft.com/en-us/771707fb-5f34-473d-9fdf-09a6a7f55ece) metodu <xref:Microsoft.Office.Interop.Outlook.Application> objektu a předat hodnotu <xref:Microsoft.Office.Interop.Outlook.OlItemType.olTaskItem> pro parametr.  
  
### <a name="contactitem-object"></a>AssistantTelephoneNumber objektu  
 <xref:Microsoft.Office.Interop.Outlook.ContactItem>Objekt představuje kontakt v **kontakty** složky. <xref:Microsoft.Office.Interop.Outlook.ContactItem>objekty obsahují celou řadu kontaktní informace pro osoby, které představují, například poštovní adresu, e-mailových adres a telefonních čísel.  
  
 Příklad, který ukazuje, jak vytvořit nový kontakt, naleznete v části [postupy: přidávání ke kontaktům aplikace Outlook prostřednictvím kódu programu položku](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md). Příklad, který ukazuje, jak k vyhledání existujícího kontaktu, naleznete v části [postupy: hledání prostřednictvím kódu programu pro konkrétní kontakt](../vsto/how-to-programmatically-search-for-a-specific-contact.md).  
  
##  <a name="refdoc"></a>Pomocí dokumentace modelu objektů aplikace Outlook  
 Úplné informace o modelu objektů aplikace Outlook může být odkaz primární spolupracující sestavení (PIA) Outlook a VBA objektu modelu.  
  
### <a name="primary-interop-assembly-reference"></a>Odkaz sestavení primární spolupráce  
 Odkaz na aplikaci Outlook PIA dokumenty typy v sestavení primární spolupráce pro aplikaci Outlook 2010. Další informace najdete v tématu [odkaz sestavení aplikace Outlook 2010 primární zprostředkovatel komunikace s objekty](http://go.microsoft.com/fwlink/?LinkId=189580).  
  
 Kromě poskytování informací o pro všechny typy v PIA, tato dokumentace obsahuje také další informace o struktuře PIA a příklady kódu pro běžné úlohy automatizace aplikace Outlook.  
  
### <a name="vba-object-model-reference"></a>Odkaz na objekt modelu VBA  
 Reference objektu modelu VBA pro vytváření dokumenty objektový model aplikace Outlook, jako je zpřístupněné pro Visual Basic pro aplikace (VBA) kód. Další informace najdete v tématu [odkaz na objekt modelu Outlook 2010](http://go.microsoft.com/fwlink/?LinkId=199769).  
  
 Všechny objekty a členy ve model odkaz na VBA odpovídají typy a členy v PIA aplikace Outlook. Například odpovídá objektu Inspector ve model odkaz na VBA <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt v PIA aplikace Outlook. I když reference VBA objektu modelu poskytuje příklady kódu pro většinu vlastností, metod a událostí, pokud chcete používat v projektu doplňku VSTO Outlook, který vytvoříte pomocí musí překládat VBA kód v této referenci na Visual Basic a Visual C# Visual Studio.  
  
### <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Práce s položkami kontaktů](../vsto/working-with-contact-items.md)|Obsahuje témata, která ukazují, jak provádět úlohy s kontakty.|  
|[Práce s položkami pošty](../vsto/working-with-mail-items.md)|Obsahuje témata, která ukazují, jak provádět úlohy s položkami pošty.|  
|[Práce se složkami](../vsto/working-with-folders.md)|Obsahuje témata, která ukazují, jak provádět úlohy s složek.|  
|[Práce s položkami kalendáře](../vsto/working-with-calendar-items.md)|Obsahuje témata, která ukazují, jak provádět úlohy s položkami kalendáře.|  
|[Postupy: Určení aktuální položky aplikace Outlook prostřednictvím kódu programu](../vsto/how-to-programmatically-determine-the-current-outlook-item.md)|Ukazuje, jak zobrazit název v aktuální složce a některé informace o vybrané položce.|  
  