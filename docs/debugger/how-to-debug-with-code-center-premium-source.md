---
title: 'Postupy: ladění se zdrojem webu Code Center Premium | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Code Center Premium
- debugging [Visual Studio], Code Center Premium
ms.assetid: 18b4769d-b007-4428-9dae-9e72c283ff0d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ef757e71f557febab74f4575635993cf77214250
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-with-code-center-premium-source"></a>Postupy: Ladění se zdrojem webu Code Center Premium
Pomocí [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] ladicí program, můžete ladit zabezpečené sdílené zdroje z Microsoft MSDN Code Center Premium.  
  
 Toto téma vysvětluje, jak nastavit a ladění kódu Center Premium zdrojového kódu v sadě Visual Studio.  
  
### <a name="to-prepare-for-debugging-with-code-center-premium"></a>Příprava na ladění pomocí Code Center Premium  
  
1.  Připojte čtečky čipových karet a vložení karty, které jste získali v iniciativy sdílené zdroje.  
  
2.  Spusťte sadu Visual Studio.  
  
3.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
4.  V **možnosti** dialogové okno, otevřete **ladění** uzel a klikněte na tlačítko **Obecné**.  
  
5.  Vymazat **povolit volbu pouze vlastní kód (pouze spravované)** zaškrtávací políčko.  
  
6.  Vyberte **povolit povolit zdrojový Server podporu**.  
  
7.  Zrušte **vyžadují zdrojové soubory tak, aby přesně shodu původní verze**.  
  
8.  V části **ladění** uzel, klikněte na tlačítko **symboly**.  
  
9. V **souboru symbolu (.pdb) umístění** pole, zrušte **symboly serveru Microsoft** zaškrtněte políčko a přidejte následující umístění:  
  
     `https://codepremium.msdn.microsoft.com/symbols`  
  
     `src=https://codepremium.msdn.microsoft.com/source/Visual%20Studio%202010/SP1/`  
  
    > [!NOTE]
    >  Nezapomeňte zahrnout do adresy koncové lomítko**/** na konci cesty.  
  
     Přesunete na začátek seznamu a ujistěte se, že tyto symboly jsou načtená nejprve těchto umístění.  
  
    > [!NOTE]
    >  Tato umístění Code Center Premium, musí být uvedené nejdříve, aby byly první umístění, které jsou načteny. V sadě Visual Studio 2010, nemůžete přesunout všechny výše uvedené servery **servery symbolů Microsoft** položku, která je proto nutné zrušit zaškrtnutí políčka.  
    >   
    >  Chcete-li načíst symboly z symboly Microsoft během relace ladění, postupujte takto:  
    >   
    >  1.  Na **ladění** nabídce zvolte **Windows** a potom zvolte **moduly**.  
    > 2.  Vyberte modul, který chcete symboly pro a pak otevřete místní nabídky. Zvolte **zatížení symboly z** a potom zvolte **servery symbolů Microsoft**.  
  
10. V **mezipaměti symboly ze serverů symbol v tomto adresáři** zadejte umístění, jako `C:\symbols` kde Code Center Premium můžete mezipaměti symboly. Ukládání do mezipaměti symboly může výrazně zlepšit výkon během ladění.  
  
     Pokud máte potíže při ladění zdrojového kódu s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] po dokončení tohoto postupu zkontrolujte vaší mezipaměti umístění pro soubory symbolů dříve uloženou v mezipaměti a zastaralé. Odeberte soubory zastaralé symbolů.  
  
11. Click **OK**.  
  
12. Restartujte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zajistit, že nastavení jsou nastavené jako trvalé.  
  
### <a name="to-debug-your-source-code-using-attach-to-process"></a>Chcete-li ladit vašeho zdrojového kódu pomocí připojit k procesu  
  
1.  Připojte čtečky čipových karet a vložení karty, které jste získali v iniciativy sdílené zdroje.  
  
2.  Spusťte sadu Visual Studio.  
  
3.  Otevřete projekt sady Visual Studio.  
  
4.  Na **nástroje** nabídky, klikněte na tlačítko **připojit k procesu**.  
  
5.  V **připojit k procesu** dialogové okno, klikněte na tlačítko **vyberte**.  
  
6.  V **vybrat typ kódu** dialogovém **rozpoznávání těchto typů kódu**, vyberte **nativní**, **spravované**, a **spravované () V4.0)**.  
  
7.  Klikněte na tlačítko **OK** pro zavření **vybrat typ kódu** dialogové okno.  
  
8.  V **dostupné procesy** vyberte procesu, kterou chcete ladit.  
  
9. Klikněte na tlačítko **připojit**.  
  
10. Po zobrazení výzvy potvrďte svůj certifikát, klikněte na tlačítko **OK**. Zadejte svůj PIN kód. Přijměte podmínky použití pro Code Center Premium, pokud se zobrazí výzva.  
  
     Stahování symboly může trvat poměrně dlouho, v závislosti na rychlosti sítě. Stavový řádek bude signalizují, že byly úspěšně staženy všechny symboly.  
  
11. Opakujte kroky připojení pro všechny spravované projekty v řešení.  
  
### <a name="to-debug-source-code-from-an-existing-solution"></a>Chcete-li ladit zdrojového kódu z existujícího řešení  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro řešení a zvolte **vlastnosti**.  
  
2.  V dialogovém okně stránky vlastností řešení zvolte **zdrojové soubory ladění** v **společných vlastností** uzlu.  
  
3.  Přidat do následujícího umístění **adresáře, který obsahuje zdrojové soubory** seznamu:  
  
     `https://codepremium.msdn.microsoft.com/source/Visual%20Studio%202010/SP1/`  
  
    > [!NOTE]
    >  Nezapomeňte zahrnout do adresy koncové lomítko**/** na konci cesty.  
  
4.  Pro každý spravovaný projekt ve vašem řešení proveďte následující  
  
    1.  V Průzkumníku řešení otevřete místní nabídky projektu a zvolte **vlastnosti**.  
  
    2.  Vyberte **ladění** a potom zvolte **povolit ladění nespravovaného kódu**.  
  
### <a name="to-debug-your-solution-with-code-center-premium-source"></a>K ladění řešení se zdrojem webu Code Center Premium  
  
1.  Ve vašem `Package` třídy, nastavte zarážky v konstruktoru balíčku.  
  
2.  V `Debug` nabídky, klikněte na tlačítko **spustit ladění**.  
  
3.  Při kliknutí na zarážka v konstruktoru balíčku, přejděte na **zásobníkem volání** okno a klikněte pravým tlačítkem na rámec zásobníku sestavení, které chcete zatížení symboly, pak klikněte na tlačítko **načíst symboly**.  
  
     Dvakrát klikněte na rámce volání načtení zdroje.  
  
### <a name="to-browse-source-code-on-code-center-premium"></a>Chcete-li procházet zdrojový kód v Code Center Premium  
  
1.  Připojte čtečky čipových karet a vložení karty, které jste získali v iniciativy sdílené zdroje.  
  
2.  Spusťte Internet Exploreru zadejte následující adresu URL: `https://codepremium.msdn.microsoft.com`  
  
3.  Procházet a najít požadovaný zdroj.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Code Center Premium](http://www.microsoft.com/resources/sharedsource/ccp.mspx)