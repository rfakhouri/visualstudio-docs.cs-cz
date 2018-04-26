---
title: Konfigurace iterací testů pro zatížení testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios, iterations
- load test, iterations
- load tests, sceanrios
ms.assetid: ac480fb7-f4f7-47dc-9ae5-98be3aca4fba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: a78921ff3415203a26da570a1966e41538ac5535
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="configure-test-iterations-in-a-load-test-scenario"></a>Konfigurace iterací testů ve scénáři zátěžového testu

Konfigurace iterací testů, upravte scénáře zátěžového testu pomocí editoru načíst testování a v okně Vlastnosti. Ve výchozím nastavení je scénáře zátěžového testu nastavený bez zadání maximálního počtu testovacích iterací. Máte možnost konfigurace maximální počet opakování ve scénáři a jak dlouho chcete pozastavit mezi nimi.

## <a name="specify-the-maximum-test-iterations-for-a-scenario"></a>Zadejte maximální testovacích iterací pro scénáře

Můžete zadat maximální počet pokusů, které chcete spustit testy pro scénář pomocí editoru zátěžových testů změnit **maximální testovacích iterací** vlastnost v okně Vlastnosti.

**Maximální iterací testů** vlastnost určuje maximální počet iterací testů ke spuštění pro tento scénář. Stejně jako u **testování iterací** vlastnost v zátěžovém testu spusťte nastavení, což není maximální mezi všechny uživatele na všechny agenty, podle nastavení uživatele.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).

 Kombinace testů sekvenčních jeden iterace je jeden předávání všechny testy v kombinaci. Pro všechny ostatní mix testovací každé spuštění testu se počítá jako iterace. Další informace najdete v tématu [o kombinaci řídicí](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).

 Pokud zátěžového testu je na základě doby trvání zátěžový test a doba trvání vyprší před dokončením počet iterací, test se stále zastaví. Pokud je test na základě iterace a testovacích iterací splnění před iterací scénář, test se zastaví. Doba trvání je nakonfigurována pomocí **spustit trvání** vlastnost v okně vlastnosti přidružené k parametrům spuštění v zátěžovém testu.

 Při splnění počet iterací scénář, tento scénář se zastaví, ale všechny další scénáře active bude nadále spouštět.

> [!NOTE]
> Související vlastnost je **jedinečný** vlastnost na webový test zdroje dat, který prochází po postupně data, po řádcích, ale jenom jeden čas pro každý záznam. Další informace najdete v tématu [přidání zdroje dat do testu výkonnosti webu](../test/add-a-data-source-to-a-web-performance-test.md).

 **Maximální testovacích iterací** vlastnost je užitečná pro různé situace. Některé zatížení testery přednost chování na základě iterace testování, zatímco jiné zatížení testery přednost chování na základě doby trvání testování.

 ![Určení iterací testů ve scénáři](../test/media/loadtest_prop.png "LoadTest_Prop")

### <a name="to-specify-the-maximum-test-iterations"></a>Chcete-li určit maximální testovacích iterací

1.  Otevřete zátěžový test.

2.  Zobrazí se Editor zátěžového testu. Zobrazí se strom zátěžového testu.

3.  V zatížení testovat stromy **scénáře** složky, vyberte uzel scénář, pro který chcete určit maximální počet iterací testů.

4.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Kategorií a vlastností scénáře jsou zobrazeny v okně Vlastnosti.

5.  Do textového pole pro **maximální iterací testů** vlastnosti, typ a hodnotu, která určuje maximální počet testů ke spuštění pro tento scénář, při spuštění zátěžového testu.

    > [!NOTE]
    > Pomocí hodnoty 0 pro **maximální testovacích iterací** vlastnost určuje žádné maximální iterací.

6.  Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Když pak spustíte zátěžový test pomocí nové **maximální iterací testů** hodnotu.

## <a name="specifying-think-times-between-test-iterations-for-a-scenario"></a>Určení dob uvažování mezi testovacími iteracemi pro scénáře

**Vezměte v úvahu dobu mezi testování iterací** je nastavena pomocí okna Vlastnosti při úpravách vlastnosti scénáře zátěžového testu v editoru načíst otestovat.

**Vezměte v úvahu dobu mezi testování iterací** vlastnost se používá k určení množství sekund se má čekat před zahájením iterací testů.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popisy najdete v tématu [načíst vlastnosti scénář otestovat](../test/load-test-scenario-properties.md).

### <a name="to-specify-the-think-times-between-test-iterations"></a>K určení doby uvažování mezi testovacími iteracemi

1.  Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2.  V zatížení testovat stromy **scénáře** složky, vyberte uzel scénáři chcete určit agenty používat.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Tento scénář kategorií a vlastností se zobrazí v okně Vlastnosti.

4.  V hodnotě pro **vezměte v úvahu dobu mezi testování iterací** vlastnost, zadejte číslo představující počet sekund pro čekání před spuštěním další iterace testu.

5.  Po dokončení změn vlastnosti, vyberte **Uložit** na **souboru** nabídky. Potom můžete spustit vaší zátěžového testu pomocí nové **vezměte v úvahu dobu mezi testování iterací** hodnotu.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Konfigurace testovacích agentů a testovací kontrolery pro zátěžové testy](../test/configure-test-agents-and-controllers-for-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)
- [Úpravy dob uvažování pro simulaci prodlev při interakci s lidským webové stránky](../test/edit-think-times-in-load-test-scenarios.md)