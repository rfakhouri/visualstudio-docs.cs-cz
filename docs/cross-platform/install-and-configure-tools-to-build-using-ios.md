---
title: Instalace a konfigurace nástrojů pro vytváření pomocí iOS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 05/13/2019
ms.technology: vs-ide-mobile
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0c311c9-9eb9-42c5-ba07-25604362cd28
author: corob-msft
ms.author: corob
manager: jillfra
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 411ab7f097a82fa850e3850c662d378f51ffd548
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2019
ms.locfileid: "67586820"
---
# <a name="install-and-configure-tools-to-build-using-ios"></a>Instalace a konfigurace nástroje potřebné k vytváření pomocí iOS

Visual C++ pro vývoj mobilních řešení napříč platformami můžete použít pro úpravy, ladění a nasazení iOS kódu do simulátoru iOS nebo zařízení s Iosem, ale z důvodu licenčních omezení, kód musí být vytvořená a vzdálené spouštění v počítačích Mac. Pokud chcete sestavovat a spouštět aplikace pro iOS pomocí sady Visual Studio, budete muset nastavit a nakonfigurovat vzdálený agent [vcremote](https://go.microsoft.com/fwlink/p/?LinkId=534988), na vašem počítači Mac. Vzdálený agent obslužné rutiny žádosti o sestavení ze sady Visual Studio aplikace a spustí se na zařízení s iOS připojené k počítači Mac, nebo simulátor iOS na macu

> [!NOTE]
> Informace o používání služeb hostovaných v cloudu Mac místo Mac najdete v tématu [konfigurace sady Visual Studio pro připojení k vašemu cloudu hostovaná Mac](/visualstudio/cross-platform/tools-for-cordova/tips-workarounds/host-a-mac-in-the-cloud?view=toolsforcordova-2017#configure-visual-studio-to-connect-to-your-cloud-hosted-mac). Pokyny jsou určené pro sestavení pomocí nástrojů Visual Studio pro Apache Cordova. Chcete-li postupujte podle pokynů pro sestavení pomocí jazyka C++, nahraďte vcremote pro remotebuild.

Jakmile nainstalujete nástroje pro vytváření pomocí iOS, přečtěte si toto téma způsoby, jak rychle nakonfigurovat a aktualizovat vzdálený agent pro vývoj pro iOS v sadě Visual Studio a na vašem počítači Mac.

## <a name="prerequisites"></a>Požadavky

Chcete-li nainstalovat a používat vzdálený agent pro vývoj kódu pro iOS, musíte nejprve mít tyto požadavky:

- Počítač Mac s macOS verze Mojave 10.14 nebo novější

- [Apple ID](https://appleid.apple.com/)

- Aktivní [Apple Developer Program](https://developer.apple.com/programs/) účtu

   Můžete získat bezplatný účet, který umožňuje zkušební načtení aplikací pro zařízení s Iosem pro testování pouze, ale nikoli pro distribuci.

- [Xcode](https://developer.apple.com/xcode/downloads/) verze 10.2.1 nebo novější

   Xcode můžete stáhnout z App Store.

- Nástroje příkazového řádku Xcode

   Instalace nástrojů příkazového řádku Xcode, otevřete aplikaci terminál na počítači Mac a zadejte následující příkaz:

   `xcode-select --install`

- Účet Apple ID nakonfigurované v prostředí Xcode jako podpisové identity k podepisování aplikací

   Chcete-li zobrazit nebo nastavit podpisové identity v Xcode, otevřete **Xcode** nabídku a zvolte **Předvolby**. Vyberte **účty** a vyberte svoje Apple ID a klikněte na tlačítko **zobrazit podrobnosti o** tlačítko. Zobrazit [přidal váš účet Apple ID, které](https://help.apple.com/xcode/mac/current/#/devaf282080a) podrobné pokyny.
   
   Podrobné informace o podepisování požadavky najdete v tématu [co je podepisování aplikací](https://help.apple.com/xcode/mac/current/#/dev3a05256b8). 

- Pokud používáte zařízení s Iosem pro vývoj, že obsahují zřizovací profil nakonfigurovaný v Xcode pro vaše zařízení

   Xcode poskytuje automatické podepisování, kde ji můžete podle potřeby vytvoří podpisové certifikáty. Podrobné informace o automatické podepisování Xcode naleznete v tématu [automatické podepisování](https://help.apple.com/xcode/mac/current/#/dev80cc24546).

   Pokud chcete provést ruční podepisování, musíte vytvořit zřizovací profil pro vaši aplikaci. Podrobné informace o vytváření zřizovací profily, najdete v části [vytváření vývojových zřizovací profil](https://help.apple.com/developer-account/#/devf2eb157f8). 

- [Node.js](https://nodejs.org/) verze 8.11.3 a npm verze 5.6.0

   Nainstalovat verzi 8.11.3 Node.js na vašem počítači Mac. Pokud nainstalujete balíček Node.js, by měl mít npm verze 5.6.0. Všimněte si, že ostatní verze Node.js a npm nemusí podporovat některé moduly používané v vcremote vzdáleného agenta, což může způsobit selhání instalace vcremote.

## <a name="Install"></a> Instalace vzdáleného agenta pro iOS

Při instalaci Visual C++ pro vývoj Multiplatformních mobilních řešení pro Visual Studio může komunikovat s [vcremote](https://go.microsoft.com/fwlink/p/?LinkId=534988), vzdáleného agenta spuštěného na počítači Mac, přenos souborů, sestavte a spusťte aplikaci pro iOS a odeslat příkazy ladění.

Před instalací vzdáleného agenta, ujistěte se, že jste splnili [požadavky](#prerequisites) a nainstalované [Visual C++ pro vývoj mobilních řešení napříč platformami](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md#install-the-tools).

### <a name="DownloadInstall"></a> Stažení a instalace vzdáleného agenta

- Z terminálu aplikace na počítači Mac zadejte:

   `sudo npm install -g --unsafe-perm vcremote`

   Globální instalace ( **-g**) přepínač se doporučuje, ale nevyžaduje.

   Během instalace vcremote je nainstalovaná a je aktivován režim pro vývojáře na vašem počítači Mac. [Homebrew](https://brew.sh/) a nainstaluje se také dva balíčky npm, vcremote lib a vcremote-utils. Po dokončení instalace je bezpečné ignorovat upozornění o přeskočené volitelné závislosti.

   > [!NOTE]
   > K instalaci Homebrew, musí mít přístup sudo (správce). Pokud je potřeba nainstalovat vcremote bez sudo, můžete ručně nainstalujte Homebrew v umístění usr/local a jeho složku bin přidat do cesty. Další informace najdete v tématu [Homebrew dokumentaci](https://github.com/Homebrew/homebrew/wiki/Installation). Vývojářský režim povolit ručně, v aplikaci terminál zadejte tento příkaz: `DevToolsSecurity -enable`

Pokud aktualizujete na novou verzi sady Visual Studio, je třeba aktualizovat na aktuální verzi vzdáleného agenta. Aktualizace vzdáleného agenta, opakujte postup stažení a instalace vzdáleného agenta.

## <a name="Start"></a> Spuštění vzdáleného agenta

Vzdálený agent musí být spuštěná sada Visual Studio sestavte a spusťte váš kód s Iosem. Visual Studio musí být párována s vzdáleného agenta předtím, než může komunikovat. Ve výchozím nastavení se vzdálený agent spouští v režimu zabezpečené připojení, která vyžaduje kód PIN spárovat se sadou Visual Studio.

### <a name="RemoteAgentStartServer"></a> Spuštění vzdáleného agenta

- Z terminálu aplikace na počítači Mac zadejte:

   `vcremote`

   Spustí se vzdálený agent s výchozí adresář sestavení z ~ / vcremote. Další možnosti konfigurace, najdete v části [konfigurace vzdáleného agenta na počítači Mac](#ConfigureMac).

Při prvním spuštění agenta a kdykoli vytvořit nový klientský certifikát, jsou k dispozici požadované informace pro konfiguraci agenta v sadě Visual Studio, včetně názvu hostitele, port a kód PIN.

![Ke generování zabezpečeného PIN kódu použít vcremote](../cross-platform/media/cppmdd_vcremote_generateclientcert.png "CPPMDD_vcremote_generateClientCert")

Pokud máte v úmyslu konfigurace vzdáleného agenta v sadě Visual Studio pomocí názvu hostitele, odešlete zprávu ping Mac z Windows pomocí názvu hostitele k ověření, že je dostupný. V opačném případě budete muset místo toho použijte IP adresu.

Vygenerovaný PIN kód je pro jeden čas použití a je platná pouze po omezenou dobu. Pokud aplikace Visual Studio není spárovat se vzdáleným agentem před vypršení časového limitu, je potřeba vygenerovat nový kód PIN. Další informace najdete v tématu [vygenerovat nový bezpečnostní kód PIN](#GeneratePIN).

Vzdálený agent můžete použít v nezabezpečeném režimu. V nezabezpečeném režimu se dají párovat vzdáleného agenta se sadou Visual Studio bez kódu PIN.

#### <a name="to-disable-secured-connection-mode"></a>Chcete-li zakázat režim zabezpečené připojení

- Chcete-li zakázat režim zabezpečených připojení v vcremote, zadejte tento příkaz v aplikaci terminál na počítači Mac:

   `vcremote --secure false`

#### <a name="to-enable-secured-connection-mode"></a>Pokud chcete povolit režim zabezpečené připojení

- Pokud chcete povolit režim zabezpečené připojení, zadejte tento příkaz:

   `vcremote --secure true`

Po zahájení vzdáleného agenta můžete použít v sadě Visual Studio až po ukončení.

#### <a name="to-stop-the-remote-agent"></a>Chcete-li zastavit vzdáleného agenta

- V okně terminálu vcremote běží v, zadejte **ovládací prvek**+**C**.

## <a name="ConfigureVS"></a> Konfigurace vzdáleného agenta v sadě Visual Studio

Pro připojení ke vzdálenému agentu ze sady Visual Studio, musíte zadat konfigurace vzdáleného v možnostech sady Visual Studio.

### <a name="to-configure-the-remote-agent-from-visual-studio"></a>Konfigurace vzdáleného agenta ze sady Visual Studio

1. Jestliže dosud není spuštěn agent na počítači Mac, postupujte podle kroků v [spustit vzdálený agent](#Start). Počítače Mac musí být spuštěná vcremote pro Visual Studio úspěšně spárovat, připojit a sestavte projekt.

1. Na počítači Mac získáte název hostitele nebo IP adresu vašeho macu.

   Můžete získat IP adresu pomocí **ifconfig** příkazu v okně terminálu. Použijte adresu inet uvedené v části active síťové rozhraní.

1. Na řádku nabídek sady Visual Studio, zvolte **nástroje**, **možnosti**.

1. V **možnosti** dialogového okna rozbalte **různé platformy**, **C++** , **iOS**.

1. V **název hostitele** a **Port** pole, zadejte hodnoty určené vzdáleného agenta při jeho spuštění. Název hostitele může být název DNS nebo IP adresu vašeho macu. Výchozí port je 3030.

   > [!NOTE]
   > Pokud je příkazem ping otestovat Mac pomocí názvu hostitele, budete muset použít IP adresu.

1. Pokud používáte vzdálený agent ve výchozím režimu zabezpečené připojení, zkontrolujte **Secure** zaškrtávací políčko, zadejte PIN kód hodnotu zadanou pomocí vzdáleného agenta v **Pin** pole. Pokud používáte vzdálený agent v režimu nezabezpečená připojení, zrušte zaškrtnutí políčka **Secure** zaškrtávací políčko a nechat **Pin** prázdné pole.

1. Zvolte **pár** povolit párování.

   ![Konfigurace připojení vcremote pro sestavení iOS](../cross-platform/media/cppmdd_options_ios.PNG "CPPMDD_Options_iOS")

   Párování se opakuje dokud nezměníte název hostitele nebo portu. Pokud změníte název hostitele nebo port v **možnosti** dialogové okno, vrátit zpět změny, zvolte **vrácení** tlačítka se vrátit k předchozí párování.

   Pokud spárování úspěšné není, ověřte, že vzdálený agent běží, pomocí kroků v [spustit vzdálený agent](#Start). Pokud příliš mnoho času uplynulo od vzdáleného agenta PIN kód se vygeneroval, postupujte podle kroků v [vygenerovat nový bezpečnostní kód PIN](#GeneratePIN) na Macu a zkuste to znovu. Pokud použijete název hostitele počítače Mac, zkuste použít IP adresu v **název hostitele** místo toho.

1. Aktualizovat název složky v **vzdálený kořen** pole zadat složku, která používají vzdálený agent doma ( *~* ) adresáře na počítači Mac. Ve výchozím nastavení vzdálený agent používá /Users/`username`/vcremote jako vzdálený kořen.

1. Zvolte **OK** se uložit nastavení vzdáleného připojení párování.

Visual Studio používá stejné informace pro připojení k vzdáleného agenta na počítači Mac pokaždé, když ho používáte. Nepotřebujete spárovat sady Visual Studio se vzdáleným agentem znovu není-li vygenerovat nový certifikát zabezpečení na počítači Mac, nebo jeho název hostitele nebo IP adresu změny.

## <a name="GeneratePIN"></a> Vygenerovat nový bezpečnostní kód PIN

Při prvním spuštění vzdáleného agenta vygenerovaný PIN kód je platný po omezenou dobu – ve výchozím nastavení, 10 minut. Pokud před vypršení časového limitu, nepárují sady Visual Studio se vzdáleným agentem, je potřeba vygenerovat nový kód PIN.

### <a name="to-generate-a-new-pin"></a>Chcete-li vygenerovat nový kód PIN

1. Zastavte agenta, nebo otevřete druhou okna aplikace na terminálu na svém počítači Mac a, který slouží k zadání příkazu.

1. V aplikaci terminál, zadejte tento příkaz:

   `vcremote generateClientCert`

   Vzdálený agent vygeneruje nový dočasný PIN kód. Visual Studio spárovat s použitím nového kódu PIN, opakujte kroky v [konfigurace vzdáleného agenta v sadě Visual Studio](#ConfigureVS).

## <a name="GenerateCert"></a> Vytvoření nového certifikátu serveru

Z bezpečnostních důvodů certifikáty serveru tento pár Visual Studio se vzdáleným agentem jsou svázány se IP adresa nebo název hostitele vašeho macu. Pokud tyto hodnoty změnit, musíte vygenerovat nový certifikát serveru a potom znovu nakonfigurovat sady Visual Studio s novými hodnotami.

### <a name="to-generate-a-new-server-certificate"></a>Pro vytvoření nového certifikátu serveru

1. Zastavte agenta vcremote.

1. V aplikaci terminál, zadejte tento příkaz:

   `vcremote resetServerCert`

1. Po zobrazení výzvy k potvrzení, zadejte `Y`.

1. V aplikaci terminál, zadejte tento příkaz:

   `vcremote generateClientCert`

   Tím se vygeneruje nový dočasný PIN kód.

1. Visual Studio spárovat s použitím nového kódu PIN, opakujte kroky v [konfigurace vzdáleného agenta v sadě Visual Studio](#ConfigureVS).

## <a name="ConfigureMac"></a> Konfigurace vzdáleného agenta na počítači Mac

Můžete nakonfigurovat pomocí různých možností příkazového řádku vzdáleného agenta. Můžete například zadat port pro naslouchání požadavkům na sestavení a zadejte maximální počet buildů udržovat v systému souborů. Výchozí limit je 10 buildů. Vzdálený agent odebere sestavení, které překračují maximální na vypnutí.

### <a name="to-configure-the-remote-agent"></a>Konfigurace vzdáleného agenta

- Pokud chcete zobrazit úplný seznam příkazů vzdáleného agenta, v terminálu aplikaci, zadejte:

   `vcremote --help`

- Zabezpečený režim zakázání a povolení jednoduché připojení na základě protokolu HTTP, zadejte:

   `vcremote --secure false`

   Když použijete tuto možnost, zrušte **Secure** zaškrtávací políčko a nechat **Pin** prázdné pole při konfiguraci agenta v sadě Visual Studio.

- Chcete-li zadat umístění pro soubory vzdáleného agenta, zadejte:

   `vcremote --serverDir directory_path`

   kde *directory_path* je umístění na počítači Mac chcete umístit soubory protokolů, sestavení a certifikáty serveru. Ve výchozím nastavení, je toto umístění */Users/\<uživatelské jméno > / vcremote*. Sestavení jsou uspořádané podle čísla sestavení v tomto umístění.

- Použití proces na pozadí k zachycení `stdout` a `stderr` do souboru s názvem server.log, zadejte:

   `vcremote > server.log 2>&1 &`

   Soubor server.log může být užitečné při řešení potíží s problémy se sestavením.

- Chcete-li spustit agenta pomocí konfiguračního souboru namísto parametrů příkazového řádku, zadejte:

   `vcremote --config config_file_path`

   kde *config_file_path* je cesta ke konfiguračnímu souboru ve formátu JSON. Možnosti spuštění a jejich hodnoty nesmí obsahovat pomlčky.

## <a name="troubleshoot-the-remote-agent"></a>Řešení potíží s vzdáleného agenta

### <a name="debugging-on-an-ios-device"></a>Ladění na zařízení s iOS

Pokud nefunguje ladění na zařízení s Iosem, může být problémy s nástrojem [ideviceinstaller](https://github.com/libimobiledevice/ideviceinstaller), který se používá ke komunikaci se zařízením s Iosem. Tento nástroj je obvykle nainstalován z Homebrew během instalace vcremote. Jako alternativní řešení proveďte následující postup.

Otevřete aplikaci terminál a aktualizujte ideviceinstaller a jeho závislosti spuštěním následujícího v pořadí:

1. Ujistěte se, že se aktualizuje Homebrew

   `brew update`

1. Odinstalujte libimobiledevice a usbmuxd

   `brew uninstall --ignore-dependencies libimobiledevice`

   `brew uninstall --ignore-dependencies usbmuxd`

1. Nainstalujte nejnovější verzi libimobiledevice a usbmuxd

   `brew install --HEAD usbmuxd`

   `brew unlink usbmuxd`

   `brew link usbmuxd`

   `brew install --HEAD libimobiledevice`

1. Odinstalujte a znovu nainstalujte ideviceinstaller

   `brew uninstall ideviceinstaller`

   `brew install ideviceinstaller`

Ověřte, zda že tento ideviceinstaller může komunikovat s zařízení tak, že zkusíte seznam aplikací na zařízení nainstalovaný:

`ideviceinstaller -l`

Pokud ideviceinstaller chyby, nemá přístup ke složce `/var/db/lockdown`, změnit oprávnění pro složku s:

`sudo chmod 777 /var/db/lockdown`
    
Zkontrolujte znovu Pokud ideviceinstaller může komunikovat se zařízením.

## <a name="see-also"></a>Viz také:

- [Instalovat Visual C++ pro vývoj mobilních řešení napříč platformami](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)
