---
title: Parametry spuštění zátěžového testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: reference
helpviewer_keywords:
- load tests, run settings
ms.assetid: de10dabb-02ed-403b-9e6f-0b735524988c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: c3f057a5642fd18affca6894521a5648f01aeb1c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977670"
---
# <a name="load-test-run-settings-properties"></a>Vlastnosti parametrů běhu zátěžových testů

Nastavení spuštění zátěžového testu určit celou řadu dalších nastavení, včetně doba trvání testu, úroveň podrobností výsledků kolekce a sad čítačů, které byly shromážděny při spuštění testu. Pro každý zátěžový test lze vytvořit a uložit několik parametrů spuštění a následně při spouštění testu zvolit jedno konkrétní nastavení. Počáteční spustit nastavení se přidá do zátěžový test, při vytváření vaší zátěžový test pomocí nového načíst testování průvodce.

 Následující tabulky popisují různé vlastnosti pro nastavení testu zatížení. Tyto vlastnosti lze upravit tak, aby splňovaly konkrétní požadavky zátěžového testu.

 Další informace najdete v tématu [konfigurace parametrů běhu testu zatížení](../test/configure-load-test-run-settings.md).

## <a name="general-properties"></a>Obecné vlastnosti

|Vlastnost|Definice|
|--------------|----------------|
|**Popis**|Popis nastavení spustit.|
|**Maximální chyba podle typu**|Maximální počet chyb podle typu uložit pro zátěžový test.<br /><br /> Pokud je nutné, ale tato funkce se také zvýší velikost a doba zpracování výsledků testu zatížení, můžete tento počet zvýšit.|
|**Maximální požadavek adresy URL hlášené**|Maximální počet jedinečných testu výkonnosti webu požadavek adresy URL, na které se mají sestavy o výsledcích v tomto testu zatížení.<br /><br /> Pokud je nutné, ale tato funkce se také zvýší velikost a doba zpracování výsledků testu zatížení, můžete tento počet zvýšit.|
|**Maximální mezních hodnot**|Maximální počet pravidel mezních hodnot pro uložení pro tento test zatížení.<br /><br /> Pokud je nutné, ale tato funkce se také zvýší velikost a doba zpracování výsledků testu zatížení, můžete tento počet zvýšit.|
|**Spouštění testů jednotek v doméně aplikace**|Logická hodnota, která určuje, zda každý jednotkové testování sestavení poběží v samostatné doméně aplikace při testování částí obsahuje zátěžový test. Ve výchozím nastavení má hodnotu True.<br /><br /> Pokud testy jednotek nevyžadují souboru samostatné aplikace domény nebo app.config fungoval správně, může rychlejší spuštění testů jednotek pomocí nastavení hodnota této vlastnosti `False`.|
|**Jméno**|Název nastavení Spustit jako se objeví v **spustit nastavení** uzlu **editoru zátěžových testů**.|
|**Úroveň ověřování**|Definuje ověřovací pravidlo, které se spustí v zátěžovém testu nejvyšší úrovně. Ověřovací pravidla jsou přidruženy k požadavků na test výkonnosti webu. Každé pravidlo ověření má úroveň přidruženého ověřování: **vysokou**, **střední**, nebo **nízká**. Tento test zatížení spusťte nastavení specifikujete které ověření pravidla se spustí při spuštění testu výkonnosti webu v zátěžovém testu. Například pokud spustíte nastavení nastavena na **střední**, všechna pravidla ověřování označen jako **střední**, nebo **nízká** bude spuštěna.|

## <a name="logging-properties"></a>Vlastnosti protokolování

|Vlastnost|Definice|
|--------------|----------------|
|**Protokolů maximální testování**|Určuje maximální počet protokolů testování uložit pro zátěžový test. Pokud hodnota zadaná pro maximální počet je dosaženo protokolů testování, zátěžového testu se zastaví shromažďování protokolů. Proto budou shromažďovány protokoly na začátku testu není element end. Zátěžový test bude nadále spouštět, dokud nebude dokončena.|
|**Uložit protokol frekvence pro dokončené testy**|Určuje četnost, kdy se zapíše protokol testu. Číslo označuje, že jeden z každé zadané číslo testů budou uloženy do protokolu testovací. Zadat hodnotu deset například určuje, že desetinu, dvacetinu, třicetiny a tak dále se zapíšou do protokolu testu. Nastavte tuto hodnotu na 0 určuje, že budou uloženy žádné protokolů testování.<br /><br /> Další informace najdete v tématu [postup: Zadejte, jak často ukládání protokolů testování](../test/how-to-specify-how-frequently-test-logs-are-saved.md)|
|**Uložit protokol o selhání testu**|Logická hodnota, která určuje, zda jsou ukládány protokolů testování, pokud se test nezdaří v zátěžovém testu. Výchozí hodnota je `True`.<br /><br /> Další informace najdete v tématu [postupy: určení, zda jsou selhání při testu ukládána do protokolů testování](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|

 Další informace najdete v tématu [úprava nastavení protokolování zatížení testů](../test/modify-load-test-logging-settings.md).

## <a name="results-properties"></a>Vlastnosti výsledků

|Vlastnost|Definice|
|--------------|----------------|
|**Typ úložiště**|Způsob ukládání čítače výkonu, které byly získány v zátěžovém testu. Možnosti jsou následující:<br /><br /> -   **Databáze** -vyžaduje databázi SQL, který má **uložení výsledků zátěžového testu**.<br />-   **Žádný**.|
|**Úložiště podrobností časování**|To se používá k určení, které informace se uloží v **uložení výsledků zátěžového testu**. K dispozici jsou tři hodnoty:<br /><br /> -   **AllIndividualDetails** – shromažďovat a ukládat hodnoty jednotlivých časování pro každý test, transakce a stránky, které se spustit nebo vydán během zátěžového testu v **uložení výsledků zátěžového testu**. Je vyžadován, jestliže máte v úmyslu použít grafu aktivity virtuálních uživatelů v Analyzéru zátěžového testu.<br />     Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).<br />-   **Žádný** -neshromažďují žádné hodnoty jednotlivých časování. Toto je výchozí hodnota pro Visual Studio 2013 Update 4 a novější verze.<br />-   **StatisticsOnly** – shromáždit a uložit pouze statistiku místo ukládání hodnot jednotlivých časování pro každý test, transakce a stránky, který byl proveden nebo vydán během zátěžového testu v **uložení výsledků zátěžového testu**.<br /><br /> Další informace najdete v tématu [postupy: určení vlastnosti úložiště podrobností časování](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md).|

## <a name="sql-tracing-properties"></a>Vlastnosti trasování SQL

|Vlastnost|Definice|
|--------------|----------------|
|**Minimální trvání operace Trasovaná SQL**|Minimální trvání operace SQL možné je zachytit pomocí trasování SQL, v milisekundách. Například tímto způsobem můžete ignorovat operací, které rychle Pokud chcete najít operace SQL, které jsou pomalé zatížení.|
|**Trasování SQL připojovacím řetězci**|Připojovací řetězec, který se používá pro přístup k databázi k trasování.|
|**Adresář trasování SQL**|Umístění, kde je soubor trasování SQL put po ukončení trasování. Tento adresář musí mít oprávnění k zápisu pro SQL Server a oprávnění ke čtení pro kontroler.|
|**Povolené trasování SQL**|To umožňuje trasování operací SQL. Výchozí hodnota je `False`.|

## <a name="test-iterations-properties"></a>Vlastnosti iterací testů

|Vlastnost|Definice|
|--------------|----------------|
|**Testovacích iterací**|Určuje celkový počet jednotlivých testů ke spuštění před dokončením zátěžový test. Tato vlastnost se týká pouze pokud je vlastnost "použití testovacích iterací" `True`.|
|**Použití testovacích iterací**|Pokud je iterací testů pomocí `True`, pak spustí zátěžový test, dokud nedosáhne číslo, která je zadána vlastnost "Iterací testů" počet jednotlivých testů dokončeny v rámci zátěžového testu. V takovém případě nastavení na základě času, které jsou tedy, doba trvání spuštění a doba trvání chladnutí, jsou ignorovány. Pokud je "Použití testovacích iterací" `False`, použije všechna nastavení časování a "Testovacích iterací" je ignorována.|

 Další informace najdete v tématu [postup: Zadejte číslo testovacích iterací v nastavení Spustit](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md).

## <a name="timing-properties"></a>Vlastnosti časování

|Vlastnost|Definice|
|--------------|----------------|
|**Doba chladnutí**|Doba trvání testu chladnutí období, vyjádřené ve formátu hh: mm:. Po dokončení zátěžový test, může být stále spuštěn jednotlivé testy v rámci zátěžového testu. Během období chladnutí tyto testy můžete pokračovat, dokud po dokončení nebo je dosaženo konce dobu chladnutí. Ve výchozím nastavení neexistuje žádný dobu chladnutí a jednotlivých testů jsou ukončen po dokončení podle nastavení Doba trvání spuštění zátěžového testu.|
|**Spustit doba trvání**|Délka testu ve formátu hh: mm:.|
|**Vzorkovací frekvence**|Interval, ve kterém chcete zaznamenat hodnoty čítače výkonu ve formátu hh: mm:.<br /><br /> Další informace najdete v tématu [postupy: určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md).|
|**Horké až Doba trvání**|Interval mezi začátky test a vzorků dat při spuštění, se zaznamenávají do formátu hh: mm:. To se často používá k krok zatížení virtuálních uživatelů k dosažení určité úrovně zatížení před provedením záznamu ukázkové hodnoty. Ukázkové hodnoty, které jsou zachyceny před koncem období warm-up se zobrazují v **Analyzéru zátěžového testu**.|

## <a name="webtest-connections-properties"></a>Vlastnosti připojení testu webu

|Vlastnost|Definice|
|--------------|----------------|
|**Model připojení testu webu**|Tato volba určuje použití daného připojení od agenta test zatížení na webovém serveru pro testy výkonnosti webu, které běží v zátěžovém testu. Jsou k dispozici tři webové výkonu test připojení model možnosti:<br /><br /> -Na **připojení na uživatele** modelu simuluje chování uživatele, který používá skutečné prohlížeče. Pokud je simulované aplikace Internet Explorer 6 nebo Internet Explorer 7, každý virtuální uživatel, který běží testu výkonnosti webu používá jedno nebo dvě vyhrazené připojení k webovému serveru. První připojení při prvním požadavku v testu výkonnosti webu. Druhé připojení může použít, pokud stránka obsahuje více než jeden požadavek na závislé. Tyto požadavky jsou vydávány paralelně s použitím dvě připojení. Tato připojení jsou opakovaně pro následné požadavky v testu výkonnosti webu. Připojení jsou uzavřeny po dokončení testu výkonnosti webu. Nevýhodou k tomuto modelu je, že počet připojení, která je otevřena v počítači agenta, může být vysoká (až dvakrát uživatele zatížení). Prostředky, které jsou potřebné k podpoře tento počet vysoké připojení v důsledku toho může omezit uživatele zatížení, která může řízené od agentů testu jedné zatížení. Pokud je simulované aplikace Internet Explorer 8, jsou podporovány šesti souběžných připojení.<br />-Na **fondu připojení** modelu šetří prostředky na agenta test zatížení při sdílení připojení k webovému serveru mezi několik virtuálních uživatelů test výkonu webové. Pokud je větší než velikost fondu připojení uživatele zatížení, webové testy výkonu, které spouštějí různé virtuální uživatelé budou sdílet připojení. To může znamenat, že jeden testu výkonnosti webu pravděpodobně muset počkat, než se vydá požadavek, když připojení používá jiného testu výkonnosti webu. Průměrnou dobu, která sleduje webového testu výkonnosti čeká, než odešle žádost o zatížení otestujte čítače výkonu Průměrná čekací doby připojení. Toto číslo musí být menší než průměrná doba odezvy pro stránku. Pokud není, je pravděpodobně příliš malá velikost fondu připojení.<br />-Na **připojení na testování iterace** modelu určuje použití vyhrazených připojení pro každou iteraci testu.|
|**Velikost fondu připojení testu webu**|Určuje maximální počet připojení, aby mezi agentem test zatížení a webový server. To se vztahuje pouze **fondu připojení** modelu.|

##  <a name="LoadTestRunSettingsHowToChange"></a> Změna vlastnosti spuštění nastavení
 K zátěžovému testu lze přidat více parametrů spuštění s různými nastaveními vlastností a spouštět tak zátěžový test za jiných podmínek. Lze například přidat nové nastavení testu a použít jinou vzorkovací frekvenci či zadat delší dobu běhu. Současně lze použít pouze jedno spuštění nastavení a je nutné zadat, která spustit nastavení, můžete používat označením jako aktivní. Příklad, naleznete v části [postup: Vyberte Active nastavení spouštění pro zátěžový Test](../test/how-to-select-the-active-run-setting-for-a-load-test.md).

### <a name="to-change-run-settings"></a>Chcete-li změnit nastavení spuštění

1.  Otevřete zátěžový test.

2.  Rozbalte **spustit nastavení** složky.

3.  Vyberte **spustit nastavení** uzlu.

4.  Na **zobrazení** nabídce zvolte **vlastnosti – okno**.

     **Vlastnosti – okno** se zobrazí a zobrazí se vlastnosti vybrané nastavení spuštění.

5.  Použití **vlastnosti – okno** Chcete-li změnit nastavení spuštění. Můžete například změnit pro spuštění dobu trvání **00:05:00** spustit svůj test na pět minut.

    > [!NOTE]
    > Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).

6.  Po dokončení změn vlastností uložte zátěžový test. Na **souboru** nabídky, zvolte **Uložit**.

> [!NOTE]
> Mapování sady čítačů jsou taky součástí parametrů běhu. Další informace najdete v tématu [určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)