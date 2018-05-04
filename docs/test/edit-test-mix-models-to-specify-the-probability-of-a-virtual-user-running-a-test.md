---
title: Úpravy modelů kombinací v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, virtual users
ms.assetid: e3b7d952-9012-400a-8131-3444390a6066
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 591bdaa84d143dc3b639990530a68246dc00385a
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test"></a>Úpravy modelů poměru testů určení pravděpodobnosti spuštění testu virtuálním uživatelem

*Model kombinace testů* určuje pravděpodobnost spuštění testu dané ve scénáři zátěžového testu virtuálním uživatelem. To umožňuje více reálně simulovat zatížení. Místo nutnosti jenom jeden pracovní postup prostřednictvím aplikací, může mít několik pracovních postupů, která je blíž aproximace o tom, jak koncoví uživatelé komunikovat s vašimi aplikacemi.

## <a name="test-mix-model-options"></a>Možnosti Model kombinace testů

Určete jednu z následujících možností model kombinace testů pro vaše scénáře zátěžového testu:

-   **Na základě celkového počtu testů:** Určuje, které webového testu výkonu nebo jednotka se spustí při spuštění iterace testu virtuálním uživatelem. Počet pokusů, které konkrétní test byl spuštěn na konci zátěžový test, odpovídá rozdělení přiřazené testu. Tento model kombinace testů používejte při poměru testů jsou založenou na procenta transakce v protokolu služby IIS nebo v provozními daty.

-   **Na základě počtu virtuálních uživatelů:** určuje procento virtuální uživatelů, kteří budou používat konkrétní test výkonu nebo jednotka webu. Počet uživatelů, kteří jsou spuštěné konkrétní test v libovolném bodě zátěžový test, odpovídá přiřazené rozdělení. Tento model kombinace testů používejte, když poměru testů jsou založenou na procento uživatelům používajícím konkrétní test.

-   **Na základě stimulací podle uživatele:** v průběhu zátěžový test každé testu výkonnosti webu nebo testování částí spuštění zadaného počtu opakování na uživatele za hodinu. Tento model kombinace testů použijte, pokud chcete virtuální uživatelům spuštění testu v určitých intervalech v rámci zátěžového testu.

-   **Na základě v sekvenčním pořadí:** každý virtuální uživatel spustí testy výkonu nebo jednotka webu v pořadí, že testy jsou definovány v tomto scénáři. Virtuálních uživatelů dál prosté prostřednictvím testů v tomto pořadí, až do dokončení zátěžový test.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Určení kombinace testů pro zátěžový test:** při vytvoříte zátěžový test, zadejte nastavení pro zátěžový test v načíst testování Průvodce novým. V nové průvodce zátěžovým testem vyberte existující Web a testování částí pro přidání do počáteční scénář. Po přidání testů ve scénáři, zadáte poměru testů pro scénář.<br /><br /> Používáte více přesně odhadnout očekávané reálného využití webové stránky nebo aplikace, která zatížení testujete zatížení modelování možnosti. Je důležité k tomu, protože zátěžový test, který není založen na model přesné zatížení může generovat zavádějící výsledky.|-   [Emulace očekávaného reálného využití webové stránky nebo aplikace](../test/emulate-real-world-usage-of-a-web-site-in-a-load-test-using-test-mix-models.md)|
|**Upravit model kombinace testů:** scénáře zátěžového testu použít jednu z modelů poměru testů pomocí editoru načíst otestovat, můžete změnit.||
|**Konfigurace intervalu zpoždění pro model kombinace pracovníky testovací uživatele:** Pokud vaše scénáře zátěžového testu je konfigurován pro použití **na základě uživatele model kombinace testů se stimulací podle**, můžete určit, jak se mají distribuční Pacing zpoždění nakonfigurované.|-   [Postupy: použití rozdělení pro zpoždění stimulace, používá Model kombinace testů se stimulací podle uživatele](../test/how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model.md)|

## <a name="change-the-test-mix-model-in-a-scenario"></a>Změňte Model kombinace testů ve scénáři

Jakmile vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností scénáře pro splnění vašich potřeb testování a cíle.

> [!NOTE]
> Úplný seznam nastavení vlastnosti zatížení a jejich popisy najdete v tématu [načíst vlastnosti testovací scénáře](../test/load-test-scenario-properties.md).

Pomocí editoru načíst otestovat, můžete změnit model kombinace testů ve scénáři zátěžového testu pomocí úpravy **testování typ kombinace** vlastnost v okně Vlastnosti.

### <a name="to-change-the-test-mix-model"></a>Chcete-li změnit model kombinace testů

1.  Otevřete zátěžový test.

     Zobrazí se Editor zátěžového testu. Zobrazí se strom zátěžového testu.

2.  V **scénáře** stromu testu zatížení, vyberte uzel scénář, pro který chcete určit maximální počet iterací testů.

3.  Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

     Zobrazí se kategorií a vlastností scénáře.

4.  V **typu kombinace testu** vlastnost, zvolte tlačítko se třemi tečkami ( **...** ).

     Zobrazí se dialogové okno Upravit poměru testů.

5.  Vyberte rozevíracím seznamu v části **model kombinace testů** a vyberte model kombinace testů, který chcete použít pro tento scénář.

6.  (Volitelné) Úpravy poměru testů pomocí **přidat**, **odebrat** a **distribuovat** tlačítka a distribuce posuvníky. Další informace najdete v tématu [úpravy kombinace testů zadejte, které testy mají zahrnout do scénáře zátěžového testu](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).

7.  (Volitelné) Zadejte webový test výkonu a jednotky k inicializaci nebo ukončení pomocí zaškrtávacích políček a výběrem požadované testy. Další informace najdete v tématu [emulace očekává reálného využití webové stránky nebo aplikace](../test/emulate-real-world-usage-of-a-web-site-in-a-load-test-using-test-mix-models.md).

8.  Zvolte **OK**.

     **Vlastnosti** v okně se zobrazí nový model kombinace testů pro **testování typ kombinace** vlastnost.

9. Po provedení změny vlastnosti, vyberte **Uložit** na **souboru** nabídky. Když pak spustíte zátěžový test pomocí nové **testování typ kombinace** hodnotu.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)