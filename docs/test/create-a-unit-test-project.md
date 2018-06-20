---
title: Vytvoření projektu testů jednotek v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3dc86281542dbedd429fae5f9976219bfa623878
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36235047"
---
# <a name="create-a-unit-test-project"></a>Vytvoření projektu testů jednotek

Testování částí často zrcadlení struktury kódu v rámci testu. Například by se vytvořily projektu testů jednotek pro každý projekt kódu v rámci produktu. K testovacímu projektu, může být ve stejném řešení jako produkčním kódu, nebo může být v samostatném řešení. Můžete mít víc částí testování projekty v řešení.

> [!NOTE]
> Umístění jednotky testů pro nativní kód a struktura projekt testu může být jiná než strukturu, která je popsaná v tomto tématu. Další informace najdete v tématu [zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Vytvoření projektu testování částí:

1.  Na **soubor** nabídce zvolte **nový** a potom zvolte **projektu** (klávesnice **Ctrl**+**Shift** + **N**).

2.  V **nový projekt** dialogové okno, rozbalte seznam **nainstalovaná** uzlu, zvolte jazyk, který chcete použít pro projekt test a potom zvolte **testování**.

3.  Chcete-li použít jeden z systémů testování částí Microsoft, zvolte **projektu testování částí** ze seznamu šablon projektu. Jinak zvolte šablonu projektu jednotky test framework, který chcete použít. K testování projektu účty našem příkladu, by název projektu **AccountsTests**.

4.  Ve vašem projektu testování částí přidáte odkaz na testovaného kódu.  Chcete-li vytvořit odkaz na projekt kódu ve stejném řešení:

    1.  Vyberte projekt v **Průzkumníku řešení**.

    2.  Na **projektu** nabídky, zvolte **přidat odkaz na**.

    3.  V **správce odkazů** dialogové okno, otevřete **řešení** uzel a zvolte **projekty**. Zkontrolujte název projektu kódu a zavřete dialogové okno.

5.  Pokud kód, který chcete testovat v jiném umístění, zobrazí se [Správa odkazů v projektu](../ide/managing-references-in-a-project.md) informace o přidávání odkazů.

## <a name="next-steps"></a>Další kroky
 **Zápis testů jednotek**

 Najdete v jednom z následujících částí:

-   [Testování částí kódu](../test/unit-test-your-code.md)

-   [Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)

-   [Použití Mstestu framework při testech jednotek](using-microsoft-visualstudio-testtools-unittesting-members-in-unit-tests.md)

 **Spouštění testů jednotek**

- [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)