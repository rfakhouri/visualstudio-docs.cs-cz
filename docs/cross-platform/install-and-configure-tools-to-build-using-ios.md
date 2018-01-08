---
title: "Instalace a konfigurace nástroje pro sestavení pomocí iOS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d0c311c9-9eb9-42c5-ba07-25604362cd28
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: xplat-cplusplus
ms.openlocfilehash: 734c7b8a8416503e457f964d74e0a3773cbada2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="install-and-configure-tools-to-build-using-ios"></a>Instalace a konfigurace nástroje pro sestavení pomocí iOS
Visual C++ pro vývoj mobilních řešení pro různé platformy můžete použít k úpravám, ladění a nasazení iOS kódu simulátoru iOS nebo zařízení s iOS, ale kvůli licenční omezení, musí být kód vytvořené a spouštět vzdáleně na macu. Sestavení a spuštění aplikace pro iOS pomocí sady Visual Studio, budete muset nastavit a konfigurovat vzdáleného agenta [vcremote](http://go.microsoft.com/fwlink/p/?LinkId=534988), na vaše Mac. Obslužné rutiny vzdáleného agenta sestavení požadavky ze sady Visual Studio a spustí aplikace na zařízení s iOS připojené k počítači Mac, nebo v simulátoru na Mac. iOS  
  
> [!NOTE]
>  Informace o používání služeb hostovaných v cloudu Mac místo Mac najdete v tématu [vytváření a simulace iOS v cloudu](https://taco.visualstudio.com/en-us/docs/build_ios_cloud/). Tyto pokyny jsou pro sestavování pomocí nástrojů Visual Studio pro Apache Cordova. Chcete-li postupujte podle pokynů k sestavení pomocí Visual C++ pro vývoj mobilních řešení pro různé platformy, nahraďte vcremote pro vs-mda vzdálené.  
  
 Po instalaci nástroje pro sestavení pomocí iOS, najdete v tomto tématu pro způsoby, jak rychle nakonfigurovat a aktualizovat vzdáleného agenta pro vývoj pro iOS v sadě Visual Studio a na vaše Mac.  
  
 [Požadavky](#Prerequisites)  
  
 [Instalace vzdáleného agenta pro iOS](#Install)  
  
 [Spuštění vzdáleného agenta](#Start)  
  
 [Konfigurace vzdáleného agenta v sadě Visual Studio](#ConfigureVS)  
  
 [Vygenerování nového zabezpečení PIN kódu](#GeneratePIN)  
  
 [Vygenerovat nový certifikát serveru](#GenerateCert)  
  
 [Konfigurace vzdáleného agenta na Mac](#ConfigureMac)  
  
##  <a name="Prerequisites"></a>Požadavky  
 K instalaci a použití vzdáleného agenta k vývoji kódu pro iOS, musíte nejprve mít tyto požadavky:  
  
-   Počítač Mac se systémem OS X Mavericks nebo novější  
  
-   [Apple ID](https://appleid.apple.com/)  
  
-   Aktivní [iOS Developer Program](https://developer.apple.com/programs/ios/) účet s Apple  
  
-   [Xcode 6](https://developer.apple.com/xcode/downloads/)  
  
     Xcode 6 si můžete stáhnout z obchodu s aplikacemi.  
  
-   Nástroje příkazového řádku Xcode  
  
     Instalace nástrojů pro příkazový řádek Xcode, otevřete aplikaci Terminálové na počítači Mac a zadejte následující příkaz:  
  
     `xcode-select --install`  
  
-   IOS podepisování identitu nakonfigurovanou v Xcode  
  
     Podrobné informace o získání iOS identitu podepisování najdete v tématu [zachování identity vaše podepisování a certifikáty](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingCertificates/MaintainingCertificates.html) v knihovně iOS Developer Library. V tématu nebo nastavit podpisové identity v Xcode, otevřete **Xcode** nabídky a zvolte **Předvolby**. Vyberte **účty** a zvolte Apple ID a pak **zobrazit podrobnosti** tlačítko.  
  
-   Pokud používáte zařízení s iOS pro vývoj, profil zřizování pro vaše zařízení nakonfigurovaná v Xcode  
  
     Podrobné informace o vytváření profily zřizování najdete v tématu [vytváření zřizování profilů pomocí Member Center](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingProfiles/MaintainingProfiles.html#//apple_ref/doc/uid/TP40012582-CH30-SW24) v knihovně iOS Developer Library.  
  
-   [Node.js](http://nodejs.org/)  
  
-   Aktualizovanou verzi npm  
  
     Verze npm, která se dodává s Node.js nemusí být dostatečně nová, aby instalace vcremote. Chcete-li aktualizovat npm, otevřete terminálu aplikace na počítači Mac a zadejte následující příkaz:  
  
     `sudo npm install -g npm@latest`  
  
##  <a name="Install"></a>Instalace vzdáleného agenta pro iOS  
 Když instalujete Visual C++ pro vývoj mobilních řešení pro různé platformy, Visual Studio může komunikovat s [vcremote](http://go.microsoft.com/fwlink/p/?LinkId=534988), vzdáleného agenta spuštěného na počítači Mac, k přenosu souborů, sestavit a spustit aplikaci s iOS a odesílání příkazů ladění.  
  
 Než nainstalujete vzdáleného agenta, ujistěte se, jste splnili [požadavky](#Prerequisites) a nainstalován [Visual C++ pro vývoj mobilních řešení pro různé platformy](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md#InstallTheTools).  
  
###  <a name="DownloadInstall"></a>Stažení a instalace vzdáleného agenta  
  
-   Z terminálu aplikace na počítači Mac zadejte:  
  
     `sudo npm install -g --unsafe-perm vcremote`  
  
     Globální instalace (**-g**) přepínač je doporučená, ale není potřeba.  
  
     Během instalace vcremote je nainstalován a režim vývojáře je aktivováno na vaše Mac. [Homebrew](http://brew.sh/) a jsou dva balíčky pro npm, vcremote-lib a vcremote utils, nainstalovány také.  
  
    > [!NOTE]
    >  Pokud chcete nainstalovat Homebrew, musí mít sudo (správce) přístup. Pokud potřebujete nainstalovat vcremote bez sudo, můžete ručně nainstalovat Homebrew v umístění usr/místní a přidat jeho složky Bin přejít na cestu k. Další informace najdete v tématu [Homebrew dokumentaci](https://github.com/Homebrew/homebrew/wiki/Installation). Ručně povolit režim vývojáře, zadejte tento příkaz v terminálu aplikaci:`DevToolsSecurity -enable`  
  
 Pokud je aktualizovat na novou verzi sady Visual Studio, musíte aktualizovat na aktuální verzi vzdáleného agenta. Pokud chcete aktualizovat vzdáleného agenta, opakujte kroky ke stažení a instalace vzdáleného agenta.  
  
##  <a name="Start"></a>Spuštění vzdáleného agenta  
 Vzdáleného agenta musí být spuštěn pro sadu Visual Studio k vytvoření a spuštění kódu iOS. Visual Studio musí být spárována s vzdáleného agenta předtím, než může komunikovat. Ve výchozím nastavení vzdáleného agenta spustí v režimu zabezpečené připojení, který vyžaduje PIN kódu spárujte pomocí sady Visual Studio.  
  
###  <a name="RemoteAgentStartServer"></a>Spuštění vzdáleného agenta  
  
-   Z terminálu aplikace na počítači Mac zadejte:  
  
     `vcremote`  
  
     Výchozí adresář sestavení to začíná vzdáleného agenta ~ / vcremote. Další možnosti konfigurace, najdete v části [konfigurace vzdáleného agenta na Mac](#ConfigureMac).  
  
 Při prvním spuštění agenta a kdykoli vytvořit nový klientský certifikát, jsou k dispozici požadované informace ke konfiguraci agenta v sadě Visual Studio, včetně názvu hostitele, port a kódu PIN.  
  
 ![Můžete vygenerovat zabezpečeného PIN kódu pomocí vcremote](../cross-platform/media/cppmdd_vcremote_generateclientcert.png "CPPMDD_vcremote_generateClientCert")  
  
 Pokud máte v úmyslu konfigurovat vzdáleného agenta v sadě Visual Studio pomocí názvu hostitele, zadejte příkaz ping Mac ze systému Windows pomocí názvu hostitele k ověření, zda je dostupná. Potřebujete, jinak hodnota místo toho použít IP adresu.  
  
 Vygenerovaný PIN kód je pro jedno použití čas a je platná pouze po omezenou dobu. Pokud není spárujte Visual Studio se vzdáleným agentem před vypršením doby, musíte vygenerovat nový kód PIN. Další informace najdete v tématu [generování nového zabezpečení PIN kódu](#GeneratePIN).  
  
 Můžete vytvořit vzdáleného agenta v nezabezpečeném režimu. V nezabezpečeném režimu se dají párovat vzdáleného agenta pro Visual Studio bez kódu PIN.  
  
#### <a name="to-disable-secured-connection-mode"></a>Chcete-li zakázat režim zabezpečené připojení  
  
-   Zakázat režim zabezpečené připojení v vcremote, zadejte tento příkaz v terminálu aplikace na počítači Mac:  
  
     `vcremote --secure false`  
  
#### <a name="to-enable-secured-connection-mode"></a>Pokud chcete povolit režim zabezpečené připojení  
  
-   Pokud chcete povolit režim zabezpečené připojení, zadejte tento příkaz:  
  
     `vcremote --secure true`  
  
 Jakmile jste spustili vzdáleného agenta, můžete použít ze sady Visual Studio dokud jej nezastavíte.  
  
#### <a name="to-stop-the-remote-agent"></a>Chcete-li zastavit vzdáleného agenta  
  
-   V terminálu okno vcremote běží v, zadejte `Control+C`.  
  
##  <a name="ConfigureVS"></a>Konfigurace vzdáleného agenta v sadě Visual Studio  
 Chcete-li připojit k vzdáleného agenta ze sady Visual Studio, musíte zadat konfigurace vzdáleného v možnostech nástroje Visual Studio.  
  
#### <a name="to-configure-the-remote-agent-from-visual-studio"></a>Konfigurace vzdáleného agenta ze sady Visual Studio  
  
1.  Pokud ještě není spuštěn agent na počítači Mac, postupujte podle kroků v [spuštění vzdáleného agenta](#Start). Počítače Mac musí být spuštěna vcremote pro sadu Visual Studio úspěšně spárujte, připojit a sestavení projektu.  
  
2.  V počítači Mac se získáte název hostitele nebo IP adresa vašeho Mac.  
  
     Můžete získat IP adresu pomocí **ifconfig** příkazu v okně terminálu. Použijte adresu inet uvedené v části active síťové rozhraní.  
  
3.  Na panelu nabídek Visual Studio zvolte **nástroje**, **možnosti**.  
  
4.  V **možnosti** dialogové okno, rozbalte seznam **křížové platformy**, **C++**, **iOS**.  
  
5.  V **název hostitele** a **Port** pole, zadejte hodnoty zadané ve vzdáleného agenta při jeho spuštění. Název hostitele může být název DNS nebo IP adresa vašeho Mac. Výchozí port je 3030.  
  
    > [!NOTE]
    >  Pokud nelze odeslat příkaz ping Mac pomocí názvu hostitele, musíte použít IP adresu.  
  
6.  Pokud používáte vzdáleného agenta ve výchozím režimu zabezpečené připojení, zkontrolujte **zabezpečeného** zaškrtávací políčko, pak zadejte PIN kód hodnotu zadanou pomocí vzdáleného agenta v **Pin** pole. Pokud používáte v režimu nezabezpečené připojení vzdáleného agenta, zrušte **zabezpečeného** zaškrtávací políčko a nechat **Pin** prázdné pole.  
  
7.  Zvolte **pár** povolit párování.  
  
     ![Nakonfigurujte připojení vcremote pro iOS sestavení](../cross-platform/media/cppmdd_options_ios.PNG "CPPMDD_Options_iOS")  
  
     Párování trvá, dokud nezměníte název hostitele nebo portu. Pokud změníte název hostitele nebo v portu **možnosti** dialogové okno, chcete-li vrátit změnu, vyberte **vrátit** tlačítko se vrátit k předchozí párování.  
  
     Pokud spárování úspěšné není, ověřte, zda vzdáleného agenta podle kroků v [spuštění vzdáleného agenta](#Start). Pokud příliš mnoho času uplynutí od vygenerování vzdáleného agenta kódu PIN, postupujte podle kroků v [vygenerovat nový kód PIN zabezpečení](#GeneratePIN) na Mac a akci opakujte. Pokud používáte název hostitele počítače Mac, zkuste použít IP adresu v **název hostitele** místo toho.  
  
8.  Aktualizovat název složky v **vzdáleného kořenové** pole zadat složku, používá vzdáleného agenta ve vašem adresáři home (~) na Mac. Ve výchozím nastavení používá vzdáleného agenta /Users/`username`/vcremote jako vzdálené kořen.  
  
9. Zvolte **OK** se uložit nastavení připojení vzdálené párovací.  
  
 Visual Studio použije stejné informace pro připojení k vzdáleného agenta na počítači Mac pokaždé, když ji používáte. Není nutné pár Visual Studio se vzdáleným agentem znovu vygenerovat nový certifikát zabezpečení na počítači Mac, resp. její název hostitele nebo IP adresa změny.  
  
##  <a name="GeneratePIN"></a>Vygenerování nového zabezpečení PIN kódu  
 Při prvním spuštění vzdáleného agenta vygenerovaný PIN kód je platný po omezenou dobu – ve výchozím nastavení 10 minut. Pokud nemáte spárujte Visual Studio se vzdáleným agentem, před vypršením doby, musíte vygenerovat nový kód PIN.  
  
#### <a name="to-generate-a-new-pin"></a>Chcete-li vygenerovat nový kód PIN  
  
1.  Zastavte agenta, nebo otevřete druhé okno terminálu aplikace na počítači Mac a použít k zadání příkazu.  
  
2.  Zadejte tento příkaz v terminálu aplikaci:  
  
     `vcremote generateClientCert`  
  
     Vzdáleného agenta generuje nový dočasný PIN kód. Visual Studio spárovat s použitím nový kód PIN, opakujte kroky v [konfigurace vzdáleného agenta v sadě Visual Studio](#ConfigureVS).  
  
##  <a name="GenerateCert"></a>Vygenerovat nový certifikát serveru  
 Z bezpečnostních důvodů certifikáty serveru tuto dvojici Visual Studio se vzdáleným agentem, jsou svázané s IP adresu nebo název hostitele vašeho Mac. Pokud tyto hodnoty změnit, musíte vygenerovat nový certifikát serveru a potom znovu nakonfigurovat Visual Studio s novými hodnotami.  
  
#### <a name="to-generate-a-new-server-certificate"></a>Pro vytvoření nového certifikátu serveru  
  
1.  Zastavte agenta vcremote.  
  
2.  Zadejte tento příkaz v terminálu aplikaci:  
  
     `vcremote resetServerCert`  
  
3.  Po zobrazení výzvy k potvrzení, zadejte `Y`.  
  
4.  Zadejte tento příkaz v terminálu aplikaci:  
  
     `vcremote generateClientCert`  
  
     Tím se vygeneruje nový dočasný PIN kód.  
  
5.  Visual Studio spárovat s použitím nový kód PIN, opakujte kroky v [konfigurace vzdáleného agenta v sadě Visual Studio](#ConfigureVS).  
  
##  <a name="ConfigureMac"></a>Konfigurace vzdáleného agenta na Mac  
 Můžete nakonfigurovat vzdáleného agenta použití různých možností příkazového řádku. Můžete například zadat port pro naslouchání požadavkům na sestavení a určete maximální počet sestavení pro zachování v systému souborů. Výchozí limit je 10 sestavení. Vzdáleného agenta dojde k odebrání sestavení, které překračují maximální na vypnutí.  
  
#### <a name="to-configure-the-remote-agent"></a>Konfigurace vzdáleného agenta  
  
-   Pokud chcete zobrazit úplný seznam příkazů vzdáleného agenta v terminálu aplikaci, zadejte:  
  
     `vcremote --help`  
  
-   Zabezpečený režim zakázání a povolení jednoduchého připojení na základě protokolu HTTP, zadejte:  
  
     `vcremote --secure false`  
  
     Pokud použijete tuto možnost, zrušte **zabezpečeného** zaškrtávací políčko a nechte **Pin** prázdné pole při konfiguraci agenta v sadě Visual Studio.  
  
-   Pokud chcete zadat umístění pro soubory vzdáleného agenta, zadejte:  
  
     `vcremote --serverDir directory_path`  
  
     kde *directory_path* je umístění na počítači Mac k umístění souborů protokolu, sestavení a certifikáty serveru. Ve výchozím nastavení, toto umístění je /Users/*uživatelské jméno*/vcremote. Sestavení jsou uspořádané podle číslo sestavení v tomto umístění.  
  
-   Můžete k zaznamenávání používat proces na pozadí `stdout` a `stderr` do souboru s názvem server.log, zadejte:  
  
     `vcremote > server.log 2>&1 &`  
  
     Soubor server.log může pomoci při řešení potíží s sestavení.  
  
-   Chcete-li spustit agenta pomocí konfiguračního souboru, místo abyste parametry příkazového řádku, zadejte:  
  
     `vcremote --config config_file_path`  
  
     kde *config_file_path* je cesta k souboru konfigurace ve formátu JSON. Možnosti spuštění a jejich hodnoty nesmí obsahovat pomlčky.  
  
## <a name="see-also"></a>Viz také  
 [Instalace komponenty Visual C++ for Cross-Platform Mobile Development](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)