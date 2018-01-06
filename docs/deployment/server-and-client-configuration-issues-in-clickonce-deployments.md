---
title: "Server a problémy s konfigurací klienta v nasazeních ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications, ClickOnce
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- Windows applications, ClickOnce deployments
ms.assetid: 929e5fcc-dd56-409c-bb57-00bd9549b20b
caps.latest.revision: "33"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: b50dbe51f58af79b8c1074c592f98abccbe8ba7e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="server-and-client-configuration-issues-in-clickonce-deployments"></a>Problémy s konfigurací serveru a klienta v nasazeních ClickOnce
Pokud používáte Internetové informační služby (IIS) v systému Windows Server a nasazení obsahuje typ souboru, který nebyl rozpoznán Windows, jako je soubor aplikace Microsoft Word, služba IIS odmítne přenos souboru a nasazení se nezdaří.  
  
 Kromě toho některé webové servery a software webových aplikací, jako například [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], obsahuje seznam souborů a typy souborů, které nelze stáhnout. Například [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] zabraňuje stáhnout všechny soubory Web.config. Tyto soubory mohou obsahovat citlivé informace, například uživatelská jména a hesla.  
  
 Ačkoli toto omezení by nemělo způsobit žádné problémy pro stahování základní [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory jako manifestů a sestavení, toto omezení může zabránit stahování datových souborů, které jsou součástí vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. V [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], tuto chybu můžete vyřešit odstraněním obslužná rutina, která znemožňuje stahování těchto souborů ze Správce konfigurace služby IIS. Najdete v dokumentaci k serveru služby IIS pro další podrobnosti.  
  
 Některé webové servery mohou blokovat soubory s příponami, například .dll, .config a .mdf. Aplikace pro systém Windows obvykle zahrnují soubory s některé z následujících přípon. Pokud se uživatel pokusí spustit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci, která přistupuje k blokované souboru na webovém serveru, bude výsledkem chyba. Místo odblokování všech přípon souborů, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] publikuje soubor každé aplikace s příponou souboru ".deploy" ve výchozím nastavení. Správce proto musí nakonfigurovat webový server k odblokování tři soubory s následujícími příponami:  
  
-   .Application  
  
-   manifest  
  
-   .deploy  
  
 Však můžete tuto možnost zakážete zrušením **používat příponu souboru ".deploy"** možnost [dialogové okno publikování možnosti](http://msdn.microsoft.com/en-us/fd9baa1b-7311-4f9e-8ffb-ae50cf110592), v takovém případě musíte nakonfigurovat webový server k odblokování všechny přípony souborů použít v aplikaci.  
  
 Budete muset nakonfigurovat manifest, .application a .deploy, například pokud používáte službu IIS, kde jste nenainstalovali [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], nebo pokud používáte jiný webový server (například Apache).  
  
## <a name="clickonce-and-secure-sockets-layer-ssl"></a>ClickOnce a Secure Sockets Layer (SSL)  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace bude pracovat správně přes protokol SSL, s výjimkou případů, kdy aplikace Internet Explorer vyvolává dotaz o certifikátu SSL. Řádku může být vyvolána v případě, že problém se certifikát, například když názvy lokalit neodpovídají nebo certifikátu vypršela. Chcete-li [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] fungovat přes připojení SSL, ujistěte se, že certifikát je aktuální a že data certifikátu odpovídá data lokality.  
  
## <a name="clickonce-and-proxy-authentication"></a>ClickOnce a ověření proxy serverem  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]poskytuje podporu pro integrované ověřování systému Windows proxy od verze rozhraní .NET Framework 3.5. Žádné zvláštní směrnice machine.config jsou povinné. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]neposkytuje podporu pro jiné protokoly ověřování, jako je například základní nebo Digest.  
  
 Můžete také použít opravu hotfix pro rozhraní .NET Framework 2.0 tuto funkci povolíte. Další informace najdete v tématu http://go.microsoft.com/fwlink/?LinkId=158730.  
  
 Další informace najdete v tématu [ \<defaultProxy – > elementu (nastavení sítě)](/dotnet/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings).  
  
## <a name="clickonce-and-web-browser-compatibility"></a>ClickOnce a kompatibilita webového prohlížeče  
 V současné době [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] instalace se spustí pouze v případě, že adresa URL manifest nasazení je otevřena pomocí Internet Exploreru. Nasazení, jejichž adresa URL je spuštěna z jiné aplikace, jako je například aplikace Microsoft Office Outlook se úspěšně spustí jenom v případě, že Internet Explorer je nastaven jako výchozí webový prohlížeč.  
  
> [!NOTE]
>  Mozilla Firefox je podporována, pokud zprostředkovatel nasazení není prázdný, nebo je nainstalované rozhraní Microsoft .NET Framework pomocníka rozšíření. Tato přípona je obsažena v rozhraní .NET Framework 3.5 SP1. Pro podporu XBAP je modul plug-in NPWPF v případě potřeby aktivována.  
  
## <a name="activating-clickonce-applications-through-browser-scripting"></a>Aktivace aplikace ClickOnce pomocí skriptování webového prohlížeče  
 Pokud jste si vytvořili vlastní webové stránky, která spustí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí aktivní skriptování, můžete zjistit, že aplikace se nespustí na některých počítačích. Internet Explorer obsahuje nastavení, nazvané **Automatické dotazování při stahování souborů**, jenž ovlivňuje toto chování. Toto nastavení je dostupné na **zabezpečení** kartě v jeho **možnosti** nabídce, která ovlivňuje toto chování. Je volána **Automatické dotazování při stahování souborů**, a je uvedena pod **stáhne** kategorie. Je nastavena na **povolit** ve výchozím nastavení pro intranet webové stránky a k **zakázat** ve výchozím nastavení pro internetové webové stránky. Pokud toto nastavení je **zakázat**, všechny pokusy o aktivaci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace prostřednictvím kódu programu (například přiřazením jeho adresy URL `document.location` vlastnost) se zablokuje. V této situaci může uživatel spouštět aplikace pouze prostřednictvím stahování spouštěné uživateli, například kliknutím na hypertextový odkaz nastavený na adresu URL aplikace.  
  
## <a name="additional-server-configuration-issues"></a>Další problémy konfigurace serveru  
  
##### <a name="administrator-permissions-required"></a>Vyžaduje oprávnění správce  
 Při publikování s protokolem HTTP, musí mít oprávnění správce na cílovém serveru. Služba IIS vyžaduje tato úroveň oprávnění. Pokud nejsou publikování pomocí protokolu HTTP, pouze potřebujete oprávnění zapisovat na cílovou cestu.  
  
##### <a name="server-authentication-issues"></a>Problémy s ověřením serveru  
 Když publikujete na vzdálený server, který má "Anonymní přístup" vypnutý, zobrazí se následující upozornění:  
  
```  
"The files could not be downloaded from http://<remoteserver>/<myapplication>/.  The remote server returned an error: (401) Unauthorized."  
```  
  
> [!NOTE]
>  Můžete použít ověřování NTLM (NT výzvy a odezvy) fungovat, pokud lokalitě vyzve k zadání pověření, než výchozích pověření, a v dialogovém okně zabezpečení kliknete **OK** po zobrazení výzvy Pokud chcete uložit zadaných přihlašovací údaje pro budoucí relace. Toto řešení však nebude fungovat pro základní ověřování.  
  
## <a name="using-third-party-web-servers"></a>Používání jiných webových serverů  
 Pokud nasazujete [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci z webového serveru než IIS, může dojít k potížím Pokud server vrací nesprávný typ obsahu pro klíč [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory, třeba – manifest nasazení a manifest aplikace. Chcete-li vyřešit tento problém, naleznete v nápovědě váš webový server dokumentaci o tom, jak přidat nové typy obsahu k serveru a ujistěte se, že všechna mapování souboru název rozšíření uvedené v následující tabulce jsou na místě.  
  
|Přípona názvu souboru|Typ obsahu|  
|-------------------------|------------------|  
|`.application`|`application/x-ms-application`|  
|`.manifest`|`application/x-ms-manifest`|  
|`.deploy`|`application/octet-stream`|  
|`.msu`|`application/octet-stream`|  
|`.msp`|`application/octet-stream`|  
  
## <a name="clickonce-and-mapped-drives"></a>ClickOnce a mapované jednotky  
 Pokud používáte Visual Studio k publikování aplikace ClickOnce, nelze zadat mapované jednotky jako umístění instalace. Můžete však upravit aplikaci ClickOnce pro instalaci z mapované jednotky pomocí generátoru manifestu a editoru (Mage.exe a MageUI.exe). Další informace najdete v tématu [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) a [MageUI.exe (generování manifestu a nástroj pro úpravy, grafický klient)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client).  
  
## <a name="ftp-protocol-not-supported-for-installing-applications"></a>Protokol FTP není podporován pro instalaci aplikací  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]podporuje instalaci aplikací z jakéhokoliv HTTP 1.1 webového serveru nebo souborového serveru. FTP, protokol, není podporován pro instalaci aplikace. K publikování aplikací pouze pomocí funkce FTP. Následující tabulka shrnuje tyto rozdíly:  
  
|Typ adresy URL|Popis|  
|--------------|-----------------|  
|FTP: / /|Můžete publikovat [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí tohoto protokolu.|  
|http://|Můžete nainstalovat [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí tohoto protokolu.|  
|https://|Můžete nainstalovat [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí tohoto protokolu.|  
|File://|Můžete nainstalovat [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí tohoto protokolu.|  
  
## <a name="windows-xp-sp2-windows-firewall"></a>Systém Windows XP SP2: Brána Windows Firewall  
 Ve výchozím nastavení Windows XP SP2 umožňuje brány Windows Firewall. Pokud vyvíjíte aplikace na počítači s nainstalovaným systémem Windows XP, budete stále moci publikovat a spouštět [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace z místního serveru se spuštěnou službou IIS. Však nelze přistupovat k tomuto serveru z jiného počítače se službou IIS, pokud spustíte bránu Windows Firewall. Pokyny pro správu brány Windows Firewall, naleznete v nápovědě systému Windows.  
  
## <a name="windows-server-enable-frontpage-server-extensions"></a>Windows Server: Povolit serverová rozšíření FrontPage  
 Serverová rozšíření FrontPage od společnosti Microsoft je vyžadován pro publikování aplikací pro Windows webový server, který používá protokol HTTP.  
  
 Ve výchozím nastavení Windows Server nemá nainstalován serverová rozšíření FrontPage. Pokud chcete použít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Pokud chcete publikovat na webový Server Windows server, který používá protokol HTTP s serverová rozšíření FrontPage, jste serverová rozšíření FrontPage nejprve nainstalovat. Instalaci můžete provést pomocí nástroje pro správu Správa serveru v systému Windows Server.  
  
## <a name="windows-server-locked-down-content-types"></a>Systému Windows Server: Typy obsahu uzamčené  
 Služba IIS na [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] uzamyká všechny typy souborů s výjimkou některých známých typů obsahu (například htm, HTML, .txt a podobně). Chcete-li povolit nasazení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace pomocí tohoto serveru, budete muset změnit nastavení služby IIS pro povolení stahování souborů .application typu, manifest a u jiných typů vlastního souboru používá vaše aplikace.  
  
 Pokud nasadíte pomocí serveru služby IIS, spusťte inetmgr.exe a přidejte nové typy souborů pro výchozí webové stránky:  
  
-   Pro rozšíření .application a manifest musí být typ MIME "application/x-ms-application." Pro ostatní typy souborů musí být typ MIME "application/octet-stream."  
  
-   Pokud vytvoříte typ MIME s příponou "*" a typ MIME "application/octet-stream", bude možné typ odblokuje souborů ke stažení. (Však zablokovány soubor, který typy například .aspx a .asmx nelze stáhnout.)  
  
 Podrobné pokyny ke konfiguraci typů standardu MIME v systému Windows Server, nahlédněte do znalostní báze Microsoft Knowledge Base KB326965, "IIS 6.0 nemá není sloužit neznámé typy MIME" v [http://support.microsoft.com/default.aspx?scid=kb;en-us;326965](http://support.microsoft.com/default.aspx?scid=kb;en-us;326965).  
  
## <a name="content-type-mappings"></a>Mapování typu obsahu  
 Při publikování přes protokol HTTP, typ obsahu (také označované jako typ MIME) pro soubor .application by měla být "application/x-ms-application." Pokud máte [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] nainstalovaná na serveru, se nastaví pro vás automaticky. Pokud to není nainstalován, pak budete muset vytvořit přidružení typu MIME pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vroot aplikace (nebo celý server).  
  
 Pokud nasadíte pomocí serveru služby IIS, spusťte inetmgr.exe a přidejte nový typ obsahu "application/x-ms-application" pro příponu .application.  
  
## <a name="http-compression-issues"></a>Problémy komprese protokolu HTTP  
 S [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], můžete provést souborů ke stažení, které používají komprese protokolu HTTP, technologii webového serveru, který používá algoritmus GZIP kompresi datového proudu před odesláním do datového proudu pro klienta. Klient – v takovém případě [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]– dekomprimuje datový proud před čtení souborů.  
  
 Pokud používáte službu IIS, můžete snadno povolit kompresi HTTP. Ale když povolíte komprese protokolu HTTP, je povolena pouze pro některé typy souborů – konkrétně, soubory HTML a text. Pokud chcete povolit kompresi pro sestavení (.dll), XML (.xml), manifesty nasazení (.application) a manifesty aplikace (manifest), musíte přidat tyto typy souborů do seznamu typů pro služba IIS zkomprimovat. Dokud nepřidáte typy souborů do vašeho nasazení, bude komprimovat pouze text a soubory HTML.  
  
 Podrobné pokyny pro službu IIS najdete v tématu [určení typů další dokumentů pro kompresi HTTP](http://go.microsoft.com/fwlink/?LinkId=178459).  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)   
 [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [Nezbytné součásti nasazení aplikace](../deployment/application-deployment-prerequisites.md)