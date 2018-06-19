---
title: Spravovat testovací kontroléry a testovací agenti v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59c676424dbba0cea17670df5a99ac0f9dbbfb5f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31979305"
---
# <a name="manage-test-controllers-and-test-agents"></a>Spravovat testovací kontroléry a testovací agenti

Pokud chcete spustit testy vzdáleně, distribuce testů mezi více počítačů pomocí sady Visual Studio nebo spouštění zátěžových testů, je nutné nakonfigurovat testovací kontroler, testovací agenti a testovací soubor s nastaveními. Toto téma popisuje, jak spravovat testovací kontroléry a testovací agenti po nainstalovat a nakonfigurovat je pro první.

Pokud používáte Microsoft Test Manager ke spuštění testů v testovacích prostředích, můžete spravovat testovacích kontrolérů a jejich agentů pomocí **Test Manager řadič** v **testovacím Center** pro Microsoft Test Manager. Toto téma se vztahuje pouze pokud používáte Visual Studio ke spuštění testů.

Informace o tom, jak nainstalovat a nakonfigurovat testovacích agentů a testovací kontrolery ke spuštění testů v sadě Visual Studio najdete v tématu [konfigurace testovacích agentů a řadičů](../test/configure-test-agents-and-controllers-for-load-tests.md).

Konfigurovat a monitorovat testovací kontroler a všechny registrované agentů, musí mít souborů nastavení testů ve vašem projektu test, který obsahuje ty testy, které chcete spustit. Otevřete soubor s nastavením testu, zvolte **Role** a zvolte **Správa testování řadičů** z rozevíracího seznamu pro **řadič** pole.

Pro projekt test zatížení, můžete také zvolit **Správa testování řadičů** z **načíst testování** nabídky.

## <a name="add-a-test-agent-to-a-test-controller"></a>Přidat agenta testů pro testovací kontroler

Můžete chtít přidat agenta test do jiného testovacího řadiče nebo možná budete muset přidat agenta testů pro testovací kontroler, který jste právě nainstalovali.

### <a name="to-add-a-test-agent-to-a-test-controller"></a>Chcete-li přidat agentem test agent pro testovací kontroler

1. Zvolte **spustit** > **testování nástroje Konfigurace agenta**.

     **Konfigurace agenta Test** se zobrazí dialogové okno.

    > [!NOTE]
    > Musí být test agent již nainstalován tím ho přidáte do testovací kontroler. Další informace o tom, jak nainstalovat agenta test najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

2. Pokud chcete změnit způsob, který se spouští agentem test agent, zvolte **spustit možnosti**.

     Jsou nabízí dvě možnosti, jak se bude agentem test agent ke spuštění:

     **Služba** Pokud nemáte spuštění automatizovaných testů komunikujících s plochou, například programových testů UI nebo vytvoření záznamu, když vaše testovací běhy, v části videa **spusťte agenta test jako**, vyberte **služby**. Testovací agent bude spuštěn jako služba. Zvolte **Další**.

     Teď můžete zadat podrobnosti o uživateli při agentem test agent spuštění jako služba.

    1. Zadejte název v **uživatelské jméno**.

    2. Zadejte heslo do **heslo**.

        |**Informace o důležitých uživatelském účtu**|
        |--------------------------------------------|
        |-Null hesla nejsou podporovány pro uživatelské účty.|
        |– Pokud chcete použít kolekce IntelliTrace nebo emulace sítě, uživatelský účet musí být členem skupiny Administrators.|
        |– Pokud je agent uživatelské jméno není ve službě agenta se pokusí přidat, který vyžaduje oprávnění k testovacímu kontroleru.|
        |-Uživatel, který se pokouší použít testovací kontroler musí být v účtu uživatele testovací řadiče nebo bude moci spouštět testy řadičem.|

     **Interaktivní proces** Pokud budete chtít spuštění automatizovaných testů, které musí komunikovat s plochou, jako například programových testů UI nebo vytvoření záznamu, když vaše testovací běhy videa, vyberte **interaktivní proces**. Testovací agent bude spuštěn jako interaktivní proces místo služby.

     Na další stránce zadejte podrobnosti o uživateli při spuštění agenta test jako proces a další možnosti.

    1. Zadejte název v **uživatelské jméno**.

    2. Zadejte heslo do **heslo**.

        > [!NOTE]
        > Pokud nakonfigurujete testovacího agenta spustit jako interaktivní proces s jiným uživatelem, který není aktuálně aktivního uživatele, je třeba restartovat počítač a přihlaste se jako tento jiný uživatel mohl spustit agenta. Kromě toho null hesla nejsou podporovány pro uživatelské účty. Pokud chcete použít kolekce IntelliTrace nebo emulace sítě, uživatelský účet musí být členem skupiny Administrators.

        |**Informace o důležitých uživatelském účtu**|
        |--------------------------------------------|
        |-Null hesla nejsou podporovány pro uživatelské účty.|
        |– Pokud chcete použít nástroje IntelliTrace nebo data emulace sítě a adaptéru diagnostických, uživatelský účet musí být členem skupiny Administrators. Pokud je počítač, který je spuštěn agent testovací má operační systém, který má nejmenší privilegovaný účet uživatele, musíte také spustit jako správce (se zvýšenými oprávněními).|
        |– Pokud je agent uživatelské jméno není ve službě agenta se pokusí přidat, který vyžaduje oprávnění k testovacímu kontroleru.|
        |-Uživatel, který se pokouší použít testovací kontroler musí být v účtu uživatele testovací řadiče nebo bude moci spouštět testy řadičem.|

    3. Abyste měli jistotu, že do počítače s agentem test agent testy můžete spustit po restartování, můžete nastavit počítač pro automatické přihlášení jako pomocí agenta test. Vyberte **automatické přihlášení**. To bude ukládat uživatelské jméno a heslo v šifrovaném formátu v registru.

    4. Chcete-li mít jistotu, že šetřič obrazovky je zakázána, protože to může narušovat žádné automatizovaných testů, které musí komunikovat s plochou, vyberte **šetřič obrazovky zajistěte, aby je zakázána**.

        > [!WARNING]
        > Pokud automatické přihlášení nebo zakážete šetřič obrazovky jsou rizika zabezpečení. Povolením automatické protokolu v, povolíte jiných uživatelů k spuštění tohoto počítače a mohli používat účet, který automaticky přihlásí. Pokud zakážete šetřič obrazovky, počítač nemusí vyzván k přihlášení uživatele k odemknutí počítače. Díky tomu každý, kdo přistupovat k počítači v případě, že mají fyzický přístup k počítači. Pokud povolíte tyto funkce na počítači, měli byste si ověřit, že tyto počítače jsou fyzicky zabezpečené. Tyto počítače jsou například umístěny ve fyzicky zabezpečeném testovacím prostředí. (Pokud zrušíte výběr **šetřič obrazovky zajistěte, aby je zakázána**, nepovolí se spořič.)

3. Chcete-li zaregistrovat tento agent s jinou testovací kontroler, vyberte **zaregistrovat testovací kontroler.** Zadejte název řadiče testovací následuje **:** a číslo portu, který používáte v **registraci agenta test s následující testovací kontroler**. Můžete například zadat **agent1:6901**.

    > [!NOTE]
    > Výchozí číslo portu je 6901.

4. Pokud chcete uložit provedené změny, zvolte **použít nastavení**. Zavřete **souhrnné informace o konfiguraci** dialogové okno a pak ukončete nástroj Test Agent konfigurace.

> [!WARNING]
> Pokud agenta je nyní nakonfigurován, aby se spouští na jiný testovací řadiči, musíte odebrat agenta test z tohoto řadiče.

## <a name="remove-a-test-agent-from-a-test-controller"></a>Odeberte agenta testů z testovacího Kontroléru

Testovací agent musí být nastavena do stavu offline, než může být odebrán.

> [!NOTE]
> Odebrání agentů, které jsou registrovány k řadiči jako součást testovacím prostředí nelze pomocí tohoto postupu. Pokud chcete odebrat tyto agenty z kontroleru, je nutné odebrat prostředí pomocí nástroje Microsoft Test Manager.

### <a name="to-remove-a-test-agent-from-a-test-controller"></a>Odebrání testovacího kontroléru agenta test

1. Pokud testovací kontroler není registrován u týmového projektu, postupujte podle těchto kroků.

    1. Ze sady Visual Studio otevřete soubor nastavení testu pro projekt test, zvolte **Role** a zvolte **Správa testování řadičů** z rozevíracího seznamu pro **řadič** pole.

         **Spravovat Test Controller** se zobrazí dialogové okno.

    2. V **řadič** rozevíracího seznamu, zadejte název počítače, na kterém jste nastavili testovací kontroler. Pokud řadič specifický test spravovaných dříve, můžete vybrat název ze seznamu.

    3. V **agenti** podokně, vyberte název testovacího agenta. Pokud agenta je stále online, zvolte **Offline.** Chcete-li odebrat, zvolte **odebrat**.

        > [!NOTE]
        > Odebrání agentem test agent právě zrušíte z testovacího kontroleru. Chcete-li zcela odinstalovat agenta test, použijte **programy a funkce** ovládací panely v počítači agenta test.

2. Pokud testovací kontroler je registrován s týmového projektu, odeberte agenta pomocí nástroje Microsoft Test Manager.

## <a name="change-the-settings-for-a-test-agent"></a>Změna nastavení pro agenta Test

Stav agenta test může být jakýkoli z následujících hodnot:

|Stav|Popis|
|------------|-----------------|
|Probíhá Test|Spouštění testů|
|Připraven|K dispozici pro spuštění testů nebo shromažďování dat a Diagnostika|
|V režimu offline|Není k dispozici ke spuštění testů nebo shromažďování dat a Diagnostika|
|odpojení|Testovací agent není spuštěna.|

Stav a další nastavení pro agenta test pomocí následujících postupů můžete změnit.

### <a name="to-change-the-settings-of-a-test-agent"></a>Chcete-li změnit nastavení agenta test

> [!NOTE]
> Pokud je test u agenta registrován pro testovací kontroler, která je zaregistrovaná u týmového projektu, změňte nastavení v nástroji Microsoft Test Manager.

1. Konfigurovat a monitorovat testovací kontroler a všechny registrované agentů pro zátěžový test, vyberte **načíst testovací** nabídky v sadě Visual Studio a zvolte **Správa testování řadičů**. Pro všechny testy, otevřete soubor nastavení testu pro projekt test v sadě Visual Studio, zvolte **Role** a zvolte **Správa testování řadičů** z rozevíracího seznamu pro **řadič**pole.

   **Spravovat Test Controller** otevře se dialogové okno.

1. Vyberte název řadiče testovací jejichž testovacích agentů, které chcete změnit v seznamu řadiče testů. Pokud testovací kontroler v seznamu nezobrazí, zkontrolujte, zda je správně zaregistrovány testovací kontroler. Další informace najdete v tématu o tom, jak nakonfigurovat testovací kontroler následující postup.

1. (Volitelné) V **testovací agenty** podokně, vyberte počítač agenta test, pro kterou chcete změnit vlastnosti.

1. Zvolte **vlastnosti**.

1. Následující vlastnosti agenta test podle potřeby změňte:

|Vlastnost agenta test|Popis|
|-------------------------|-----------------|
|**Vyvážení**|Slouží k distribuci zatížení při použití testovacích agentů s úrovně různých výkonu. Například agentem test agent s vyvážení 100 obdrží dvakrát zatížení jako agentem test agent s váhu 50.|
|**Přepínání IP**|Slouží ke konfiguraci přepínání IP. Přepínání IP umožňuje agentem test agent na odesílání žádostí na server pomocí rozsah IP adres. To se simuluje volání, které pocházejí z různých klientských počítačů.<br /><br /> Přepínání IP je důležité, pokud zátěžový test přistupuje k webové farmy. Většina nástrojů pro vyrovnávání zatížení vytvořit přidružení mezi klientem a konkrétní webový server pomocí IP adresy klienta. Pokud všechny požadavky působí, jako jsou pocházejících z jednoho klienta, nebudou nástroje pro vyrovnávání zatížení vyrovnávat zatížení. Chcete-li získat nástroj pro vyrovnávání zatížení dobrý ve webové farmě, ujistěte se, že požadavky pocházejí z rozsahu IP adres. **Poznámka:** můžete určit síťový adaptér, nebo použijte **(všechny nepřiřazené)** automaticky vyberte ten, který není aktuálně používán. <br /><br /> Pokud chcete používat funkci přepínání IP, musí používat službu Visual Studio Test Agent jako uživatel ve skupině Administrators pro tento počítač agenta. Tento uživatel je vybraná při instalaci agenta, ale lze změnit úpravou vlastností služby a jej restartovat.<br /><br /> Pokud chcete ověřit, že přepnutí IP funguje správně, povolit protokolování na webovém serveru služby IIS, pomocí funkce protokolování služby IIS ověřte, jestli požadavky přicházejí z IP adresy, které jste nakonfigurovali.|
|**Atributy**|Sada dvojic název hodnota, které lze použít v testu agenta výběru. Test může například vyžadovat konkrétní operačního systému. Můžete přidat atributů v **role** kartě testované soubor nastavení a lze vybrat agentem test agent, který má odpovídající atributy. Pokud chcete spustit test na více počítačů, vytvořte atribut v roli nastavení testu, který je nakonfigurován na spuštění testů a poté proveďte konfiguraci odpovídající atribut na každý test agent, který chcete použít v dané roli... **Poznámka:** toto nastavení je dostupná jenom pro testovací agenty, které jsou registrovány testovací kontroler, který není zaregistrován na týmový projekt, protože tyto atributy se používají jenom v nastavení testu pro sadu Visual Studio.|

Testovací agent váhy a testovací agent atribut změny projeví okamžitě, ale neovlivní testy, které jsou spuštěné. Rozsah IP adres se projeví po restartování testovací kontroler.

(Volitelné) Chcete-li změnit stav agenta test, vyberte agenta v seznamu a pak vyberte akci z dostupných možností na základě aktuálního stavu agenta.

> [!NOTE]
> Pokud agenta test agent běží jako proces, spravovat stav agenta test z ikonu v oznamovací oblasti, která běží na počítači, kde je nainstalován agenta test agent. To se zobrazuje stav agenta test. Můžete spustit, zastavit nebo restartovat agenta, pokud je spuštěn jako proces pomocí tohoto nástroje. Pokud není spuštěná, spusťte agenta test jako proces, zvolte **spustit**, **všechny programy**, **Microsoft Visual Studio** , **Microsoft Visual Studio Test Agent**. Tím se přidá na ikonu v oznamovací oblasti.

## <a name="configure-a-test-controller"></a>Konfigurace testovací kontroler

Ke konfiguraci testovací kontroler, je nutné použít **Team testování řadiče konfigurační nástroj**. Když konfigurujete řadiči test, můžete zaregistrovat řadiči testovací kolekci jiný týmový projekt nebo zrušit registraci řadiči testu z kolekce týmových projektů.

Pokud chcete zaregistrovat řadiči testovací kolekci projektu Team Foundation Server, účet, který používáte pro službu testovací řadiče musí být členem skupiny kolekci projektu, testování účty služby pro kolekce týmového projektu, nebo účet, který použijete ke spuštění nástroje Konfigurace testu řadiče musí být správcem kolekci projektu.

> [!NOTE]
> Pokud jste se zrušit registraci testovací kontroler z kolekce týmového projektu, který má existující prostředí v kolekci týmových projektů, prostředí jsou stále zachována, pokud jste přesunuli této kolekce týmového projektu a znovu zaregistrujte testovací kontroler tomuto přesunutý týmu kolekci projektu.

### <a name="to-configure-a-test-controller"></a>Ke konfiguraci testovací kontroler

1. Chcete-li spustit nástroj překonfigurovat řadiči testovací kdykoli, zvolte **spustit** > **všechny programy** >  **Microsoft Visual Studio**  >  **Konfigurační nástroj pro sadu Microsoft Visual Studio testování řadiče**.

     **Konfigurace testovacího Kontroléru** se zobrazí dialogové okno.

2. Vyberte uživatele, který má používat jako přihlašovací účet pro služby testovací řadiče.

    > [!NOTE]
    > Null hesla nejsou podporovány pro uživatelské účty.

4. (Volitelné) Pokud nechcete používat řadiči test s testovacím prostředí, ale pouze ke spuštění testů ze sady Visual Studio, zrušte **zaregistrovat u kolekce týmového projektu**.

5. (Volitelné) Při konfiguraci řadiči testu pro zátěžové testování vyberte **konfigurace pro zátěžové testování**. Zadejte instanci serveru SQL v **výsledků zátěžového testu vytvořit databázi v instanci serveru SQL následující**.

> [!NOTE]
> Další řešení potíží informace o testovacích kontrolérů, najdete v části [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

## <a name="manage-your-agents-when-you-run-your-tests-with-a-test-controller"></a>Spravovat agenty při spuštění testů s testovací kontroler

Při přidání role pro vaše aplikace a nastavení testu pro sadu Visual Studio, můžete přidat vlastnosti agenta pro jednotlivé role. Určuje, které testovací agenti jsou k dispozici pro tuto roli. Při spouštění testů pomocí těchto nastavení testů, testovací kontroler, který je vybraná nastavení testu zjišťuje dostupnost požadované agenty. Toto jsou následující situace, které může dojít, když je určen dostupnost agenta:

-   Pro roli, který se musí spustit testy k dispozici není žádný agent. Nelze spustit testy. Můžete provést jednu z následujících akcí a poté znovu spusťte testy:

    -   Počkejte, až agenta k dispozici pro tuto roli spouštět testy.

    -   Pokud jsou všechny agenty, které jsou offline, může být použita pro tuto roli, je restartovat agenta, aby bylo k dispozici.

    -   Jiné agenta s vlastnostmi správné agenta pro tuto roli můžete přidat k testovacímu kontroleru.

    -   Můžete změnit vlastnosti agenta pro tuto roli v nastavení testu pro povolení dalších agentů, které chcete použít.

-   Pro jednu nebo více rolí, které spustit adaptérů diagnostických dat k dispozici není žádný agent. Spuštěním testů, ale adaptér diagnostických dat nelze spustit. Můžete spustit testy bez adaptéru diagnostických dat, nebo můžete provést jednu z následujících akcí a znovu spusťte testy:

    -   Počkejte, až agenta k dispozici pro tyto role.

    -   Pokud jsou všechny agenty, které jsou offline, může být použita pro tuto roli, musíte změnit stav agenta na online z **spravovat Test Controller** na **Test** nabídky. Kromě toho budete muset restartovat agenta, pokud byla odpojena z řadiče.

    -   Ověřte, že všechny agenty, které může být nutné pro tuto testovací běh není zaneprázdněných spouštění testů. Můžete zkontrolovat stav všech agentů z **spravovat Test Controller** na **Test** nabídky.

    -   Jiné agenta s vlastnostmi správné agenta pro roli můžete přidat k testovacímu kontroleru.

    -   Můžete změnit vlastnosti agenta role v nastavení testu pro povolení dalších agentů, které chcete použít.

## <a name="load-tests-from-delay-signed-assemblies"></a>Spouštění testů z zpožděním podepsané sestavení

Testovací kontrolery a testovací agenti můžou načítat jenom testovací sestavení, které jsou důrazně podepsaná sestavení nebo nepodepsaná sestavení. Některé testovací sestavení jsou zpoždění podepsat, protože potřebují k přístupu do provozní sestavení pro aplikaci. Tyto sestavení, nejsou však podepsané důrazně, protože jsou pouze testovací sestavení a nejsou distribuovány. Tyto sestavení nelze načíst, protože jsou podepsané zpoždění, takže je nutné zakázat ověřování silných názvů pro tyto sestavení na všech počítačích, kde bude načten včetně testovacího počítače řadič sestavení. Zakázat ověřování podepsané zpoždění, použijte sn.exe. Token veřejného klíče zpožděním podepsané sestavení, pro kterou se požaduje ověřování silných názvů lze vynechat také potřebovat mají být zahrnuty.

Zakázat ověření zpoždění podepsané pomocí Sn.exe (nástroj pro silný název).

To zakáže ověřování silných názvů, pro zadané sestavení pouze v počítači, na kterém jste spustili příkaz. Lze provést pouze v případě, že máte dostatečná oprávnění.

Po dokončení testu, spusťte znovu povolte ověření odložené podepisování pomocí příkazu SN.exe.

Doporučený způsob, jak zakázat a znovu povolit ověření podpisu je používat příkazy SN.exe ve skriptech. Můžete zakázat ověření v instalační skript a znovu povolit ověření v skript pro vyčištění.

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)