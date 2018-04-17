---
title: Přiřazení rolí k testovacímu Kontroleru a testovacímu agentovi pro automatizované testování v sadě Visual Studio | Microsoft Docs
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- testing, walkthroughs, test controller and test agents
- test agent, walkthrough
- walkthroughs [Visual Studio ALM] testing
- test controller, walkthrough
- walkthroughs, test controller and test agents
ms.assetid: 57ed43ae-4e67-4139-8aec-3e9fceb0a745
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 932a6fe470812fc647cad653fb95ba7ca8997ab0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="assign-roles-to-a-test-controller-and-test-agent"></a>Přiřazení rolí k testovacímu Kontroleru a testovacímu agentovi

Tento návod ukazuje, jak vytvořit a nakonfigurovat nastavení testu, který využívá testovacího kontroléru a agenta test k distribuci testování mezi několik počítačů pomocí sady Visual Studio. Kromě toho tento návod ukazuje, jak přidat adaptérů diagnostiky a dat do nastavení testu.

V tomto návodu dokončí následující úkoly:

-   Vytvoření nastavení testu.

-   Testovací kontrolery a testovací agenti přiřadíte role.

-   Diagnostika a data adaptéru přiřadíte vaše nastavení testu.

## <a name="prerequisites"></a>Požadavky

-   Vytvořte testy jednotek nebo programové testy uživatelského rozhraní se spouští s nastavení testu.

-   Testovací kontrolery a testovací agenty nainstalujte. Informace o tom, jak nainstalovat řadič testů a testovací agenti najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

## <a name="to-create-and-configure-a-test-setting"></a>Vytvořit a nakonfigurovat nastavení testu

1.  V Průzkumníku řešení klikněte pravým tlačítkem na **položky řešení** přejděte na příkaz **přidat**a potom zvolte **novou položku**.

     **Přidat novou položku** zobrazí se dialogové okno.

2.  V **nainstalovaných šablonách** podokně vyberte **nastavení testu**.

3.  V **název** zadejte **TestSettingDistributedTestWalkthrough**.

4.  Zvolte **přidat**.

     Nový test TestSettingDistributedTestWalkthrough.testsettings souboru se zobrazí v Průzkumníku řešení klikněte v části **položky řešení** složky.

     **Nastavení testu** se zobrazí dialogové okno. **Obecné** je vybrány.

     Nyní můžete upravit a uložit testování nastavení hodnoty.

    > [!NOTE]
    > Každý test nastavení, které vytvoříte je uveden jako volba pro **vyberte Active Test nastavení** a **upravit Test nastavení** možnosti na **testování** nabídky.

5.  V části **název**, zadejte název pro nastavení testu.

6.  V části **popis**, typ **nastavení testu distribuované**.

7.  Nechte **výchozí schéma pojmenování** vybrané.

## <a name="to-assign-roles-to-a-test-controller-and-test-agents"></a>K přiřazení rolí pro testovací kontrolery a testovací agenti

1.  Zvolte **role**.

     **Role** zobrazí se stránka.

2.  Chcete-li spustit test vzdáleně, použijte **Test provádění metody** rozevíracího seznamu a vyberte **vzdálené spuštění**.

3.  V **řadič** rozevíracího seznamu, zadejte název počítače [řadiči testovací](../test/lab-management/install-configure-test-agents.md).

    > [!NOTE]
    > Pokud přidáváte řadič poprvé, neexistují žádné řadiče uvedených v rozevíracím seznamu. Naplnění seznamu předchozí řadiče, které jste zadali v jiných nastavení testu.

4.  V části **role**, zvolte **přidat**.

5.  V řádku zvýrazněných v **název** zadejte **distribuované testovací**.

## <a name="to-assign-a-diagnostic-and-data-adapter-to-your-test-setting"></a>Diagnostika a data adaptéru přiřadit vaše nastavení testu

1.  Zvolte **datové a diagnostické**.

     **Datové a diagnostické** zobrazí se stránka.

2.  V části **Role**, ověřte, zda **distribuované testovací** je vybraná role.

3.  V části **dat a diagnostiky pro vyberte roli**, vyberte **IntelliTrace** a **informace o systému** adaptéry.

     Informace o těchto adaptérů a další adaptéry, které můžete použít v nastavení testu najdete v tématu [konfigurace testů jednotek](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).

4.  Zvolte **hostitele**.

5.  (Volitelné) Pokud váš počítač běží na 64bitovou verzi systému Microsoft Windows a zkompilovat testu pomocí **libovolný procesor** konfigurace, použijte **spuštění testu v procesu 32bitová nebo 64bitová verze** rozevíracího seznamu a vyberte **Testy v procesu 64-bit na 64bitový počítač**.

    > [!TIP]
    > Flexibilní, by měl kompilovat testovací projekty s **libovolný procesor** konfigurace. Potom můžete spustit na 32bitové a 64bitové verze agentů. Neexistuje žádné výhody kompilace projektů testů pomocí **64-bit** konfigurace.

6.  Chcete-li uložit nové nastavení testu, zvolte **použít**.

7.  Zvolte **Zavřít**.

8.  V nabídce Test vyberte **vyberte testovací upgrade nastavení Active** a potom zvolte **TestSettingDistributedTestWalkthrough.testsettings**.

9. Spusťte test jako obvykle.

     Když testovací kontroler zpracovává testy částí a programové testy uživatelského rozhraní, testovací kontroler rozděluje testy do skupin 100 a je odešle do testovacího počítače agenta. Například pokud máte 250 testy jednotek a tři testovací agenti, testy částí prvních 100 odešlou do agent1, testy dalších 100 jednotek odešlou do agent2 a zbývající testy jednotek 50 odešlou do agent3.

## <a name="see-also"></a>Viz také

- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)