---
title: Emulace reálného využití webové stránky pro zatížení testování v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load model, specifying
- load test load model, specifying
ms.assetid: b7fae849-0538-40d1-ab35-2bb3a0fe4393
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 0458135040209f79648ca299bc56ba3acae21908
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="emulate-expected-real-world-usage-of-a-web-site-or-application-in-a-load-test-using-a-test-mix-models"></a>Emulovat očekávaného reálného využití webové stránky nebo aplikace v zátěžovém testu s použitím modelů kombinace testů

Používáte více přesně odhadnout očekávané reálného využití webové stránky nebo aplikace, která zatížení testujete zatížení modelování možnosti. Je důležité k tomu, protože zátěžový test, který není založen na model přesné zatížení může generovat zavádějící výsledky.

## <a name="test-mix-model-enhancements"></a>Vylepšení Model kombinace testů

Pomocí editoru načíst testování nebo Průvodce model kombinace testů, můžete zadat následující typy poměru testů pro scénáře zátěžového testu. Další informace najdete v tématu [změna Model kombinace testů ve scénáři](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

Určete jednu z následujících možností model kombinace testů pro vaše scénáře zátěžového testu:

-   **Na základě celkového počtu testů:** Určuje, které webového testu výkonu nebo jednotka se spustí při spuštění iterace testu virtuálním uživatelem. Na konci zátěžový test odpovídající počet pokusů, které spuštění testu konkrétní distribuční přiřazené testu. Tento model kombinace testů používejte při poměru testů jsou založenou na procenta transakce v protokolu služby IIS nebo v provozními daty. Další informace najdete v tématu [procento podle spustit testy](#BasedOnTestsStarted).

-   **Na základě počtu virtuálních uživatelů:** určuje procento virtuální uživatelů, kteří budou používat konkrétní test výkonu nebo jednotka webu. Počet uživatelů, kteří jsou spuštěné konkrétní test v libovolném bodě zátěžový test, odpovídá přiřazené rozdělení. Tento model kombinace testů používejte, když poměru testů jsou založenou na procento uživatelů, kteří jsou spuštěné konkrétní test. Další informace najdete v tématu [procento podle virtuálních uživatelů](#PercentageBasedonVirtualUsers).

-   **Na základě stimulací podle uživatele:** v průběhu zátěžový test každé testu výkonnosti webu nebo testování částí spuštění zadaného počtu opakování na uživatele za hodinu. Tento model kombinace testů použijte, pokud chcete virtuální uživatelům spuštění testu v určitých intervalech v rámci zátěžového testu. Další informace najdete v tématu [poměru testů Pacing](#PacingTestMix).

    > [!TIP]
    > Pokud vyberete **poměru testů procento** a pokud vyberete **procento podle virtuálních uživatelů**? Rozdíl mezi tyto dvě možnosti je důležité, pokud některé testy v poměru testů mnohem delší dobu než jiné testy. V takovém případě byste měli pravděpodobně zvolit **procento podle virtuálních uživatelů**. Tato volba umožňuje vyhnout se spustit test v které pravděpodobnost zvyšuje, že příliš mnoho uživatelů bude spuštěna dlouho trvání testy. Ale pokud testy všechny podobné doby trvání, více bezpečně můžete **poměru testů procento**.

-   **Na základě v sekvenčním pořadí:** každý virtuální uživatel spustí testy výkonu nebo jednotka webu v pořadí, že testy jsou definovány v tomto scénáři. Virtuálních uživatelů dál prosté prostřednictvím testů v tomto pořadí, až do dokončení zátěžový test. Další informace najdete v tématu [sekvenčním pořadí](#SequentialOrder).

###  <a name="BasedOnTestsStarted"></a> Procento podle testy spuštění
 Pro každý test v kombinaci můžete zadat procentuální hodnotu, která určuje, jak často je test vybrán jako další test ke spuštění. Může například přiřadit tři testy následující procentní hodnoty:

-   TestA (50%)

-   TestB (35 %)

-   TestC (15%)

 Pokud použijete toto nastavení, další test spusťte je založena na přiřazené procenta. Můžete to udělat bez ohledu na počet virtuálních uživatelů, kteří jsou aktuálně spuštěny všechny testy.

###  <a name="PercentageBasedonVirtualUsers"></a> Procento podle virtuálních uživatelů
 Tento model kombinace testů určuje procento virtuálních uživatelů, kteří se spustil konkrétní test. Pokud chcete použít tento model kombinace testů, je založena další test spustit jenom na přiřazené procenta, ale také na procento virtuálních uživatelů, kteří jsou aktuálně spuštěny konkrétní test. V libovolném bodě zátěžový test počet uživatelů, kteří jsou spuštěné konkrétní test co nejvíce odpovídá přiřazené rozdělení.

###  <a name="PacingTestMix"></a> Interval poměru testů
 Pokud zadáte intervalu poměru testů, nastavíte počet spuštění testu pro každý virtuální uživatele pro každý test v poměru testů. Pro jednotlivé testy dělají tento kurz je vyjádřen jako testu na virtuální uživatele na hodinu. Například můžete přiřadit následující intervalu poměru testů na následující testy:

-   TestA: 4 testy na uživatele na hodinu

-   TestB: 2 testy na uživatele na hodinu

-   TestC: 0,125 testy na uživatele na hodinu

 Pokud používáte intervalu model kombinace testů, modul runtime testu zatížení zaručuje, že skutečná rychlost, kdy jsou spuštění testů je menší než nebo rovna hodnotě určenou míru. Pokud testy spuštění příliš dlouhý pro přiřazené číslo, které má být dokončena, je vrácena chyba.

 **Vezměte v úvahu dobu mezi testování iterací** nastavení neplatí, pokud použijete intervalu poměru testů.

#### <a name="applying-distribution-to-pacing-delay"></a>Použití rozdělení pro interval zpoždění
 Hodnota **použít distribuční interval zpoždění** ve scénáři zátěžového testu může být nastavena na hodnotu true nebo false:

-   **Hodnota TRUE,**: scénáři použije typické statistické distribuční zpoždění určená hodnotou v **testy na uživatele za hodinu** sloupec v dialogu Upravit poměru testů. Další informace najdete v tématu [úpravy modelů kombinací určení pravděpodobnosti virtuální uživatele spuštění testu](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Předpokládejme například, že máte **testy na uživatele za hodinu** hodnota v upravit testování kombinace dialogové okno pro test 2 uživatelům za hodinu. Pokud **použít distribuční interval zpoždění** je nastavena na **True**, typické statistické distribuce se použije na dobu čekání mezi testy. Testy stále spouštět 2 testy za hodinu, ale nemusí být nutně 30 minut mezi nimi. První test by mohl spustit až 4 minuty a druhý test po 45 minut.

-   **False**: testy spustí konkrétní tempem, jste zadali pro hodnotu v **testy na uživatele za hodinu** sloupec v dialogu Upravit poměru testů. Další informace najdete v tématu [úpravy modelů kombinací určení pravděpodobnosti virtuální uživatele spuštění testu](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Předpokládejme například, že máte **testy na uživatele za hodinu** hodnota v upravit testování kombinace dialogové okno pro test 2 uživatelům za hodinu. Pokud **použít distribuční interval zpoždění** je nastavena na **False**, v podstatě udělujete žádné volně mohou při spuštění testů. Test se spouští každých 30 minut. Tím je zajištěno, že můžete spustit 2 testy za hodinu.

 Další informace najdete v tématu [postupy: použití rozdělení pro interval zpoždění při použití uživatel Model kombinace testů rychle](../test/how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model.md).

###  <a name="SequentialOrder"></a> Sekvenčním pořadí
 Výběr založený na test sekvenčních order – možnost umožňuje jednotlivých virtuálních uživatelů spustit všechny testy ve scénáři v pořadí, aby byly definovány testy.

## <a name="test-iterations-property"></a>Vlastnost iterací testů
 Ve vlastnostech spustit nastavení můžete zadat hodnotu pro vlastnost testovacích iterací. Tato hodnota je počtu testovacích iterací ke spuštění v zátěžovém testu. Po spuštění zadaného počtu testovacích iterací, spustí se bez ohledu na nastavení všech profilů zatížení žádné další testovacích iterací. Po dokončení počtu testovacích iterací zadaný končí zátěžový test. Další informace najdete v tématu [postup: Zadejte číslo testovacích iterací v nastavení Spustit](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md).

## <a name="initialize-and-terminate-tests"></a>Inicializace a ukončení testů
 Můžete vybrat testů ke spuštění na začátku a na konci každého virtuálního uživatele zatížení testování relace. Další informace najdete v tématu [úpravy modelů kombinací určení pravděpodobnosti virtuální uživatele spuštění testu](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

-   **Inicializace testovacího**. Tento test běží každý uživatel, virtuální předtím, než se spouští všechny testy v poměru testů.

-   **Ukončit test**. Tento test se spouští po spuštění všech testů pro konkrétní virtuální uživatele.

 Všimněte si následujícího o testovací inicializovat a testování ukončit:

-   Doba trvání testu zatížení podle času místo můžete zadat počet iterací. V takovém případě po dokončení zátěžového testu, spuštění doba trvání testu provedení příkazu Ukončit se nespustí.

-   Je-li inicializovat test testování částí nebo testu výkonnosti webu, uložení stavu objektu TestContext nebo WebTestContext, po dokončení testu inicializovat. Ji pak bude sloužit jako výchozí kontext pro iterací testů v poměru testů.

-   Noví uživatelé, jak jsou definovány v vlastnost scénář procento nových uživatelů, vždy spustit test inicializovat, jeden iterace testu z kombinace testů a testovací ukončit.

## <a name="see-also"></a>Viz také

- [Úpravy modelů kombinací určení pravděpodobnosti spuštění testu virtuálním uživatelem](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)
- [Úpravy vzorů zatížení pro modelování aktivit virtuálních uživatelů](../test/edit-load-patterns-to-model-virtual-user-activities.md)
- [Úpravy kombinace testů určující, které testy mají být zahrnuty scénáře zátěžového testu](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)
- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)
- [Změna Model kombinace testů ve scénáři](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)