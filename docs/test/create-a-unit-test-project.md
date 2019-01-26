---
title: Vytvoření projektu testů jednotek
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: e90aa1f8fe13bc7ee99f3ac20b1813ca2a6c9672
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996811"
---
# <a name="create-a-unit-test-project"></a>Vytvoření projektu testů jednotek

Testy jednotek často zrcadlí struktury kódu v rámci testu. Pro každého kódu projektu v produktu by například vytvořit projekt testování částí. Projekt testů může být ve stejném řešení jako produkční kód nebo může být v samostatném řešení. Můžete mít více jednotek testování projektů v řešení.

> [!NOTE]
> Umístění jednotky testů pro nativní kód a strukturu projektu testu může být jiné než struktury, který je popsaný v tomto tématu. Další informace najdete v tématu [zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Chcete-li vytvořit projekt testování částí:

1.  Na **souboru** nabídce zvolte **nový** a klikněte na tlačítko **projektu** (klávesnice **Ctrl**+**Shift** + **N**).

2.  V **nový projekt** dialogového okna rozbalte **nainstalováno** uzlu, vyberte jazyk, který chcete použít pro testovací projekt a pak zvolte **testování**.

3.  Chcete-li použít jeden z rozhraní pro testování částí Microsoft, zvolte **projekt testů jednotek** ze seznamu šablon projektu. V opačném případě vyberte šablonu projektu jednotky testů, který chcete použít. Otestování projektu účty našeho příkladu, bude název projektu **AccountsTests**.

4.  V projektu testování částí přidejte odkaz na testovaný kód.  Tady je postup pro vytvoření odkazu na projekt kódu ve stejném řešení:

    1.  Vyberte projekt v **Průzkumníka řešení**.

    2.  Na **projektu** nabídce zvolte **přidat odkaz**.

    3.  V **správce odkazů** dialogovém okně Otevřít **řešení** uzlu a zvolte **projekty**. Zkontrolujte název projektu kódu a zavřete dialogové okno.

5.  Pokud je kód, který chcete testovat v jiném umístění, přečtěte si téma [Správa odkazů v projektu](../ide/managing-references-in-a-project.md) informace o přidávání odkazů.

## <a name="next-steps"></a>Další kroky

 Přečtěte si následující části:

**Zápis testů jednotek**

- [Testování částí kódu](../test/unit-test-your-code.md)

- [Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)

- [Použití rozhraní MSTest při testech jednotek](using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md)

**Provádění testů jednotek**

- [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)