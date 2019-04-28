---
title: Vytvoření projektu testů jednotek
ms.date: 01/29/2019
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: ca83689628f02a8c7a2e0166b390d5b277086c1d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62965528"
---
# <a name="create-a-unit-test-project"></a>Vytvoření projektu testů jednotek

Testy jednotek často zrcadlí struktury kódu v rámci testu. Pro každého kódu projektu v produktu by například vytvořit projekt testování částí. Projekt testů může být ve stejném řešení jako produkční kód nebo může být v samostatném řešení. Můžete mít více jednotek testování projektů v řešení.

> [!NOTE]
> Umístění jednotky testů pro nativní kód a strukturu projektu testu může být jiné než struktury, který je popsaný v tomto článku. Další informace najdete v tématu [zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Chcete-li vytvořit projekt testování částí

1. Na **souboru** nabídce zvolte **nový** > **projektu**, nebo stiskněte klávesu **Ctrl**+**Shift** + **N**.

::: moniker range="vs-2017"

2. V **nový projekt** dialogového okna rozbalte **nainstalováno** uzlu, vyberte jazyk, který chcete použít pro testovací projekt a pak zvolte **testování**.

3. Chcete-li použít jeden z rozhraní pro testování částí Microsoft, zvolte **projekt testů jednotek** ze seznamu šablon projektu. V opačném případě vyberte šablonu projektu jednotky testů, který chcete použít. Pojmenujte projekt a pak vyberte **OK**.

::: moniker-end

::: moniker range=">=vs-2019"

2. Na **vytvořte nový projekt** zadejte **Jednotkový test** do vyhledávacího pole. Vyberte **projekt testu jednotek (.NET Framework)** šablony projektu a pak klikněte na tlačítko **Další**.

3. Na **konfigurovat nový projekt** stránky, zadejte název pro váš projekt a potom klikněte na tlačítko **vytvořit**.

::: moniker-end

4. V projektu testování částí přidejte odkaz na testovaný kód. Přidání odkazu do projektu kódu ve stejném řešení:

   1. Vyberte projekt testu v **Průzkumníka řešení**.

   2. Na **projektu** nabídce zvolte **přidat odkaz**.

   3. V **správce odkazů**, vyberte **řešení** pod uzlem **projekty**. Vyberte projekt kódu, který chcete testovat a pak vyberte **OK**.

   Pokud je kód, který chcete testovat v jiném umístění, přečtěte si téma [Správa odkazů v projektu](../ide/managing-references-in-a-project.md) informace o přidání odkazu.

## <a name="next-steps"></a>Další kroky

Přečtěte si následující části:

**Zápis testů jednotek**

- [Testování částí kódu](../test/unit-test-your-code.md)

- [Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)

- [Použití rozhraní MSTest při testech jednotek](using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md)

**Provádění testů jednotek**

- [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)