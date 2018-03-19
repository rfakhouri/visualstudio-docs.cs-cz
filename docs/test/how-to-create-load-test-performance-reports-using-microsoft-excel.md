---
title: "Vytvoření sady Visual Studio výkonu sestav pro zátěžový Test pomocí aplikace Microsoft Excel | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, creating Excel reports
- load tests, reporting
ms.assetid: b87fb196-9973-4512-a924-088788def4ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: c3897a9f316a7bcb0bf52d6730c3622434b6b396
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-load-test-performance-reports-using-microsoft-excel"></a>Postupy: Vytváření sestav výkonnosti pro zátěžový test pomocí aplikace Microsoft Excel

Můžete vygenerovat sestav Microsoft Excel zátěžový test, které jsou založeny na dva nebo více výsledků testů. K dispozici jsou dva typy sestav pro zátěžový test:

-   **Spustit porovnání** tím se vytvoří sada sestavy, které porovnávají data ze dvou výsledků zátěžového testu pomocí tabulky a pruhové grafy.

-   **Trend** můžete vygenerovat analýzy trendů na dva nebo více výsledků zátěžového testu. Výsledky jsou zobrazeny pomocí spojnicových grafů, ale data jsou k dispozici v kontingenční tabulky.

> [!TIP]
> Zkopírováním a vložením dat ze zobrazení se souhrnnými informacemi, zobrazení grafů a tabulek zobrazení můžete také ručně vytvořit sestavy Microsoft Word. V tématu [postupy: ruční vytvoření sestavy výkon testu zatížení pomocí aplikace Microsoft Word](../test/how-to-manually-create-a-load-test-performance-report-using-microsoft-word.md).

 Buď sestava umožňuje sdílet data výkonu s zúčastněným stranám a sdělit, zda celkový výkon a stav systému je zlepšuje nebo programy.

 Definice sestavy jsou uloženy v databázi testu zatížení. Při uložení sestavy definici sestavy je uloženo v databázi a lze znovu použít později.

 Navíc sešitu aplikace Excel je možné sdílet s zúčastněným stranám tak, aby zúčastněným stranám není potřeba připojení k databázi chcete zobrazit sestavu.

> [!NOTE]
> Můžete sdílet sešitu aplikace Excel; jenom uživatelé, kteří mají nainstalovanou na jejich počítači sadu Visual Studio však bude možné upravovat tabulek. Ostatní uživatelé neuvidí **sestava testu zatížení** možnost na pásu karet Office, ale bude moci zobrazit sešit.

 Na následujícím obrázku je příkladem sestavu, která obsahuje korelace mezi odmítnout v transakci (aktualizace košíku) rychlost a degenerace čítače (% procesoru). To ukazuje na potenciální problém v kódu aplikace, místo databáze nebo síti a je vhodný pro diagnostiku pomocí ASP.NET Profiler.

 ![Potenciální problém v kódu aplikace](../test/media/lt_excel.png "LT_Excel")

 Sestavy aplikace Excel můžete buď vytvořit v Analyzéru zátěžového testu pomocí **vytvořit sestavu aplikace Excel** tlačítka na panelu nástrojů nebo z Excelu pomocí **sestava testu zatížení** možnost **zátěžového testu**  karty na pásu karet Office.

> [!NOTE]
> Pokud přidáte komentáře zátěžový test, zobrazí se v sestavě aplikace Excel. Další informace najdete v tématu [postupy: Přidání komentářů během analýzy byla dokončena zátěžového testu](../test/how-to-add-comments-on-a-completed-load-test.md).

## <a name="to-generate-load-test-comparison-reports-using-excel"></a>Ke generování sestav porovnání zátěžový test pomocí aplikace Excel

1.  Před generováním sestavy, je potřeba nejdřív spustit zátěžový test.

2.  Sestavy aplikace Excel zatížení test můžete vytvořit dvěma způsoby:

    1.  Po dokončení testu zatížení v **načíst výsledky testu** vyberte **vytvořit sestavu aplikace Excel** tlačítka na panelu nástrojů.

        > [!NOTE]
        > Pokud **vytvořit sestavu aplikace Excel** tlačítko k dispozici na panelu nástrojů Prohlížeč výsledků testu výkonnosti webu, bude pravděpodobně nutné ke spuštění aplikace Microsoft Excel jeden čas, než je povolený. Když Visual Studio Enterprise je nainstalovaná, Visual Studio Enterprise zatížení testu v aplikaci se zkopírují na váš počítač pro aplikaci Microsoft Excel. k dokončení procesu instalace pro doplněk musí však spustit aplikaci Microsoft Excel.

     Aplikace Microsoft Excel otevře s **vygenerování sestavy testu zatížení** průvodce.

     -nebo-

    1.  Otevřete Microsoft Excel, vyberte **zátěžový Test** kartu na pásu karet Office a potom zvolte **sestava testu zatížení**.

         **Vygenerování sestavy testu zatížení** zobrazí se průvodce.

    2.  V **vyberte databázi, která obsahuje zátěžové testy** v části **název serveru**, zadejte název serveru, jehož výsledků zátěžového testu.

    3.  V **Databasename** rozevíracího seznamu vyberte databázi obsahující výsledků zátěžového testu.

3.  V **jak chcete generovat sestavy** ověřte, zda **vytvoření sestavy** je vybraná a zvolte **Další**.

4.  V **typu hlášení chcete generovat** ověřte, zda **spustit porovnání** je vybraná a zvolte **Další**.

5.  V **Enter zatížení testovací sestava obsahuje podrobnosti o** stránky, zadejte název pro sestavu na **název sestavy**.

6.  Vyberte zátěžový test, kterou chcete vygenerovat sestavu pro a zvolte **Další**.

7.  V **vyberte spuštění pro sestavy** v části **vyberte jeden nebo více používá pro přidání do sestavy**, vyberte dvě načíst výsledky testů, které chcete porovnat v sestavě a zvolte **Další**.

    > [!NOTE]
    > Pouze můžete vygenerovat porovnání sestavy o výsledcích testů dvě zatížení. Pokud vyberete buď výsledků testů zatížení jeden nebo více než dva výsledky zátěžového testu, zobrazí se zpráva s upozorněním.

8.  V **vyberte čítače, sestavy** v části **, vyberte na nebo další čítače při přidání do sestavy** rozevírací seznam čítačů je k dispozici pro sestavu upravit. Vyberte čítače, které chcete porovnat ze dvou vybrané testovací spouští v sestavě a zvolte **Dokončit**.

9. Sestavu sešitu aplikace Excel je vytvořen s následujícími kartami tabulky:

    -   **Obsah** – zobrazí název sestavy testu zatížení a poskytuje obsah s odkazy na různé karty v sestavě.

    -   **Spustí -** poskytuje informace, na kterých jsou dvě spustí porovnávané v sestavě.

    -   **Testování porovnání -** poskytuje pruhový graf podrobné informace o výkonu regresí a vylepšení mezi dvěma spustí porovnávané.

    -   **Stránka porovnání -** poskytuje pruhový graf a výkonu procento porovnání data mezi dvěma běží na různých stránkách v testovací spouští.

    -   **Počítač porovnání -** poskytuje porovnání data mezi dvěma běží na základě počítačů, které byly používány.

    -   **Chyba porovnání -** porovná typů chyb došlo mezi dvěma spustí a počet výskytů.

    > [!TIP]
    > Pro lepší sestavy několik vlastností, které jsou k dispozici v zátěžových testů a testy výkonnosti webu, které umožňují bohatší sestavy. Požadavek na stránku má dvě vlastnosti, které jsou uvedené v sestavách: generování sestav název a cíl. Časy odezvy stránky se ohlásí vůči cíli a vytváření sestav název se použije místo adresy URL v sestavách. V zátěžovém testu spusťte nastavení v části Správa sad čítačů vlastnost značek počítače jsou poskytovány názvy počítačů sestavy. To je velmi užitečné k popisu roli konkrétní počítač v sestavě.

## <a name="to-generate-load-test-trend-reports-using-excel"></a>Ke generování sestav trend zátěžový test pomocí aplikace Excel

1.  Před generováním sestavy, je nutné spustit zátěžový test.

2.  Sestavy aplikace Excel zatížení test můžete vytvořit dvěma způsoby:

    1.  Po dokončení testu zatížení v **načíst výsledky testu** vyberte **vytvořit sestavu aplikace Excel** tlačítka na panelu nástrojů.

        > [!NOTE]
        > Pokud **vytvořit sestavu aplikace Excel** tlačítko k dispozici na panelu nástrojů Prohlížeč výsledků testu výkonnosti webu, bude pravděpodobně nutné ke spuštění aplikace Microsoft Excel jeden čas, než je povolený. Když Visual Studio Enterprise je nainstalovaná, Visual Studio Enterprise zatížení testu v aplikaci se zkopírují na váš počítač pro aplikaci Microsoft Excel. k dokončení procesu instalace pro doplněk musí však spustit aplikaci Microsoft Excel.

     Aplikace Microsoft Excel otevře s **vygenerování sestavy testu zatížení** průvodce.

     -nebo-

    1.  Otevřete Microsoft Excel, vyberte **zátěžový Test** kartu na pásu karet Office a potom zvolte **sestava testu zatížení**.

         **Vygenerování sestavy testu zatížení** zobrazí se průvodce.

    2.  V **vyberte databázi, která obsahuje zátěžové testy** v části **název serveru**, zadejte název serveru, jehož výsledků zátěžového testu.

    3.  V **Databasename** rozevíracího seznamu vyberte databázi obsahující výsledků zátěžového testu.

3.  V **jak chcete generovat sestavy** ověřte, zda **vytvoření sestavy** je vybraná a zvolte **Další**.

4.  V **typu hlášení chcete generovat** ověřte, zda **Trend** je vybraná a zvolte **Další**.

5.  V **Enter zatížení testovací sestava obsahuje podrobnosti o** stránky, zadejte název pro sestavu na **název sestavy**.

6.  Vyberte zátěžový test, kterou chcete vygenerovat sestavu pro a zvolte **Další**.

7.  V **vyberte spuštění pro sestavy** v části **vyberte jeden nebo více používá pro přidání do sestavy**, vyberte výsledků zátěžových testů, které chcete porovnat v sestavě a zvolte **Další**.

8.  V **vyberte čítače, sestavy** v části **, vyberte na nebo další čítače při přidání do sestavy**, rozevírací seznam čítačů je k dispozici pro sestavu upravit. Vyberte čítače, které chcete porovnat pro analýzu trendů a zvolte **Dokončit**.

10. Sestava je generována s tabulkou obsah, který obsahuje odkazy na různé karty sešitu aplikace Excel vygenerované v sestavě. Odkazy jsou založené na vybrané sestavy trendu čítače. Například pokud jste nechali výchozí počítadla vybrali v kroku 7, pak sestavu vygeneruje data, která se zobrazí na samostatných záložkách v aplikaci Excel pro jednotlivé čítače uvedené v kroku 7. Data, která se generuje pro jednotlivé čítače jsou poskytovány trend stylu grafy.

    > [!TIP]
    > Pro lepší sestavy několik vlastností, které jsou k dispozici v zátěžových testů a testy výkonnosti webu, které umožňují bohatší sestavy. Požadavek na stránku má dvě vlastnosti, které jsou uvedené v sestavách: generování sestav název a cíl. Časy odezvy stránky se ohlásí vůči cíli a vytváření sestav název se použije místo adresy URL v sestavách. V zátěžovém testu spusťte nastavení v části Správa sad čítačů vlastnost značek počítače jsou poskytovány názvy počítačů sestavy. To je velmi užitečné k popisu roli konkrétní počítač v sestavě.

## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework

Výsledků zátěžových testů a sestavy obsahovat potenciálně citlivé informace, které lze použít k vytvoření útoku proti počítači nebo síti. Výsledků zátěžových testů a sestavy obsahují názvy počítačů a připojovací řetězce. Je třeba věnovat pozornost tohoto při sdílení sestav pro zátěžový test s jinými uživateli.

## <a name="see-also"></a>Viz také

- [Vytváření sestav zatížení výsledků testů pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md)