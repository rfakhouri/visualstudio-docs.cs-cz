---
title: "Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí | Microsoft Docs"
ms.custom: 
ms.date: 2015-10-04
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: coded UI tests
ms.assetid: 544742b5-4ec1-4d51-b941-72b2f6ff17bc
caps.latest.revision: "106"
ms.author: douge
manager: douge
ms.openlocfilehash: de0ce914e61f6fd3dc3eb227496b09e77c37be57
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings"></a>Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí
Podporované konfigurace a platformy pro programové testy uživatelského rozhraní pro Visual Studio Enterprise jsou uvedeny v následující tabulce. Tyto konfigurace platí také pro zaznamenávání akcí, které jsou vytvořeny pomocí [!INCLUDE[MTRlong](../test/includes/mtrlong_md.md)].  
  
> [!NOTE]
>  Programový test UI musí mít stejná oprávnění jako testovaná aplikace.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
## <a name="supported-configurations"></a>Podporované konfigurace  
  
|Konfigurace|Podporováno|  
|-------------------|---------------|  
|Operační systémy:|[!INCLUDE[win7](../debugger/includes/win7_md.md)]<br /><br /> [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)]<br /><br /> [!INCLUDE[win8](../debugger/includes/win8_md.md)]<br /><br /> Windows 10|  
|Podpora 32bitové/64bitové verze|32bitová verze Windows, která běží 32bitová verze [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] můžete otestovat 32bitové aplikace.<br /><br /> 64bitová verze Windows, která běží 32bitová verze [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] můžete otestovat 32bitové WOW aplikace, které mají Synchronization.n uživatelského rozhraní.<br /><br /> 64bitová verze Windows, která běží 32bitová verze [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] můžete otestovat 64bitová verze Windows Forms a WPF aplikace, které nemají synchronizace uživatelského rozhraní.|  
|Architektura|x86 a x64 **Poznámka:** Internet Exploreru se nepodporuje v režimu 64-bit kromě při spuštění v rámci [!INCLUDE[win8](../debugger/includes/win8_md.md)] nebo novější verze.|  
|.NET|.NET 2.0, 3.0, 3.5, 4 a 4.5. **Poznámka:** [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] a Visual Studio budou vyžadovat .NET 4 pracovat.   Nicméně aplikace vyvinuté pomocí uvedených verzí rozhraní .NET jsou podporovány.|  
  
> [!NOTE]
>  *Synchronizace uživatelského rozhraní* je funkce, kde je přehrávání ověřený v každé řízení fronty zpráv. Pokud ovládací prvek neodpověděl na událost, která mu byla zaslána, událost je odeslána znovu.  
  
## <a name="platform-support"></a>Podpora platformy  
  
|Platforma|Úroveň podpory|  
|--------------|----------------------|  
|Aplikace Windows Phone|Pouze WinRT XAML na základě Phone podporované aplikace.|  
|Aplikace UWP|Jsou podporovány pouze aplikace UWP založených na XAML.|  
|Univerzální aplikace pro Windows|Jsou podporovány pouze založených na XAML univerzálních aplikací pro Windows Phone nebo plochy.|  
|Edge|V sadě Visual Studio 2015 Update 2 a později pomocí [programového testování uživatelského rozhraní mezi prohlížeče rozšíření](https://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d)|  
|Internet Explorer 8<br /><br /> Internet Explorer 9<br /><br /> Internet Explorer 10 **důležité:** Internet Explorer 10 je podporována pouze na ploše. <br /><br /> Internet Explorer 11 **důležité:** aplikace Internet Explorer 11 je podporována pouze na ploše.|Plně podporováno.<br /><br /> -   **Podpora pro HTML5 v aplikaci Internet Explorer 9 a Internet Explorer 10:** testů uživatelského rozhraní programového podporu záznam, přehrávání a ověření ovládacích prvků HTML5: zvuk, Video, ProgressBar a posuvníku. Další informace najdete v tématu [pomocí ovládacích prvků HTML5 v programových testů uživatelského rozhraní](../test/using-html5-controls-in-coded-ui-tests.md). **Upozornění:** Pokud vytvoříte programové testy uživatelského rozhraní v Internet Exploreru 10, se nemusí být možné spustit pomocí aplikace Internet Explorer 9 nebo Internet Explorer 8. Je to proto, že aplikace Internet Explorer 10 obsahuje ovládací prvky HTML5, jako je Zvuk, Video, Indikátor průběhu a Posuvník. Tyto ovládací prvky jazyka HTML5 nejsou rozpoznány aplikací Internet Explorer 9 nebo Internet Explorer 8. Podobně váš programový test UI pomocí aplikace Internet Explorer 9 může zahrnovat některé ovládací prvky jazyka HTML5, které aplikace Internet Explorer 8 nerozpozná.<br />-   **Podpora pro Internet Explorer 10 kontrola pravopisu:** Internet Explorer 10 obsahuje všechna textová pole kontrolu pravopisu. Můžete provádět výběr ze seznamu navrhovaných oprav. Programový test UI bude ignorovat akce uživatele, jako je volba návrhu alternativního pravopisu. Bude zaznamenán pouze konečný text zadaný do textového pole.<br />     Tyto akce jsou zaznamenány pro programový test UI používající ovládací prvek kontroly pravopisu: Přidat do slovníku, Kopírovat, Vybrat vše, Přidat do slovníku a Ignorovat.<br />-   **Podpora pro 64bitové verze Internet Exploreru spuštěna pod Windows 8:** dříve, nejsou podporované 64bitové verze aplikace Internet Explorer pro záznam a přehrávání. S [!INCLUDE[win8](../debugger/includes/win8_md.md)] a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], programových testů uživatelského rozhraní byly povoleny pro 64bitové verze aplikace Internet Explorer. **Upozornění:** podpora 64bitových technologií pro Internet Explorer platí, pouze pokud používáte [!INCLUDE[win8](../debugger/includes/win8_md.md)] nebo novější.<br />-   **Podpora pro připnutý weby v Internet Exploreru 9:** v aplikaci Internet Explorer 9, byly zavedeny definovaného lokalit. Díky funkci Připnuté weby se můžete dostat na své oblíbené weby přímo z hlavního panelu systému Windows – bez nutnosti nejdříve spustit aplikaci Internet Explorer. Programové testy UI nyní mohou generovat akce podporující záměr na připnutých webech. Další informace o definovaného lokality najdete v tématu [připnutý lokality](http://go.microsoft.com/fwlink/?LinkId=220037).<br />-   **Podpora pro Internet Explorer 9 sémantického značky:** aplikace Internet Explorer 9 zavedly následující sémantického značky: část, navigaci, článek, vyhraďte, hgroup, záhlaví, zápatí, obrázek, figcaption a označit. Programové testy UI ignorují během záznamu všechny tyto sémantické značky. Pomocí Tvůrce programového testu UI můžete přidat do těchto značek kontrolní výrazy. K procházení všech těchto prvků a zobrazení jejich vlastností můžete použít Navigační vytáčení v Tvůrci programového testu UI.<br />-   **Plynulé zpracování z prázdné znaky mezi verze aplikace Internet Explorer:** jsou mezi aplikace Internet Explorer 8, Internet Explorer 9 a Internet Explorer 10 rozdíly ve zpracování prázdné znaky. Programový test UI zpracovává tyto rozdíly bez problémů. Proto se například bude programový test UI vytvořený v aplikaci Internet Explorer 8 přehrávat úspěšně v aplikaci Internet Explorer 9 a Internet Explorer 10.<br />-   **Oznámení oblasti z Internet Explorer jsou nyní zaznamenávají s nastavit "Pokračovat v Error" atribut:** všechny akce v oznamovací oblasti Internet Exploreru se teď zaznamenávají s nastaveným atributem "Pokračovat v chyba". Pokud se během přehrávání nezobrazí panel oznámení, akce na něm budou ignorovány a programový test UI bude pokračovat další akcí.|  
|Ovládací prvky rozhraní Windows Forms a WPF třetích stran|Plně podporováno.<br /><br /> Chcete-li povolit ovládací prvky třetích stran v rozhraních Windows Forms a WPF, musíte přidat odkazy a kód. Další informace najdete v tématu [povolení programového testování z vaše ovládacích prvků uživatelského rozhraní](../test/enable-coded-ui-testing-of-your-controls.md).|  
|Aplikace Internet Explorer 6<br /><br /> Internet Explorer 7|Není podporováno.|  
|Chrome<br /><br /> Firefox|Záznam kroků akcí není podporován. Programové testy UI můžete přehrát v prohlížečích Chrome a Firefox, pokud používáte sadu Visual Studio 2012 s aktualizací 4 nebo novější. Přejděte [sem](http://msdn.microsoft.com/library/jj835758.aspx) další podrobnosti.|  
|Opera<br /><br /> Safari|Není podporováno.|  
|Silverlight|Není podporováno.<br /><br /> Pro Visual Studo 2013 však můžete stáhnout [Microsoft Visual Studio 2013 programového uživatelského rozhraní zásuvný modul pro testování pro Silverlight](https://go.microsoft.com/fwlink/?LinkId=691026) z Galerie Visual Studio.|  
|Flash nebo Java|Není podporováno.|  
|Windows Forms 2.0 a vyšší|Plně podporováno. **Poznámka:** NetFx ovládací prvky jsou plně podporované, ale ne všechny ovládací prvky jiných výrobců jsou podporovány.|  
|WPF 3.5 a novější|Plně podporováno.<br /><br /> **Poznámka:** NetFx ovládací prvky jsou plně podporované, ale ne všechny ovládací prvky jiných výrobců jsou podporovány.|  
|Windows Win32|Může pracovat s některými známými problémy, ale není oficiálně podporována.|  
|MFC|Částečně podporováno. Najdete zde [webu společnosti Microsoft](http://go.microsoft.com/fwlink/?LinkId=206511) podrobnosti o jaké funkce jsou podporované.|  
|SharePoint|Plně podporováno.|  
|Klientské aplikace Office|Není podporováno.|  
|Webový klient Dynamics CRM|Plně podporováno.|  
|Klient Dynamics (Ax) 2012|Záznam a přehrávání akce jsou podporovány jen částečně. Najdete zde [webu společnosti Microsoft](http://go.microsoft.com/fwlink/?LinkId=232677) podrobnosti.|  
|SAP|Není podporováno.|  
|Citrix/Terminálové služby|Nedoporučujeme záznam akcí na serveru. Záznam nepodporuje spuštěním několika instancí ve stejnou dobu.|  
|PowerBuilder|Částečně podporováno.<br /><br /> Podpora se provádí v rozsahu, ve kterém je povoleno usnadnění pro ovládací prvky aplikace PowerBuilder.|  
  
 Informace o tom, jak vytvořit rozšíření, které podporují jiné platformy najdete v tématu [povolení programového testování z vaše ovládacích prvků uživatelského rozhraní](../test/enable-coded-ui-testing-of-your-controls.md) a [rozšiřování programových testů uživatelského rozhraní a zaznamenávání akcí do podpory aplikace Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md).  
  
## <a name="see-also"></a>Viz také  
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Generování programových testů UI ze stávajícího záznamu akcí](/devops-test-docs/test/generating-a-coded-ui-test-from-an-existing-action-recording)
