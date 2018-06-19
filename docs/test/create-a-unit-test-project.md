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
ms.openlocfilehash: d1add4084c856db5a31cf74d75ba848e50e30d3c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31965305"
---
# <a name="create-a-unit-test-project"></a>Vytvoření projektu testů jednotek

Testování částí často zrcadlení struktury kódu v rámci testu. Například by se vytvořily projektu testů jednotek pro každý projekt kódu v rámci produktu. K testovacímu projektu, může být ve stejném řešení jako produkčním kódu, nebo může být v samostatném řešení. Můžete mít víc částí testování projekty v řešení.

> [!NOTE]
> Umístění jednotky testů pro nativní kód a struktura projekt testu může být jiná než strukturu, která je popsaná v tomto tématu. Další informace najdete v tématu [zápis testování částí pro C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="to-create-a-unit-test-project"></a>Vytvoření projektu testování částí:

1.  Na **soubor** nabídce zvolte **nový** a potom zvolte **projektu** (klávesnice Ctrl + Shift + N).

2.  V dialogovém okně Nový projekt rozbalte **nainstalovaná** uzlu, zvolte jazyk, který chcete použít pro projekt test a potom zvolte **testování**.

3.  Chcete-li použít jeden z systémů testování částí Microsoft, zvolte **projektu testování částí** ze seznamu šablon projektu. Jinak zvolte šablonu projektu jednotky test framework, který chcete použít. K testování projektu účty našem příkladu, by název projektu AccountsTests.

4.  Ve vašem projektu testování částí přidáte odkaz na testovaného kódu.  Chcete-li vytvořit odkaz na projekt kódu ve stejném řešení:

    1.  Vyberte projekt v Průzkumníku řešení.

    2.  Na **projektu** nabídky, zvolte **přidat odkaz na...** .

    3.  V dialogovém okně Správce odkazů otevřete **řešení** uzel a zvolte **projekty**. Zkontrolujte název projektu kódu a zavřete dialogové okno.

5.  Pokud kód, který chcete testovat v jiném umístění, zobrazí se [Správa odkazů v projektu](../ide/managing-references-in-a-project.md) informace o přidávání odkazů.

## <a name="next-steps"></a>Další kroky
 **Zápis testů jednotek**

 Najdete v jednom z následujících částí:

-   [Zápis testů částí pro rozhraní .NET Framework s infrastrukturou pro testování částí Microsoft Unit Test Framework pro spravovaný kód](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)

-   [Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)

 **Spouštění testů jednotek**

- [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)