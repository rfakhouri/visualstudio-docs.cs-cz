---
title: "Instalace systémů testů jednotek třetích stran | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c0cd7853c65d5501213076cb7ccb533c5134c9f4
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="install-third-party-unit-test-frameworks"></a>Instalace systémů testů jednotek od třetích stran
Testování Průzkumníka Visual Studio můžete spustit test rozhraní, které vyvinula adaptéru rozhraní pro aplikaci Explorer žádné jednotky. Instalační program rozhraní Framework nainstalují binární soubory a přidá šablony projektů Visual Studio pro jazyky, které podporuje. Když vytvoříte pomocí šablony projektu, rozhraní je zaregistrován pomocí Průzkumníka testů. Řešení sady Visual Studio může obsahovat projektů testů jednotek, které používají různé architektury a které se budou zaměřovat na různé jazyky. Průzkumníka testů spouští je všechny.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise, Visual Studio Professional  
  
## <a name="acquiring-third-party-frameworks"></a>Získání rozhraní třetích stran  
 Můžete stáhnout a nainstalovat mnoha systémů testů jednotek třetích stran, pomocí Správce rozšíření Visual Studio nebo Visual Studio Marketplace. Rozhraní můžete také stáhnout z jiných webů, jako je například web rozhraní.  
  
### <a name="installing-from-visual-studio"></a>Instalace ze sady Visual Studio  
  
1.  Zvolte **nástroje** v nabídce standardní a potom zvolte **rozšíření a aktualizace**.  
  
2.  Rozbalte položku **Online**, **sady Visual Studio Marketplace**, **nástroje**. Zvolte **testování**.  
  
3.  Procházejte seznamem a najděte rozhraní.  
  
4.  Vyberte rozhraní a zvolte **Stáhnout**.  
  
 Další informace najdete v části [hledání a používání rozšíření Visual Studia](../ide/finding-and-using-visual-studio-extensions.md).  
  
### <a name="installing-from-the-web"></a>Instalace z webu  
 Pokud znáte rozhraní, které vás zajímají:  
  
1.  Otevřete [sady Visual Studio Marketplace](https://marketplace.visualstudio.com/vs).  
  
2.  Zadejte název rozhraní v **najít** pole.  
  
3.  Vyberte v seznamu výsledků přejít na stránku Visual Studio Marketplace pro nástroj rozhraní.  
  
 Chcete-li procházet seznam architektury spolu s ostatními nástroji pro testování:  
  
1.  Otevřete [sady Visual Studio Marketplace](https://marketplace.visualstudio.com/vs).  
  
2.  V **filtrovat podle kategorie nebo kolekce**, zvolte **zobrazit všechny**.  
  
3.  V **kategorie** seznamu (označené jako **zobrazující**), rozbalte **nástroje** uzel a potom zvolte **testování**.  
  
4.  Zvolte rozhraní v seznamu výsledků přejít na stránku Visual Studio Marketplace pro nástroj. 

## <a name="update-to-the-latest-test-adapters"></a>Aktualizovat na nejnovější adaptéry testu

Aktualizace na nejnovější stabilní testovací adaptér, který má lepší prostředí otestovat zjišťování a spouštění. Další informace o aktualizacích Mstestu, NUnit a xUnit testovací adaptéry, najdete v článku [blog Visual Studio](https://blogs.msdn.microsoft.com/visualstudio/2017/11/16/test-experience-improvements/).

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>Aktualizace na verzi adaptér nejnovější stabilní testu

1. Otevřete Správce balíčků Nuget pro řešení přechodem na **nástroje > Správce balíčků NuGet > Správa balíčků NuGet pro řešení...**

2. Klikněte na **aktualizace** kartě a vyhledejte NUnit nebo xUnit testovací adaptéry, které jsou nainstalovány.

3. Vyberte každý adaptér testu a pak v rozevírací nabídce vyberte nejnovější stabilní verze.

4. Vyberte **nainstalovat** tlačítko.

![Testování upgradu adaptéru](media/installadapter-upgrade.png)

## <a name="see-also"></a>Viz také

- [Testování částí kódu](../test/unit-test-your-code.md)
