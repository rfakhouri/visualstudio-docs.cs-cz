---
title: Použití architektury Microsoft pro testování jednotek pro jazyk C++
ms.date: 06/13/2019
ms.topic: conceptual
ms.author: mblome
manager: markl
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: fd5780479da10da43c270bbf4ffc5a215cb86ad6
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926692"
---
# <a name="use-the-microsoft-unit-testing-framework-for-c-in-visual-studio"></a>Použít Microsoft rozhraní testování části pro C++ v sadě Visual Studio

Ve výchozím nastavení je zahrnuto Microsoft Unit Testing Framework pro C++ **Desktop Development with C++** pracovního vytížení.

## <a name="separate_project"></a> Pro psaní jednotkových testů testovacího projektu

Obvykle spustíte testovací kód ve svém vlastním projektu ve stejném řešení jako kód, který chcete testovat. Chcete-li vytvořit a nakonfigurovat nový testovací projekt, naleznete v tématu [zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md).

## <a name="same_project"></a> Pro psaní jednotkových testů do stejného projektu

V některých případech, například při testování neexportovaných funkcí v knihovně DLL, může být nutné vytvořit testy ve stejném projektu jako program, který testujete. Pro psaní jednotkových testů do stejného projektu:

1. Upravte vlastnosti projektu, aby zahrnovaly hlavičkové soubory a soubory knihoven, které jsou požadovány pro testování částí.

   1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu pro testování programu a pak zvolte **vlastnosti** > **vlastnosti konfigurace**  >  **Adresáře VC ++** .

   2. Klikněte na šipku dolů v následujících řádcích a vyberte možnost  **\<Upravit >** . Přidejte tyto cesty:

      | Adresář | Vlastnost |
      |-| - |
      | **Adresáře souborů k zahrnutí** | **$ (VCInstallDir) Auxiliary\VS\UnitTest\include** |
      | **Adresáře knihoven** | **$ (VCInstallDir) Auxiliary\VS\UnitTest\lib** |

2. Přidáte soubor testu jednotek C++:

   - V **Průzkumník řešení** klikněte pravým tlačítkem myši na uzel projektu a vyberte možnost **Přidat** > **nový soubor položky**  >   **C++ (. cpp)** .

## <a name="write-the-tests"></a>Zápis testů

Žádné *.cpp* soubor s testovacích tříd musí obsahovat "CppUnitTest.h" a obsahovat using příkazu pro `using namespace Microsoft::VisualStudio::CppUnitTestFramework`. Projekt testů už je nakonfigurovaný pro vás. Zahrnuje také definice oboru názvů a TEST_CLASS s TEST_METHOD, které vám pomůžou začít. Můžete upravit název oboru názvů, jakož i názvy v závorkách v makrech třídy a metody.

Speciální makra jsou definována pro inicializaci testovacích modulů, tříd a metod a pro vyčištění prostředků po dokončení testů. Tato makra generovat kód, který je proveden před třídy nebo metody, je nejprve otevřen a po provedení posledního testu. Další informace najdete v tématu [inicializace a vyčištění](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#Initialize_and_cleanup).

Používají statické metody v [Assert](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#general_asserts) třídy definovat podmínky testu. Použití [protokolovací nástroj](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#logger) třídu pro zápis zpráv do **okno výstup**. Přidat atributy s testovacími metodami

## <a name="run-the-tests"></a>Spustit testy

1. Na **testovací** nabídce zvolte **Windows** > **Průzkumník testů**.

1. Pokud všechny testy nejsou zobrazeny v okně, vytvoření testovacího projektu kliknutím pravým tlačítkem myši v jeho uzel **Průzkumníka řešení** a zvolíte **sestavení** nebo **znovu sestavit**.

1. V **Průzkumník testů**, zvolte **spustit všechny**, nebo vyberte konkrétní testy, které chcete spustit. Klikněte pravým tlačítkem myši na test pro další možnosti, včetně spuštění v režimu ladění se zarážkami povolené.

1. V **okno výstup** zvolte **testy** v rozevíracího seznamu ji můžete zapsat pomocí zobrazení zpráv `Logger` třídy:

   ![Okno výstup C++ zkušební zprávy](media/cpp-test-output-window.png)

## <a name="define-traits-to-enable-grouping"></a>Definovat vlastnosti, které chcete povolit seskupování

Můžete definovat vlastnosti pro testovací metody, které vám umožní kategorizaci a seskupte testy v **Průzkumníka testů**. Chcete-li definovat vlastnost, použijte `TEST_METHOD_ATTRIBUTE` – makro. Například pro definici znaku s názvem `TEST_MY_TRAIT`:

```cpp
#define TEST_MY_TRAIT(traitValue) TEST_METHOD_ATTRIBUTE(L"MyTrait", traitValue)
```

Použití definované vlastnosti v testech jednotek:

```cpp
BEGIN_TEST_METHOD_ATTRIBUTE(Method1)
    TEST_OWNER(L"OwnerName")
    TEST_PRIORITY(1)
    TEST_MY_TRAIT(L"thisTraitValue")
END_TEST_METHOD_ATTRIBUTE()

TEST_METHOD(Method1)
{
    Logger::WriteMessage("In Method1");
    Assert::AreEqual(0, 0);
}
```

### <a name="c-trait-attribute-macros"></a>Atributy a makra C++ vlastností

Následující předdefinované vlastnosti se nacházejí v `CppUnitTest.h`. Další informace najdete v tématu [Microsoft Unit Testing Framework pro reference k rozhraní API C++](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md).

|– Makro|Popis|
|-|-----------------|
|`TEST_METHOD_ATTRIBUTE(attributeName, attributeValue)`|Chcete-li definovat vlastnost, použijte makro TEST_METHOD_ATTRIBUTE.|
|`TEST_OWNER(ownerAlias)`|Použijte předdefinovanou vlastnost Owner k zadání vlastníka testovací metody.|
|`TEST_PRIORITY(priority)`|Pomocí předdefinované vlastnosti Priority přiřaďte relativní priority testovacím metodám.|

## <a name="see-also"></a>Viz také:

- [Rychlý start: Vývoj řízených testů pomocí Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)
