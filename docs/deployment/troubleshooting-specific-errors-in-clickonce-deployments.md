---
title: Řešení konkrétních chyb v nasazeních ClickOnce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.UncRequired
- Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.NoInstallUrl
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications, ClickOnce
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
ms.assetid: 22dfe8f1-8271-4708-9c25-6bbb13920ac8
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: b52caad3b6e4c98dd78e6c6be9835c11ac4d4175
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshooting-specific-errors-in-clickonce-deployments"></a>Řešení konkrétních chyb v nasazeních ClickOnce
Toto téma obsahuje následující běžné chyby, ke kterým dochází při nasazení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace a poskytuje postup řešení každého problému.  
  
## <a name="general-errors"></a>Obecné chyby  
  
#### <a name="when-you-try-to-locate-an-application-file-nothing-occurs-or-xml-renders-in-internet-explorer-or-you-receive-a-run-or-save-as-dialog-box"></a>Při pokusu vyhledat soubor .application, nedojde k žádné akci, nebo XML vykreslí v aplikaci Internet Explorer nebo se zobrazí dialogové okno spustit nebo uložit jako  
 Tato chyba je pravděpodobně způsobená typy obsahu (také označované jako typy MIME) nesprávně registrovanými na serveru nebo klienta.  
  
 Nejprve se ujistěte, že je server nakonfigurovaný pro přidružení příponu .application obsahu typ "application/x-ms-application".  
  
 Pokud server je nakonfigurován správně, ujistěte se, že [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] je v počítači nainstalována. Pokud [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] je nainstalován, a stále vidíte potíže, zkuste odinstalovat a znovu nainstalovat [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] se znovu registrovat, typu obsahu na straně klienta.  
  
#### <a name="error-message-says-unable-to-retrieve-application-files-missing-in-deployment-or-application-download-has-been-interrupted-check-for-network-errors-and-try-again-later"></a>Uvádí chybová zpráva "nelze načíst aplikaci. Soubory v nasazení chybí"nebo"stažení aplikace byla přerušena, zkontrolujte chyby sítě a zkuste to znovu později"  
 Tato zpráva znamená, že jeden nebo více souborů, které se odkazují [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty nelze stáhnout. Nejjednodušší způsob, jak ladit tato chyba se pokusí stáhnout adresu URL, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uvádí nelze stáhnout. Zde jsou některé možné příčiny:  
  
-   Pokud soubor protokolu říká "(403) zakázán" nebo "(404) Not found" Ověřte, že webový server je nakonfigurován tak, aby neblokovala stažení tohoto souboru. Další informace najdete v tématu [Server a problémy s konfigurací klienta v nasazeních ClickOnce](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md).  
  
-   Pokud soubor .config je blokován nastavením serveru, najdete v části "Chyba stažení při instalaci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci, která obsahuje soubor .config" dál v tomto tématu.  
  
-   Určete, jestli k situaci došlo proto `deploymentProvider` URL v manifestu nasazení odkazuje na jiné umístění než použitá adresa URL pro aktivaci.  
  
-   Ujistěte se, zda jsou všechny soubory nacházejí na serveru; [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] protokolu by měl zjistíte který soubor nebyl nalezen.  
  
-   Podívejte se, zda jsou problémy se síťovým připojením; Pokud klientský počítač přešel do režimu offline během stahování můžete tato zpráva se zobrazí.  
  
#### <a name="download-error-when-you-try-to-install-a-clickonce-application-that-has-a-config-file"></a>Chyba při pokusu o instalaci aplikace ClickOnce, která má soubor .config stažení  
 Ve výchozím nastavení zahrnuje soubor App.config aplikace pro systém Windows Visual Basic. Bude problém když se uživatel pokusí nainstalovat z webového serveru, který používá Windows Server 2003, protože daný operační systém blokuje instalaci soubory .config z bezpečnostních důvodů. Chcete-li povolit soubor .config k instalaci, klikněte na tlačítko **používat příponu souboru ".deploy"** v **možnosti publikování** dialogové okno.  
  
 Je třeba také nastavit typy obsahu (také označované jako typy MIME) správně .application, manifest a .deploy souborů. Další informace najdete v dokumentaci webového serveru.  
  
 Další informace najdete v tématu "Windows Server 2003: Locked-Down typy obsahu" v [Server a problémy s konfigurací klienta v nasazeních ClickOnce](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md).  
  
#### <a name="error-message-application-is-improperly-formatted-log-file-contains-xml-signature-is-invalid"></a>Chybová zpráva: "Aplikace je v nesprávném formátu;" Soubor protokolu obsahuje "podpis XML je neplatná."  
 Zkontrolujte aktualizaci souboru manifestu a znovu podepsaná. Znovu publikovat aplikace pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo pomocí Mage pro opětovné podepsání aplikace.  
  
#### <a name="you-updated-your-application-on-the-server-but-the-client-does-not-download-the-update"></a>Aktualizovat aplikaci na serveru, ale klient nestáhne aktualizace  
 Tento problém může vyřešit provedením jednoho z následujících úloh:  
  
-   Zkontrolujte `deploymentProvider` adresy URL v manifestu nasazení. Zkontrolujte aktualizaci bits ve stejném umístění, která `deploymentProvider` odkazuje na.  
  
-   Zkontrolujte interval aktualizace v manifestu nasazení. Pokud je tento interval nastavená pravidelný interval, jako je například jednou za šest hodin, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nebudou kontrolovat aktualizace, dokud tento interval byla úspěšná. Manifest kontrolovala aktualizace při každém spuštění aplikace, můžete změnit. Změna interval aktualizace je vhodná možnost během doby vývoje ověření probíhá instalace aktualizací, ale zpomaluje aktivaci aplikace.  
  
-   Zkuste znovu spustit aplikaci v nabídce Start. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] může mít zjištěny aktualizace na pozadí, ale zobrazí výzvu k instalaci při další aktivaci.  
  
#### <a name="during-update-you-receive-an-error-that-has-the-following-log-entry-the-reference-in-the-deployment-does-not-match-the-identity-defined-in-the-application-manifest"></a>Během aktualizace obdržíte chybu, která má následující záznam protokolu: "odkaz v nasazení neodpovídá identitě definované v manifestu aplikace"  
 Této chybě může dojít, protože jste ručně upravili manifesty nasazení a aplikace a způsobit popis identity sestavení v jednom manifestu synchronizován s druhým. Identita sestavení se skládá z jeho název, verzi, jazykovou verzi a tokenu veřejného klíče. Popisy identity ve vašem manifesty zkontrolujte a opravte případné rozdíly.  
  
#### <a name="first-time-activation-from-local-disk-or-cd-rom-succeeds-but-subsequent-activation-from-start-menu-does-not-succeed"></a>První aktivace z místního disku nebo disk CD-ROM úspěšná, ale neproběhne úspěšně následné aktivace z nabídky Start  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] používá adresu poskytovatel nasazení pro příjem aktualizací pro aplikaci. Ověřte správnost umístění, které je přejdete na adresu URL.  
  
#### <a name="error-cannot-start-the-application"></a>Chyba: "nelze spustit aplikaci"  
 Tato chybová zpráva obvykle znamená, že existuje problém instalace této aplikace do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uložit. Buď aplikace došlo k chybě nebo úložišti je poškozená. Soubor protokolu může zjistit, kde došlo k chybě.  
  
 Měli byste udělat následující:  
  
-   Ověřte, zda jsou všechny jedinečné identity manifest nasazení, identita manifestu aplikace a identity hlavní aplikace EXE.  
  
-   Ověřte, zda vaše cesty k souboru není delší než 100 znaků. Pokud vaše aplikace obsahuje cesty, které jsou příliš dlouhé, pravděpodobně překročil omezení na maximální cestu, kterou můžete uložit. Zkuste zkrátit cesty a znovu nainstalujte.  
  
#### <a name="privatepath-settings-in-application-config-file-are-not-honored"></a>Není dodrženo Nastavení PrivatePath v konfiguračním souboru aplikace  
 Pokud chcete používat PrivatePath (Fusion testování cest), aplikace musí požádat oprávnění úplný vztah důvěryhodnosti. Zkuste změnit manifest aplikace k vyžádání úplný vztah důvěryhodnosti a potom akci opakujte.  
  
#### <a name="during-uninstall-a-message-appears-saying-failed-to-uninstall-application"></a>Při odinstalaci se zobrazí zpráva, "Nepodařilo se odinstalovat aplikaci"  
 Tato zpráva se obvykle označuje, že aplikace již byla odebrána nebo úložiště je poškozený. Po kliknutí na tlačítko **OK**, **přidat nebo odebrat programy** položka bude odebrána.  
  
#### <a name="during-installation-a-message-appears-that-says-that-the-platform-dependencies-are-not-installed"></a>Během instalace zobrazí se zpráva s upozorněním, že nejsou nainstalovány závislosti platformy  
 Chybí předpoklad v mezipaměti GAC (globální mezipaměť sestavení), které aplikace potřebuje, aby bylo možné spustit.  
  
## <a name="publishing-with-visual-studio"></a>Publikování pomocí sady Visual Studio  
  
#### <a name="publishing-in-visual-studio-fails"></a>Selhání publikování v sadě Visual Studio  
 Zajistěte, abyste měli právo publikovat na server, kterou cílíte. Například pokud jste se přihlásili k počítači terminálového serveru jako běžný uživatel, ne jako správce, pravděpodobně nebudete mít práva potřebná k publikování do místního webového serveru.  
  
 Pokud publikujete pomocí adresy URL, zkontrolujte, zda cílový počítač serverová rozšíření FrontPage povolena.  
  
#### <a name="error-message-unable-to-create-the-web-site-site-the-components-for-communicating-with-frontpage-server-extensions-are-not-installed"></a>Chybová zpráva: Nelze vytvořit webovou stránku se\<lokality >'. Nejsou nainstalovány součásti pro komunikaci s serverová rozšíření FrontPage.  
 Ujistěte se, že máte součást sady Microsoft Visual Studio webové vytváření nainstalovaný na počítači, který publikujete z. Tato součást není pro uživatele Express nainstalována ve výchozím nastavení. Další informace najdete na webu [http://go.microsoft.com/fwlink/?LinkId=102310](http://go.microsoft.com/fwlink/?LinkId=102310).  
  
#### <a name="error-message-could-not-find-file-microsoftwindowscommon-controls-version6000-culture-publickeytoken6595b64144ccf1df-processorarchitecture-typewin32"></a>Chybová zpráva: Nelze najít soubor ' Microsoft.Windows.Common – ovládací prvky, verze 6.0.0.0, Culture = = *, PublicKeyToken = 6595b64144ccf1df, ProcessorArchitecture =\*, typ = win32.  
 Při pokusu o publikování aplikace WPF s povolenými vizuálními styly, zobrazí se tato chybová zpráva. Chcete-li tento problém vyřešit, najdete v části [postupy: publikování aplikace WPF s vizuální styly povoleny](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md).  
  
## <a name="using-mage"></a>Pomocí Mage  
  
#### <a name="you-tried-to-sign-with-a-certificate-in-your-certificate-store-and-a-received-blank-message-box"></a>Jste se pokusili přihlásit pomocí certifikátu do úložiště certifikátů a pole prázdné přijaté zprávy  
 V **podpisování** dialogové okno, musíte:  
  
-   Vyberte **přihlášení s certifikátem uložené**, a  
  
-   Vyberte certifikát ze seznamu; první certifikát není výchozí výběr.  
  
#### <a name="clicking-the-dont-sign-button-causes-an-exception"></a>Klepnutím na tlačítko "Bez podepisování" způsobí výjimku  
 Tento problém je známé chyby. Všechny [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] jsou vyžadovány k podepsání manifestů. Stačí vybrat jednu z možností podepisování a pak klikněte na **OK**.  
  
## <a name="additional-errors"></a>Další chyby  
 Následující tabulka uvádí některé běžné chybové zprávy, které klientský počítač uživatele mohou zobrazit, když uživatel nainstaluje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Každá zpráva Chyba je uvedena vedle popis nejvíce pravděpodobné příčiny chyby.  
  
|Chybová zpráva|Popis|  
|-------------------|-----------------|  
|Aplikaci nelze spustit. Obraťte se na vydavatele aplikace.<br /><br /> Nelze spustit aplikaci. Požádejte dodavatele aplikace o pomoc.|Toto jsou obecné chybové zprávy, které dojít, když aplikace nelze spustit, a naleznete žádný konkrétní důvod. Často to znamená, že aplikace je nějakým způsobem poškozena nebo který [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] úložiště je poškozeno.|  
|Nelze pokračovat. Aplikace je v nesprávném formátu. Pomoc, obraťte se na vydavatele aplikace.<br /><br /> Ověřování aplikací se nezdařilo. Nelze pokračovat.<br /><br /> Nelze načíst soubory aplikace. Soubory poškozený v nasazení.|Jeden ze souborů manifestu v nasazení není syntakticky správný, nebo obsahuje hodnotu hash, který nelze sjednotit pomocí odpovídající soubor. Tato chyba může taky znamenat, že manifest vložený uvnitř sestavení je poškozený. Znovu vytvořte nasazení a znovu zkompiluje vaší aplikace, nebo vyhledejte a opravte chyby ručně v vaše manifesty.|  
|Nelze načíst aplikaci. Došlo k chybě ověřování.<br /><br /> Instalace aplikace se nezdařilo. Nelze nalézt soubory aplikace na serveru. Požádejte o pomoc vydavateli aplikace nebo svého správce.|Jeden nebo více souborů v nasazení nelze stáhnout, protože nemáte oprávnění pro přístup k nim. Může to být způsobeno chybou 403 Zakázáno vrácený webový server, který může dojít, pokud jeden ze souborů ve vašem nasazení končí příponou, která si webový server s nimi zacházet jako na chráněný soubor. Adresář, který obsahuje jeden nebo více souborů aplikace může také vyžadovat uživatelské jméno a heslo pro přístup.|  
|Aplikaci nelze stáhnout. Aplikace chybí požadované soubory. Požádejte dodavatele aplikace nebo správce systému o pomoc.|Jeden nebo více souborů uvedených v manifestu aplikace nelze nalézt na serveru. Ověřte, zda odeslali soubory závislé všechna nasazení a zkuste to znovu.|  
|Stažení aplikace se nezdařilo. Zkontrolujte připojení k síti, nebo se obraťte na správce systému nebo poskytovatele síťové služby.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Nelze navázat síťové připojení k serveru. Zkontrolujte stav sítě a dostupnost serveru.|  
|URLDownloadToCacheFile se nezdařila s hodnotou HRESULT:\<číslo > ". Došlo k chybě při pokusu o stažení '\<soubor >'.|Pokud uživatel nastavil možnost rozšířené zabezpečení aplikace Internet Explorer "Upozornit při změně mezi zabezpečeným a není zabezpečený režim" na cílovém počítači, nasazení a adresy URL instalační program instaluje aplikace ClickOnce k lokalitě zabezpečené přesměrována z nezabezpečeného (nebo naopak), instalace se nezdaří, protože ji přeruší upozornění aplikace Internet Explorer.<br /><br /> To vyřešit, můžete provést jednu z těchto možností:<br /><br /> -Zrušte výběr možnosti zabezpečení.<br />-Ujistěte se, že není URL přesměrována takovým způsobem, který mění režimy zabezpečení.<br />-Úplně odeberte přesměrování a přejděte na adresu URL skutečné instalační program.|  
|Zápis na disk došlo k chybě. Může být nedostatek místa k dispozici na disku. Požádejte dodavatele aplikace nebo správce systému o pomoc.|To může znamenat nedostatek místa na disku pro uložení aplikace, ale může také to znamenat další obecné vstupně-výstupní chyba při ukládání souborů aplikace na jednotku.|  
|Nelze spustit aplikaci. Na disku není dostatek volného místa.|Pevný disk je zaplněn. Vyčistěte prostor a spusťte aplikaci znovu.|  
|Příliš mnoho nasazených aktivací se pokus o načtení najednou.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] omezuje počet různých aplikací, které můžete spustit ve stejnou dobu. Toto je z velké části k ochraně proti škodlivým pokusům o k zahájení denial-of-service útoky na místní [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] služeb; uživatelů, kteří se pokuste spustit stejnou aplikaci opakovaně, rychle za sebou, bude pouze ukončí jednu instanci aplikace.|  
|Zástupce nelze aktivovat přes síť.|Zástupce [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci lze spustit pouze na místní pevný disk. Nemohou být spuštěny tak, že otevřete adresu URL, která odkazuje na soubor zástupce na vzdáleném serveru.|  
|Aplikace je příliš velká pro spuštění v online v částečné důvěryhodnosti. Požádejte dodavatele aplikace nebo správce systému o pomoc.|Aplikaci, která běží v částečné důvěryhodnosti, nemůže být větší než polovinu velikost kvóty online aplikací, který ve výchozím nastavení je 250 MB.|  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)