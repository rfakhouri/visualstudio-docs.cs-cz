---
title: "Vytvoření projektu testování částí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a608bfba-1a43-4a60-b73a-1fe53ef58098
caps.latest.revision: "8"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 6294bd85d3a0fe189f0beff5c8a8a91294bd6b1d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="create-a-unit-test-project"></a>Vytvoření projektu testů jednotek
Testování částí často zrcadlení struktury kódu v rámci testu. Například by se vytvořily projektu testů jednotek pro každý projekt kódu v rámci produktu. K testovacímu projektu, může být ve stejném řešení jako produkčním kódu, nebo může být v samostatném řešení. Můžete mít víc částí testování projekty v řešení.  
  
> [!NOTE]
>  Umístění jednotky testů pro nativní kód a struktura projekt testu může být jiná než strukturu, která je popsaná v tomto tématu. Další informace najdete v tématu [zápis testování částí pro C/C++](writing-unit-tests-for-c-cpp.md).  
  
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
  
 [Spouštění testování částí pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md)
