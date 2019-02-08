---
title: Vytvoření projektu testů jednotek
ms.date: 01/29/2019
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 381f04b78e5cfc9ed61187e62e310a2d927eb0ce
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55949431"
---
# <a name="create-a-unit-test-project"></a>Vytvoření projektu testů jednotek

Testy jednotek často zrcadlí struktury kódu v rámci testu. Pro každého kódu projektu v produktu by například vytvořit projekt testování částí. Projekt testů může být ve stejném řešení jako produkční kód nebo může být v samostatném řešení. Můžete mít více jednotek testování projektů v řešení.

> [!NOTE]
> Umístění jednotky testů pro nativní kód a strukturu projektu testu může být jiné než struktury, který je popsaný v tomto článku. Další informace najdete v tématu [zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Chcete-li vytvořit projekt testování částí

1. Na **souboru** nabídce zvolte **nový** a klikněte na tlačítko **projektu**. Také můžete stisknout klávesu **Ctrl**+**Shift**+**N**.

2. V **nový projekt** dialogového okna rozbalte **nainstalováno** uzlu, vyberte jazyk, který chcete použít pro testovací projekt a pak zvolte **testování**.

3. Chcete-li použít jeden z rozhraní pro testování částí Microsoft, zvolte **projekt testů jednotek** ze seznamu šablon projektu. V opačném případě vyberte šablonu projektu jednotky testů, který chcete použít. Pojmenujte projekt a pak vyberte **OK**.

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