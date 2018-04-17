---
title: Zabezpečování aplikací ClickOnce | Microsoft Docs
ms.custom: ''
ms.date: 02/17/2017
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce security
- ClickOnce deployment, security
- deploying applications, ClickOnce security
ms.assetid: a05b5f2f-d1f2-471a-8096-8b11f7554265
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 8f41fb12c8ec9a5a3cec0a802f7fc5b4216a39d6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="securing-clickonce-applications"></a>Zabezpečování aplikací ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace podléhají omezením zabezpečení přístupu kódu v rozhraní .NET Framework ke omezení přístupu k chráněným prostředkům a operace. Z tohoto důvodu je důležité, že rozumíte důsledkům zabezpečení přístupu kódu k zápisu vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace odpovídajícím způsobem. K omezení přístupu mohou vaše aplikace používat plnou důvěryhodnost nebo částečné zóny, jako jsou zóny pro Internet a Intranet.  
  
 Dále lze použít technologii ClickOnce využívající certifikáty k ověření pravosti vydavatele a podepisování manifestů aplikace a nasazení, která ověřuje, zda se soubory nebylo manipulováno. Podepisování je volitelný krok, který usnadňuje změnu souborů aplikace po vytvoření manifestů. Bez podepsaných manifestů je však obtížné zajistit, aby nebylo s instalačním programem manipulováno při bezpečnostních útocích prostředníkem. Chcete-li aplikaci zabezpečit, doporučujeme vám, abyste podepsali manifesty aplikace a nasazení.  
  
## <a name="zones"></a>Zóny  
 Aplikace, které jsou nasazeny pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] technologie jsou omezeny na sadu akcí, které jsou definovány zóny zabezpečení a oprávnění. Zóny zabezpečení jsou definovány v aplikaci Internet Explorer a jsou založeny na umístění aplikace. V následující tabulce jsou uvedena výchozí oprávnění na základě umístění nasazení:  
  
|Umístění nasazení|Zóna zabezpečení|  
|-------------------------|-------------------|  
|Spuštění z webu|Zóna Internetu|  
|Instalace z webu|Zóna Internetu|  
|Instalace ze sdíleného síťového umístění|Zóna Místního intranetu|  
|Instalace z disku CD-ROM|Plná důvěryhodnost|  
  
 Výchozí oprávnění jsou založena na umístění, ze kterého byla nasazena původní verze aplikace; aktualizace aplikace tato oprávnění zdědí. Pokud je aplikace nakonfigurována pro vyhledání aktualizací z webového nebo síťového umístění a je k dispozici novější verze, mohou původní instalace namísto oprávnění plné důvěryhodnosti přijímat oprávnění pro zónu Internetu nebo Intranetu. Chcete-li zabránit v zobrazování výzev uživatelům, může správce systému zadat zásady nasazení technologie ClickOnce, které definují konkrétního vydavatele aplikace jako důvěryhodný zdroj. Pro počítače, na kterých je tato zásada nasazena, budou oprávnění udělena automaticky a uživateli nebude zobrazena žádná výzva. Další informace najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md). Chcete-li konfigurovat nasazení důvěryhodné aplikace, lze certifikát nainstalovat na úrovni počítače nebo podniku. Další informace najdete v tématu [postupy: Přidání důvěryhodného vydavatele ke klientskému počítači pro aplikace ClickOnce](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md).  
  
## <a name="code-access-security-policies"></a>Zásady zabezpečení přístupu kódu  
 Určuje oprávnění pro aplikaci nastavení na [ \<trustInfo > Element](../deployment/trustinfo-element-clickonce-application.md) element manifestu aplikace. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky generuje tyto informace podle nastavení v projektu **zabezpečení** stránku vlastností. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace jsou udělena pouze konkrétní oprávnění, která požaduje. V případech, kdy například přístup k souborům vyžaduje oprávnění plné důvěryhodnosti, pokud aplikace požaduje oprávnění přístupu k souborům, bude uděleno pouze oprávnění přístupu k souborům, nikoli oprávnění plné důvěryhodnosti. Při vývoji vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, měli byste zajistit, abyste si vyžádali pouze konkrétní oprávnění, které aplikace potřebuje. Ve většině případů můžete nastavit omezení aplikace na částečnou důvěryhodnost pomocí zóny Internetu a Místního intranetu. Další informace najdete v tématu [postupy: nastavení zóny zabezpečení pro aplikaci ClickOnce](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md). Pokud aplikace požaduje vlastní oprávnění, můžete vytvořit vlastní zónu. Další informace najdete v tématu [postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
 Pokud použijete oprávnění, které není součástí výchozího oprávnění nastaveného pro zónu, ze které je aplikace nasazena, zobrazí se koncovému uživateli při instalaci nebo aktualizaci výzva k udělení oprávnění. Chcete-li zabránit v zobrazování výzev uživatelům, může správce systému zadat zásady nasazení technologie ClickOnce, které definují konkrétního vydavatele aplikace jako důvěryhodný zdroj. Na počítačích, na kterých je tato zásada nasazena, budou oprávnění udělena automaticky a uživateli nebude zobrazena žádná výzva.  
  
 Jako vývojář se musíte přesvědčit, zda lze aplikaci spustit i s příslušnými oprávněními. Pokud aplikace po spuštění požádá o oprávnění mimo zónu, může se zobrazit výjimka zabezpečení. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] umožňuje ladění aplikace v cílové zóně zabezpečení. a poskytuje nápovědu při vývoji zabezpečení aplikací. Další informace najdete v tématu [postupy: ladění aplikace ClickOnce s omezenými oprávněními](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md).  
  
 Další informace o zabezpečení přístupu kódu a ClickOnce najdete v tématu [zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).  
  
## <a name="code-signing-certificates"></a>Certifikáty podepisování kódu  
 K publikování aplikace pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, můžete si manifestů aplikace a nasazení pro aplikaci pomocí pár veřejného a privátního klíče. Nástroje pro podepsání manifestu jsou k dispozici na **podpisování** stránky **Návrhář projektu**. Další informace najdete v tématu [stránka podepisování, Návrhář projektu](../ide/reference/signing-page-project-designer.md). Alternativně můžete podepsat manifesty se soubor klíče během procesu publikování pomocí Průvodce publikováním.  
  
 Po podepsání manifestů jsou informace o vydavateli aplikace založené na signatuře technologie Authenticode zobrazeny uživateli při instalaci v dialogovém okně oprávnění, a to proto, aby uživatel věděl, že aplikace pochází z důvěryhodného zdroje.  
  
 Další informace o ClickOnce a certifikáty, najdete v části [ClickOnce a kód Authenticode](../deployment/clickonce-and-authenticode.md).  
  
## <a name="aspnet-form-based-authentication"></a>Ověřování založené na formulářích ASP.NET  
 Pokud chcete řídit nasazení, které může každý uživatel, by neměla být povolena anonymní přístup k [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nasazené na webovém serveru. Místo toho byste měli povolit uživatelům přístup k nainstalovaným nasazením na základě identity uživatele pomocí ověřování systému Windows.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nepodporuje ověřování pomocí formulářů technologie ASP.NET, protože používá trvalé soubory cookie. Tyto představovat bezpečnostní riziko, protože se nenachází v mezipaměti v aplikaci Internet Explorer a může hacker. Proto pokud nasazujete [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, žádný scénář ověřování kromě ověřování systému Windows není podporována.  
  
## <a name="passing-arguments"></a>Předávání argumentů  
 K posouzení další bezpečnostní dochází, pokud máte předání argumentů do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] umožňuje vývojářům zadat řetězec dotazu do aplikace nasazené prostřednictvím webu. Řetězec dotazu má formu řady párů názvu a hodnoty na konci adresy URL určených ke spuštění aplikace:  
  
 `http://servername.adatum.com/WindowsApp1.application?username=joeuser`  
  
 Argumenty řetězce dotazu jsou zakázány. Chcete-li povolit je atribut `trustUrlParameters` musí být nastavena v manifestu nasazení aplikace. Tato hodnota se dá nastavit z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a z MageUI.exe. Podrobné pokyny k povolení předávání řetězce dotazu, najdete v části [postupy: načtení informací řetězce dotazu v Online aplikace ClickOnce](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).  
  
 Nikdy byste neměli předávat argumenty načtené pomocí řetězce dotazu do databáze nebo příkazového řádku bez ověřování argumentů a zajištění jejich bezpečnosti. Nebezpečné argumenty jsou argumenty s řídicími znaky databáze nebo příkazového řádku, které by mohly umožnit uživateli se zlými úmysly manipulaci s aplikací a provádění libovolných příkazů.  
  
> [!NOTE]
>  Argumenty řetězce dotazu jsou pouze způsobem předání argumentů [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] při spuštění aplikace. Nelze předat argumenty [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace z příkazového řádku.  
  
## <a name="deploying-obfuscated-assemblies"></a>Nasazení obfuskovaných sestavení  
 Visual Studio zahrnuje bezplatnou [preemptivní ochrana – Dotfuscatoru Community Edition](../ide/dotfuscator/index.md), který můžete použít k ochraně vašich aplikací ClickOnce pomocí kódu maskováním a aktivní ochranu míry.  Podrobnosti najdete v tématu [části ClickOnce v uživatelské příručce Dotfuscatoru Community Edition](https://www.preemptive.com/dotfuscator/ce/docs/help/5.27/advanced_clickonce.html).

## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)