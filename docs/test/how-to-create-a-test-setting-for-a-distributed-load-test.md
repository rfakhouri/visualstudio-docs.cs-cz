---
title: Vytvoření nastavení testu pro distribuovaný zátěžový Test v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, for distributed load tests
ms.assetid: b63d4b71-3b74-4872-b2d1-f0bd1a9a8544
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 29517fcf0f788150db43988fdacf54b3b8b5800c
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751816"
---
# <a name="how-to-create-a-test-setting-for-a-distributed-load-test"></a>Postupy: Vytvoření nastavení testu pro distribuovaný zátěžový test

Konfigurace *nastavení testů* pro vaše zátěžové testy, abyste mohli tyto testy distribuovat do více počítačů pomocí testovacích agentů a testovací kontrolery. Můžete taky nakonfigurovat nastavení testu *adaptérů diagnostických dat*, který zadejte typů dat, který chcete shromáždit, nebo postup ovlivnit testovacích počítačů při spuštění zátěžových testů ze sady Visual Studio.

Například můžete použít adaptér diagnostických dat ASP.NET Profiler ke shromažďování výkonu rozpis kódu. Kromě toho adaptérů diagnostických dat slouží k simulaci potenciální problémová místa na testovacím počítači nebo snižte dostupné systémové paměti.

Nastavení testů pro sadu Visual Studio jsou uloženy v souboru. Test nastavení zadejte následující informace o každé role:

-   Role, které jsou vyžadovány pro aplikaci v testovací sadu

-   Role, kterou chcete použít ke spuštění testů

-   Adaptérů diagnostických dat pro každou roli

Pokud spustíte testy, vyberte nastavení testů pro použití jako aktivního nastavení testování v závislosti na tom, co budete potřebovat pro tento konkrétní test spustit. Soubor s nastavením testu ukládána v rámci vašeho řešení. Název souboru má příponu *.testsettings*.

Když přidáte výkonu webu a zatížení testování projektu a řešení, *Default.testsettings* soubor je vytvořen. Soubor je automaticky přidán do řešení v části **položky řešení** složky. Tento soubor spouští testy místně bez adaptérů diagnostických dat. Můžete přidat další *.testsettings* souboru, nebo upravit *.testsettings* souboru zadejte adaptérů diagnostických dat a testovací kontrolery.

Testovací kontroler bude mít agentů, které lze použít pro každou roli v nastavení testu. Další informace o testovacích kontrolérů a testovacích agentů najdete v tématu [Správa testovací Kontroléry a testovací agenty pomocí sady Visual Studio](../test/manage-test-controllers-and-test-agents.md).

Postupujte podle těchto kroků k vytvoření a odebrat nastavení testu v řešení pro zátěžové testy, které chcete spustit ze sady Visual Studio.

## <a name="create-a-test-setting-for-a-distributed-load-test"></a>Vytvoření nastavení testu pro distribuovaný zátěžový Test

### <a name="to-add-a-test-settings-for-a-distributed-load-test"></a>Chcete-li přidat nastavení testu pro distribuovaný zátěžový test

1.  V Průzkumníku řešení klikněte pravým tlačítkem na **položky řešení**, přejděte na příkaz **přidat**a potom zvolte **novou položku**.

     **Přidat novou položku** zobrazí se dialogové okno.

2.  V **nainstalovaných šablonách** podokně vyberte **nastavení testu**.

3.  (Volitelné) V **název** pole, změňte název souboru s nastavením testu.

4.  Zvolte **přidat**.

     Nový soubor nastavení testů se zobrazí v Průzkumníku řešení klikněte v části **položky řešení** složky.

    > [!NOTE]
    > Seznam nastavení testů, které zobrazí Visual Studio Enterprise je odvozena ze seznamu souborů nastavení testů v **položky řešení** složky. Například testovací nastavení soubory ve složce položky řešení se zobrazují, když použijete **vyberte Active Test nastavení** možnost **testování** nabídky. To znamená, že souborů nastavení testů se přesunout do jiného umístění v hierarchii řešení, je už lze nastavit jako nastavení testu z integrované vývojové prostředí sady Visual Studio.

5.  **Nastavení testu** se zobrazí dialogové okno. **Obecné** je vybrány.

     Nyní můžete upravit a uložit testování nastavení hodnoty.

    > [!NOTE]
    > Každý test nastavení, které vytvoříte je uveden jako volba pro **vyberte Active Test nastavení** a **upravit Test nastavení** možnosti na **testování** nabídky.

6.  V části **název**, zadejte název pro nastavení testu.

7.  (Volitelné) V části **popis**, zadejte popis nastavení testu, ostatní členové týmu vědět, co je určený pro.

8.  (Volitelné) Chcete-li vybrat výchozí schéma pojmenování při testovacím běhu, vyberte **výchozí schéma pojmenování**. Chcete-li definovat vlastní schéma pojmenování, vyberte **uživatelem definované schéma** a pak zadejte text, který chcete v **textu předpony**. Datum a časové razítko připojit k názvu testu, vyberte **razítka data a času připojení**.

9. Zvolte **role**.

     **Role** zobrazí se stránka.

     ![Test nastavení role](../test/media/load_testtestrole.png)

10. Ke spuštění testů vzdáleně, nebo pokud chcete spustit testy vzdáleně a vzdáleně shromažďování dat, použijte **Test provádění metody** rozevíracího seznamu a vyberte možnost **vzdálené spuštění**.

11. Použití **řadič** rozevíracího seznamu vyberte testovací kontroler pro testovací agenty z **řadič** který se použije ke spuštění testů nebo shromažďování dat.

    > [!NOTE]
    > Pokud přidáváte řadič poprvé, objeví se v rozevíracím seznamu žádné řadiče. Naplnění seznamu předchozí řadiče, které jste zadali v jiných nastavení testu. Musíte zadat název kontroleru, do pole (například **TestControllerMachine1**).

12. K přidání rolí, které chcete použít ke spuštění testů a shromažďování dat, v části **role**, zvolte **přidat**.

13. Zadejte název role v **název** sloupce. Role může být například "Web Server".

14. Opakujte kroky 12 a 13 přidat všechny role, které potřebujete.

     Každá role používá agentem test agent, který je spravovaný nástrojem testovací kontroler.

15. Vyberte roli, kterou chcete spustit testy a potom vyberte **nastavit jako roli ke spuštění testů**.

    > [!IMPORTANT]
    > Jiných rolí, které můžete vytvořit a definovat testy se nespustí, ale slouží pouze ke shromažďování dat podle dat a diagnostická adaptéry, které zadáte pro role v **diagnostiky a dat** stránky.

16. Chcete-li omezit agentů, které lze použít pro roli, vyberte roli a poté zvolte **přidat** na panelu nástrojů v části **agenta atributy pro vybraný karta**e.

     **Pravidlo Výběr agenta** se zobrazí dialogové okno.

     Zadejte název v **název atributu** a hodnotou v **hodnota atributu**a potom zvolte **OK**. Přidáte libovolný počet atributů, které potřebujete.

     Můžete například přidat atribut, který je s názvem "RAM > 16GB", má hodnotu "True" nebo "Nepravda" pro filtrování testovací počítače agenta, které mají víc než 16GB paměti. Použít stejný atribut na jeden nebo více testovacích agentů, použijte dialogové okno Spravovat Kontroleru testů. Další informace najdete v tématu [Správa testovacích Kontrolérů a testovacích agentů v sadě Visual Studio](../test/manage-test-controllers-and-test-agents.md).

17. Zvolte **datové a diagnostické**.

     **Datové a diagnostické** zobrazí se stránka.

     ![Test nastavení data a Diagnostika](../test/media/load_testtest.png)

18. V **diagnostiky a dat** stránky, můžete definovat, co roli nemá výběrem *adaptérů diagnostických dat* , roli použijete ke shromažďování dat. Proto pokud jeden nebo více dat a diagnostická adaptéry jsou povolené pro roli, testovací kontroler vyberte dostupné testovací počítač agenta ke shromažďování dat pro zadaná data a adaptérů diagnostických na základě atributů, které jste zadali pro roli. Vyberte data a adaptérů diagnostických dat, které chcete shromažďovat pro každou roli, vyberte roli. Pro každou roli vyberte adaptérů diagnostických dat podle potřeb testů. Chcete-li konfigurovat každý adaptér diagnostických dat, který jste vybrali pro každou roli, zvolte **konfigurace**.

     **Příklad rolí a adaptérů diagnostických dat:**

     Můžete například vytvořit roli klienta, která je s názvem "Desktop klient, který má atribut"Používá SQL"nastavena na"True"a role serveru, která je s názvem"SQL Server", který má atribut nastavena na"16 RAM > GB". Pokud určíte, že klient"plocha" bude spouštět testy výběrem **nastavit jako roli ke spuštění testů** v **role** , testovací kontroler bude vyberte počítače, které mají testovacích agentů, které zahrnují atribut "Používá SQL" nastavit na hodnotu "True", na kterém chcete spustit testy. Testovací kontroler bude také vybrat počítače serveru SQL, které mají testovacích agentů, které zahrnují atribut "RAM > 16GB" pouze ke shromažďování dat, která je definována dat a diagnostická adaptéry, které jsou součástí role. Agent testy "Desktop Client" může taky shromažďovat data pro počítače, na kterých se spustí, pokud vyberete příliš dat a diagnostická adaptéry pro tuto roli.

     Další podrobnosti o každý adaptér diagnostických dat a jeho konfiguraci můžete zobrazit související téma v následující tabulce.

     Další informace o adaptérů diagnostických dat najdete v tématu [shromažďovat diagnostické informace využitím testovacích nastavení](../test/collect-diagnostic-information-using-test-settings.md).

     **Adaptérů diagnostických dat pro zátěžové testy**

    |Adaptér diagnostiky dat|Použití v zátěžových testech|Přidružené tématu|
    |-----------------------------|-------------------------|----------------------|
    |**Proxy server klienta ASP.NET pro IntelliTrace a dopadu testu:** tento proxy server umožňuje shromažďování informací o volání protokolu http od klienta na webový server pro adaptérů diagnostických dat IntelliTrace a dopadu testu.|![Informační ikona, která](../test/media/vc364f4.gif)<br /><br /> Pokud máte konkrétní potřebu shromažďovat informace o systému pro testovací počítače agenta, nezahrnujte tento adaptér. **Upozornění:** nedoporučujeme používání IntelliTrace adaptéru v zátěžových testech z důvodu, ke kterým dochází z důvodu velkého množství dat, které jsou shromážděny. <br /><br /> Testovací dopad data nejsou shromažďovány pomocí zátěžové testy.||
    |**IntelliTrace:** můžete nakonfigurovat konkrétní diagnostické trasování informací, které jsou uloženy v souboru protokolu. Soubor protokolu má rozšíření .tdlog. Když spustíte test a test krok nezdaří, můžete vytvořit chyby. Soubor protokolu, který obsahuje diagnostické trasování se automaticky přiloží k této chyby. Data, která se shromažďují v souboru protokolu zvyšuje produktivitu ladění snížením čas, který je potřeba reprodukujte a diagnostikovat chybu v kódu. Z tohoto protokolu soubor místní relace můžete je znovu vytvořit na jiném počítači. Tím se snižuje riziko, že chyby nelze reprodukovat.<br /><br /> Další informace najdete v tématu [dat shromažďování IntelliTrace](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md).|![Ikona důležité](../test/media/vc364f3.gif)<br /><br /> Nedoporučujeme použití IntelliTrace adaptéru v zátěžových testech z důvodu, ke kterým dochází z důvodu velkého množství dat, který se shromažďuje a přihlášení. Pokuste se použít adaptér IntelliTrace pouze v zátěžových testech, které se nespustí dlouhé a nepoužívejte mnoho testovacích agentů.|[Postupy: shromáždění dat technologie IntelliTrace pro snazší ladění složitých problémů](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)|
    |**ASP.NET Profiler:** můžete vytvořit testovací nastavení, které zahrnuje tvorbě profilace ASP.NET, který shromažďuje údaje o výkonu na webových aplikací ASP.NET.|Adaptér diagnostických dat profileru ASP.NET profily proces Internetové informační služby (IIS), takže nebudou fungovat u webového serveru vývoj. Profilu webové stránky v zátěžovém testu, budete muset nainstalovat testovacího agenta na počítači, který běží služby IIS na. Testovací agent nebude generování zatížení, ale bude pouze agenta kolekce. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).|[Postupy: Konfigurace služby ASP.NET Profiler pro zátěžové testy s využitím testovacích nastavení](../test/how-to-configure-aspnet-profiler-for-load-tests-using-test-settings.md)|
    |**Protokol událostí:** můžete nakonfigurovat testu nastavení zahrnout shromažďování protokolu událostí, který bude součástí výsledků testů.||[Postupy: Konfigurace shromažďování událostí protokolu pomocí nastavení testů](http://msdn.microsoft.com/en-us/48d67891-6018-4549-83e3-213d5d824a02)|
    |**Emulace sítě:** můžete určit, že se mají vrátit zatížení umělé sítě na svůj test s použitím nastavení testu. Emulace sítě s ovlivňuje komunikace do a z počítače pomocí emulace rychlost konkrétní síťového připojení, jako je například telefonického připojení. **Poznámka:** emulace sítě nelze použít ke zvýšení rychlosti připojení k síti.|Emulace sítě s adaptér je ignorován v zátěžových testech. Zátěžové testy místo toho použijte nastavení, které jsou určené v síti směs scénáře zátěžového testu.<br /><br /> Další informace najdete v tématu [určení typů virtuálních síťových](../test/specify-virtual-network-types-in-a-load-test-scenario.md).||
    |**Informace o systému:** nastavení testu můžete nastavit tak, aby zahrnují systémové informace o počítačích, na kterých běží informace o systému Diagnostika a data kolekce. Informace o systému je zadán ve výsledcích testu s použitím nastavení testu.|![Informační ikona, která](../test/media/vc364f4.gif)<br /><br /> Zatížení agenty a systém testovaného lze shromažďovat informace o systému.|Tyto informace můžete shromáždit není nutná žádná konfigurace.|
    |**Test dopad:** můžete shromáždit informace o tom, které byly používány metody kódu aplikace při spuštění testovacího případu. To lze použít společně s změny kódu aplikace, které jsou vytvářeny vývojáři k určení, které testy situace měla vliv na tyto změny vývoj.|Testovací dopad data nejsou shromažďovány se zátěžovými testy.||
    |**Záznam videa:** můžete vytvořit záznam videa plochy relace při spuštění automatizovaných testů. To může být užitečné k zobrazení akce uživatelů pro programového testu uživatelského rozhraní. Video může pomoci ostatní členové týmu izolovat aplikace problémy, které je obtížné reprodukovat. **Poznámka:** při spouštění testů vzdáleně záznam videa nebude fungovat, pokud je agent spuštěn v režimu interaktivní proces.|![Ikona důležité](../test/media/vc364f3.gif) **upozornění:** nedoporučujeme používání adaptéru záznam videa pro zátěžové testy.|[Postupy: zahrnují záznam obrazovky a zvuku během testů s použitím nastavení testu](../test/how-to-include-recordings-of-the-screen-and-voice-during-tests.md)|

19. Zvolte **nasazení**.

     **Nasazení** zobrazí se stránka.

20. Vytvořit samostatný adresář pro nasazení pokaždé, když spustíte testy, vyberte **povolit nasazení**.

    > [!NOTE]
    > Pokud to uděláte, můžete sestavit aplikaci při spuštění testů.

21. Chcete-li přidat soubor do adresáře, který používáte pro spouštění testů, zvolte **přidat soubor**a potom vyberte soubor, který chcete přidat.

    > [!NOTE]
    > Když spustíte testy zatížení, modul plug-in sestavení, datové soubory a odeslané soubory se automaticky nasadí.

22. Přidejte adresář na adresář, který používáte ke spuštění testů, zvolte **adresáře přidat** a poté vyberte adresář, který chcete přidat.

23. Ke spouštění skriptů před a po testy, vyberte **instalační program a skriptů čištění**.

     **Instalační program a skriptů čištění** zobrazí se stránka.

    1.  Zadejte umístění souboru skriptu v **nastavení skriptu** nebo zvolte se třemi tečkami (**...** ) vyhledejte instalační skript.

    2.  Zadejte umístění souboru skriptu v **skript pro vyčištění** nebo zvolte se třemi tečkami (**...** ) vyhledejte skript pro vyčištění.

24. Pokud chcete spustit testy s použitím jiného hostitele, vyberte **hostitele**.

    1.  V **typ hostitele**, ověřte, zda **výchozí** je vybrána.

        > [!NOTE]
        > **ASP.NET** v **hostitele typ** není podporována v zátěžových testech.

    2.  Použijte spuštění testu v 32bitové nebo 64bitové verze procesu rozevíracího seznamu můžete určit, zda chcete webové testy výkonu a jednotka v testu zatížení ke spuštění jako 32bitové nebo 64bitové procesy.

        > [!NOTE]
        > Flexibilní, by měl zkompilování výkon vašich webových a načtení projektů testů pomocí **libovolný procesor** konfigurace. Potom můžete spustit na 32bitové a 64bitové verze agentů. Kompilace výkonu webu a zatížení testování projektů pomocí **64-bit** konfigurace nabízí žádnou výhodu.

25. (Volitelné) Chcete-li omezit dobu, pro každou testu a jednotlivých testů, zvolte **testování vypršení časových limitů.**

    1.  Na zrušení testu spustit, když dojde k překročení časového limitu, vyberte **Abort celkový čas překročí-li spustit test** a pak zadejte hodnotu pro tento limit.

    2.  Při překročení časového limitu, selhání na jednotlivé testy, vyberte **označit jednotlivé testy jako neúspěšná, pokud jeho čas provádění překročí**a zadejte hodnotu pro tento limit.

26. Přeskočit **testování částí**. Zátěžové testy se nedoporučuje používat tato nastavení.

27. Přeskočit **webový Test**. Zátěžové testy se nedoporučuje používat tato nastavení.

28. Chcete-li uložit nastavení testu, zvolte **uložit jako**. Zadejte název souboru, který chcete v **název objektu**.

    > [!NOTE]
    > Pokud je nutné změnit nastavení testu, zvolte **testování** a potom zvolte **upravit Test nastavení** a přejděte na nastavení testů, které jste vytvořili.

### <a name="to-remove-a-test-settings-from-your-solution"></a>Odebrání řešení nastavení testů

Ve složce položky řešení v Průzkumníku řešení klikněte pravým tlačítkem na testovací nastavení, které chcete odebrat a potom vyberte **odebrat**.

Soubor nastavení testu je odebrán z vašeho řešení. Tato změna se odrazí v seznamu nabízených možností pro **vyberte testovací upgrade nastavení Active** a **upravit nastavení testu** možnosti na **Test** nabídky.

## <a name="see-also"></a>Viz také:

- [Kontrolery testů a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)