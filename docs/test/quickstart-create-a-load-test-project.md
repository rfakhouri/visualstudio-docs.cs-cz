---
title: Vytvoření výkonu webu a zatížení testovacího projektu v sadě Visual Studio
ms.date: 03/14/2018
ms.topic: quickstart
helpviewer_keywords:
- load testing, quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 4349220f650eef98ee765c1e7dbacb69263fe845
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976712"
---
# <a name="quickstart-create-a-load-test-project"></a>Rychlý úvod: Vytvoření projektu testování zatížení

V tento rychlý start 10 minut dozvíte, jak vytvořit a spustit výkonu webu a zatížení testovacího projektu v sadě Visual Studio. Zátěžové testy spustit výkonu webů nebo testy jednotek k simulaci mnoha uživateli přístup k serveru ve stejnou dobu.

> [!IMPORTANT]
> Projektů webové testování výkonu a zatížení jsou dostupné pouze v edici Enterprise systému Visual Studio 2017.

## <a name="install-the-load-testing-component"></a>Nainstalujte zatížení testování součásti

Pokud nemáte již výkonu webů a spouštění testování nainstalována součást nástroje, musíte ji nainstalovat prostřednictvím Instalační program Visual Studio.

1. Instalační program Visual Studio otevřete z nabídky Start v systému Windows. Můžete také k němu přístup v sadě Visual Studio z **nový projekt** dialogové okno, nebo výběrem **nástroje** > **funkcí a nástrojů pro získání...**  z řádku nabídek.

1. V instalačním programu Visual Studio, vyberte **jednotlivých součástí** kartě a přejděte dolů k položce **ladění a testování** části. Vyberte **výkonnosti webů a zátěžové testování nástroje**.

   ![Výkonnosti webů a zátěžové testování součást nástroje](media/web-perf-load-testing-tools-component.png)

1. Vyberte **upravit** tlačítko.

   Je nainstalována výkonu webu a zatížení testování součást tools.

## <a name="create-a-load-test-project"></a>Vytvoření projektu testování zatížení

V této části vytvoříme projekt testu zatížení C#. Testovacího projektu Visual Basic zatížení, můžete také vytvořit, pokud dáváte přednost.

1. Otevřete Visual Studio a zvolte **soubor** > **nový** > **projektu...**  z řádku nabídek.

   **Nový projekt** otevře se dialogové okno.

1. V **nový projekt** dialogové okno, rozbalte seznam **nainstalovaná** a **Visual C#** a pak vyberte **Test** kategorie. Vyberte **výkonu webu a zatížení testovacího projektu** šablony.

   ![Výkon webové a zatížení testovací šablona projektu](media/web-perf-load-test-project-template.png)

1. Zadejte název projektu, pokud nechcete použít výchozí název a potom vyberte **OK**.

   Visual Studio vytvoří projekt a zobrazí soubory v **Průzkumníku řešení**. Projekt původně obsahuje jeden testovací soubor Web s názvem *WebTest1.webtest*.

## <a name="add-a-load-test-to-the-project"></a>Do projektu přidat zátěžový test

1. V nabídce klikněte pravým tlačítkem, nebo v místní nabídce uzlu projektu v **Průzkumníku řešení**, zvolte **přidat** > **zátěžový Test...** .

   **Nového Průvodce zátěžovým testem** otevře.

1. Vyberte **místní zátěžový Test** možnost a potom vyberte **Další**. Další informace o cloudové zátěžové testování [zde](/vsts/load-test/get-started-simple-cloud-load-test).

   ![Nového Průvodce zátěžovým testem – první stránka](media/load-test-wizard-page-1.png)

1. Zvolte **Další** ke kroku pomocí průvodce, dokud se nedostanete **přidejte testů do scénáře zátěžového testu a úpravy poměru testů** stránky. Vyberte **přidat** tlačítko.

   **Přidat testy** otevře se dialogové okno.

1. V části **dostupné testy**, vyberte **WebTest1**a klikněte na šipku vpravo se jej přesunout **vybrané testy** pole. Vyberte **OK** tlačítko.

   ![Testy dialogové okno Přidat](media/add-tests-dialog-box.png)

1. Zpět v **nového Průvodce zátěžovým testem**, vyberte **Dokončit** tlačítko.

   Zátěžový test se přidá do projektu a zatížení testovací soubor se otevře v okně editoru.

## <a name="run-the-load-test"></a>Spuštění zátěžového testu

Vytvořili jsme zátěžový test, který není nechcete velmi velká, ale můžeme ho i přesto spustit.

V místní nabídce, nebo místní nabídku zátěžový test, který je otevřen v editoru, zvolte **spustit načíst testování**.

![Nabídky spuštění zátěžového testu](media/run-load-test.png)

Zátěžový test spuštění. **Výsledky testu** okno ukazuje, že probíhá test a analyzéru zátěžového testu se zobrazí v okně editoru. Po dokončení testu, který by mělo být pět minut, pokud jste přijali výchozí hodnoty, souhrn se zobrazí v editoru. Můžete zvolit **grafy**, **tabulky**, nebo **podrobností** získat různé informace o výsledcích zátěžového testu.

![Okno analyzátor testu zatížení](media/load-test-analyzer.png)

## <a name="next-steps"></a>Další kroky

Teď, když jste vytvořili projekt testu jednoduché zatížení, dalším krokem je konfigurace pro scénáře, sad čítačů a nastavení spouštění.

> [!div class="nextstepaction"]
> [Upravit nastavení testů](edit-load-tests.md)