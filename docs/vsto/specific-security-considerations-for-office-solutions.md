---
title: "Specifické aspekty zabezpečení pro řešení Office | Microsoft Docs"
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
- troubleshooting Office development in Visual Studio, security
- trusted code [Office development in Visual Studio]
- blocked code [Office development in Visual Studio]
- Outlook [Office development in Visual Studio], object model guard
- malicious code [Office development in Visual Studio]
- Outlook object model guard [Office development in Visual Studio]
- security [Office development in Visual Studio], troubleshooting
ms.assetid: 6a8b3e12-26c6-4ee2-a37e-d5bc8df9c5d1
caps.latest.revision: "51"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: bfe5505fdd861fb99c3f4d40abd0f17e066339b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="specific-security-considerations-for-office-solutions"></a>Specifické aspekty zabezpečení u řešení pro systém Office
  Funkce zabezpečení poskytuje rozhraní Microsoft .NET Framework a aplikace Microsoft Office může pomoct chránit vaše řešení pro systém Office před možnými hrozbami. Toto téma popisuje některé z těchto hrozeb a poskytuje doporučení, která pomáhá chránit proti. Zahrnuje také informace o vlivu řešení pro systém Office nastavení zabezpečení aplikace Microsoft Office.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="trusted-code-is-repurposed-in-a-new-malicious-document"></a>Důvěryhodné, že kód je znovu použít v nový Kyberzločinci dokument  
 Útočník může trvat důvěryhodný kód, který je určená pro jeden konkrétní účel, například stahování osobní údaje pro jejich zaměstnání aplikaci, a opakovaně ji používat do jiného dokumentu, jako je například na listu. Kód nebude vědět, že není spuštěn původního dokumentu a může otevře dalšími hrozbami, jako je například získat osobní údaje nebo provádění kódu s použitím zvýšená oprávnění, když je otevřen jiným uživatelem. Alternativně útočník můžete jednoduše změňte dat v listu tak, aby, odeslání do napadeného chová neočekávaně. Změnou hodnoty, vzorce nebo prezentace charakteristiky sešitu spojené s kódem se zlými úmysly k útoku na odesláním změněný soubor jiným uživatelem. Je také možné uživatelům přístup k informacím, které by neměl zobrazíte změnou hodnoty v listu.  
  
 Vzhledem k tomu, že umístění sestavení a umístění dokumentu musí mít dostatečně průkaznými materiály provést, není tento útok snadno připojit. Například dokumenty v e-mailových příloh, nebo v nedůvěryhodné intranetových serverů nemají dostatečná oprávnění ke spuštění.  
  
 Chcete-li možné tento útok, samotný kód musí být napsaná tak, že umožňuje rozhodnutí, která na základě dat o potenciálně nedůvěryhodným. Příkladem je vytvoření listu, který má skrytý buňku, která obsahuje název serveru databáze. Uživatel odešle listu pro stránky ASPX, která se pokusí o připojení k tomuto serveru pomocí ověřování SQL a heslo SA pevně. Útočník by mohl nahraďte obsah skrytá buňky jiný název počítače a získat heslo správce systému. Pokud chcete zabránit tento problém, nikdy pevný kód hesla a vždy zkontrolujte ID serveru vůči interní seznam serverů, které jsou známé dobré předcházet přístup k serveru.  
  
### <a name="recommendations"></a>Doporučení  
  
-   Vždycky ověřte vstup a data, zda pochází od uživatele, dokument, databáze, webová služba nebo jakýkoli jiný zdroj.  
  
-   Buďte opatrní vystavení konkrétní typy funkcí, jako je například získání privilegovaného dat jménem uživatele a umístit ho do nechráněných listu.  
  
-   V závislosti na typu aplikace může být vhodné ověřit, že původního dokumentu běží před provedením žádný kód. Ověřte například, zda je spuštěna z dokumentu uloží známé a bezpečné umístění.  
  
-   Může být vhodné zobrazit upozornění, když dokument se otevře, pokud aplikace provede všechny privilegované akce. Například může vytvořit úvodní obrazovka nebo spuštění dialogové okno oznamující, že aplikace přístup k osobním informacím a uživatel se rozhodnete pokračovat, nebo zrušit. Pokud koncový uživatel získá takové upozornění z zdánlivě nevinnosti dokumentu, bude moci ukončit aplikaci před nic dojde k ohrožení bezpečnosti.  
  
## <a name="code-is-blocked-by-the-outlook-object-model-guard"></a>Kód je blokována ochrana modelů objektů aplikace Outlook  
 Aplikace Microsoft Office můžete omezit kódu pomocí určité vlastnosti, metod a objekty v modelu objektu. Omezením přístupu k těmto objektům Outlook pomáhá zabránit červi, kteří e-mailu a viry pomocí objektový model zlými úmysly. Tato funkce zabezpečení se označuje jako ochrana modelů objektů aplikace Outlook. Pokud doplňku VSTO pokusí použít s omezeným přístupem vlastnosti nebo metody, když je povolená ochrana modelů objektů, zobrazí se upozornění zabezpečení, který umožňuje uživatelům zastavte operaci, nebo umožňuje uživatelům udělit přístup k vlastnosti nebo metody omezenou dobu čas. Pokud uživatel zastaví prováděnou operaci, vyvolá výjimku Outlook doplňků VSTO vytvořili pomocí řešení pro systém Office v sadě Visual Studio <xref:System.Runtime.InteropServices.COMException>.  
  
 Ochrana modelů objektů může ovlivnit doplňků VSTO různými způsoby v závislosti na tom, jestli se používá aplikace Outlook s Microsoft Exchange Server:  
  
-   Pokud aplikace Outlook se nepoužívá se serverem Exchange, může správce povolit nebo zakázat ochrana modelů objektů pro všechny doplňků VSTO na počítači.  
  
-   Pokud se serverem Exchange se používá aplikace Outlook, správce můžete povolit nebo zakázat ochrana modelů objektů pro všechny doplňků VSTO na počítači nebo může správce určit, že určité doplňků VSTO můžete spouštět bez zjištění ochrana modelů objektu. Správci mohou také upravit chování ochrana modelů objektů v určité oblasti objektový model. Například mohou správci automaticky povolit doplňků VSTO pro odeslání e-mailu prostřednictvím kódu programu, i když je povolená ochrana modelů objektu.  
  
 Spuštění v aplikaci Outlook 2007, chování ochrana modelů objektu se změnil na zlepšení uživatelského rozhraní pro vývojáře a uživatel současně pomáhá zabezpečit aplikace Outlook. Další informace najdete v tématu [zabezpečení změn kódu v aplikaci Outlook 2007](http://go.microsoft.com/fwlink/?LinkId=73429).  
  
### <a name="minimizing-object-model-guard-warnings"></a>Minimalizace objektu modelu ochrana upozornění  
 Abyste se vyhnuli upozornění zabezpečení při použití s omezeným přístupem vlastnosti a metody, ujistěte se, že vaše doplňku VSTO získává Outlook objekty z `Application` pole z `ThisAddIn` třídy ve vašem projektu. Další informace o tomto poli najdete v tématu [programování doplňků VSTO](../vsto/programming-vsto-add-ins.md).  
  
 Ochrana modelů objektu může být důvěryhodný pouze objekty aplikace Outlook získat z tohoto objektu. Naproti tomu objekty, které jsou získávány z nový objekt Microsoft.Office.Interop.Outlook.Application nejsou důvěryhodné, a s omezeným přístupem vlastnosti a metody se vyvolat upozornění zabezpečení, pokud je povolená ochrana modelů objektu.  
  
 Následující příklad kódu zobrazuje upozornění zabezpečení, pokud je povolená ochrana modelů objektu. Ochrana modelů objektu je omezený na vlastnosti třídy Microsoft.Office.Interop.Outlook.MailItem. Objekt Microsoft.Office.Interop.Outlook.MailItem není důvěryhodný, protože kód získá z Microsoft.Office.Interop.Outlook.Application, která je vytvořena pomocí **nové** operátor místo získání z `Application` pole.  
  
 [!code-csharp[Trin_VstcoreOutlookSecurity#1](../vsto/codesnippet/CSharp/Trin_VstcoreOutlookSecurity/ThisAddIn.cs#1)]
 [!code-vb[Trin_VstcoreOutlookSecurity#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreOutlookSecurity/ThisAddIn.vb#1)]  
  
 Následující příklad kódu ukazuje, jak používat s omezeným přístupem k vlastnosti Microsoft.Office.Interop.Outlook.MailItem objektu, který je důvěryhodný ochrana modelů objektu. Kód používá důvěryhodné `Application` pro získání Microsoft.Office.Interop.Outlook.MailItem.  
  
 [!code-csharp[Trin_VstcoreOutlookSecurity#2](../vsto/codesnippet/CSharp/Trin_VstcoreOutlookSecurity/ThisAddIn.cs#2)]
 [!code-vb[Trin_VstcoreOutlookSecurity#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreOutlookSecurity/ThisAddIn.vb#2)]  
  
> [!NOTE]  
>  Pokud se serverem Exchange se používá aplikace Outlook, získávání všechny objekty aplikace Outlook z `ThisAddIn.Application` není zaručeno, že vaše doplňku VSTO bude mít přístup k celé objektový model aplikace Outlook. Například pokud správce Exchange Outlook automaticky nastaví na hodnotu Odepřít všechny pokusy o informace o adrese přístup pomocí objektového modelu aplikace Outlook, potom aplikace Outlook nebude povolovat předchozí příklad kódu pro přístup na vlastnost, i když příklad kódu používá důvěryhodných `ThisAddIn.Application` pole.  
  
### <a name="specifying-which-add-ins-to-trust-when-using-exchange"></a>Určení které doplňky do vztahu důvěryhodnosti při používání systému Exchange  
 Pokud používají Outlook se Exchange, správci mohou určit, že určité doplňků VSTO můžete spouštět bez zjištění ochrana modelů objektu. Outlook doplňků VSTO vytvořili pomocí řešení pro systém Office v sadě Visual Studio nemůže být důvěryhodný samostatně. může být pouze důvěryhodné jako skupina.  
  
 Outlook důvěřuje VSTO doplňku založené na hodnotu hash souboru vstupní bod DLL doplňku VSTO. Všechny aplikace Outlook doplňků VSTO cílených [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] použít stejnou knihovnu vstupní bod DLL (VSTOLoader.dll). To znamená, že pokud správce důvěřuje žádné Add-in VSTO, která je cílena [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] běžet bez zjištění ochrana modelů objektu, pak všechny ostatní doplňků VSTO které cílí [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] jsou důvěryhodné. Další informace o důvěřující konkrétní doplňků VSTO běžet bez zjištění ochrana modelů objektů najdete v tématu [zadat metodu Outlook používá ke správě funkce prevence virů](http://go.microsoft.com/fwlink/?LinkId=128773).  
  
## <a name="permission-changes-do-not-take-effect-immediately"></a>Oprávnění změny se projeví okamžitě  
 Pokud správce upraví oprávnění pro dokument nebo sestavení, musí uživatelé ukončete a restartujte všechny aplikace Office pro tyto změny, která budou vynucena.  
  
 Jiné aplikace, které jsou hostiteli aplikace Microsoft Office může bránit také nová oprávnění z vynucení. Uživatelé musí ukončit všechny aplikace, které používají Office, hostované nebo samostatný, pokud došlo ke změně zásady zabezpečení.  
  
## <a name="trust-center-settings-in-the-microsoft-office-system-do-not-affect-add-ins-or-document-level-customizations"></a>Centrum zabezpečení pro nastavení v systému Microsoft Office nemá vliv na doplňky nebo úpravy na úrovni dokumentů  
 Uživatelé mohou zabránit doplňků VSTO načítání nastavením možnost v **Centrum zabezpečení**. Však nejsou doplňků VSTO a úpravy na úrovni dokumentů vytvořené pomocí řešení pro systém Office v sadě Visual Studio ovlivněny tato nastavení vztahu důvěryhodnosti.  
  
 Pokud uživatel brání doplňků VSTO z načítání pomocí **Centrum zabezpečení**, následující typy doplňků VSTO nenačte:  
  
-   Spravovanými a nespravovanými COM doplňků VSTO.  
  
-   Spravovanými a nespravovanými Chytré dokumenty.  
  
-   Spravovanými a nespravovanými automatizace doplňků VSTO.  
  
-   Komponenty spravovaných a nespravovaných dat v reálném čase.  
  
 Následující postupy popisují, jak mohou uživatelé používat **Centrum zabezpečení** omezit doplňků VSTO z načítání v aplikaci Microsoft [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] a Microsoft Office 2010. Tyto postupy neovlivňují doplňků VSTO nebo úprav vytvořili pomocí nástroje pro vývoj pro Office v sadě Visual Studio.  
  
#### <a name="to-disable-vsto-add-ins-in-microsoft-office-2010-and-microsoft-includeoffice15shortvstoincludesoffice-15-short-mdmd-applications"></a>Chcete-li zakázat doplňků VSTO v Microsoft Office 2010 a Microsoft [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] aplikace  
  
1.  Vyberte **souboru** kartě.  
  
2.  Vyberte *ApplicationName* **možnosti** tlačítko.  
  
3.  V podokně kategorie, zvolte **Centrum zabezpečení**.  
  
4.  V podokně podrobností vyberte **nastavení Centra zabezpečení**.  
  
5.  V podokně kategorie, zvolte **doplňky**.  
  
6.  V podokně podrobností vyberte **aplikace vyžadují doplňků být podepsané důvěryhodným vydavatelem** nebo **zakažte všechny aplikace doplňků**.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
  
  