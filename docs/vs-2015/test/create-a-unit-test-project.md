---
title: Vytvořit projekt testování částí | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: a608bfba-1a43-4a60-b73a-1fe53ef58098
caps.latest.revision: 10
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f792c29b50be5bbadf34980b81f7c5dd329cccfb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442823"
---
# <a name="create-a-unit-test-project"></a>Vytvoření projektu testování částí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Testy jednotek často zrcadlí struktury kódu v rámci testu. Pro každého kódu projektu v produktu by například vytvořit projekt testování částí. Projekt testů může být ve stejném řešení jako produkční kód nebo může být v samostatném řešení. Můžete mít více jednotek testování projektů v řešení.  
  
> [!NOTE]
> Umístění jednotky testů pro nativní kód a strukturu projektu testu může být jiné než struktury, který je popsaný v tomto tématu. Další informace najdete v tématu [přidání testů jednotek do stávajících aplikací C++](../test/unit-testing-existing-cpp-applications-with-test-explorer.md).  
  
## <a name="to-create-a-unit-test-project"></a>Chcete-li vytvořit projekt testování částí:  
  
1. Na **souboru** nabídce zvolte **nový** a klikněte na tlačítko **projektu** (klávesnice: Ctrl + Shift + N).  
  
2. V dialogovém okně Nový projekt rozbalte **nainstalováno** uzlu, vyberte jazyk, který chcete použít pro testovací projekt a pak zvolte **testování**.  
  
3. Chcete-li použít jeden z rozhraní pro testování částí Microsoft, zvolte **projekt testů jednotek** ze seznamu šablon projektu. V opačném případě vyberte šablonu projektu jednotky testů, který chcete použít. Otestování projektu účty našeho příkladu, by pojmenujte projekt AccountsTests.  
  
4. V projektu testování částí přidejte odkaz na testovaný kód.  Tady je postup pro vytvoření odkazu na projekt kódu ve stejném řešení:  
  
    1. Vyberte projekt v Průzkumníku řešení.  
  
    2. Na **projektu** nabídce zvolte **přidat odkaz...** .  
  
    3. V dialogovém okně Správce odkazů otevřete **řešení** uzlu a zvolte **projekty**. Zkontrolujte název projektu kódu a zavřete dialogové okno.  
  
5. Pokud je kód, který chcete testovat v jiném umístění, přečtěte si téma [Správa odkazů v projektu](../ide/managing-references-in-a-project.md) informace o přidávání odkazů.  
  
## <a name="next-steps"></a>Další kroky  
 **Zápis testů jednotek**  
  
 Přečtěte si následující části:  
  
- [Zápis testů částí pro rozhraní .NET Framework s infrastrukturou pro testování částí Microsoft Unit Test Framework pro spravovaný kód](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)  
  
- [Zápis testů jednotek pro C/C++ s infrastrukturou testování částí Microsoft Unit Testing Framework pro C++](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)  
  
  **Provádění testů jednotek**  
  
  [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)
