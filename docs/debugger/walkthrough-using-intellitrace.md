---
title: "Zobrazení událostí s použitím technologie IntelliTrace | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1c9c91a-0009-4c4e-9b4f-c9ab3a6022a7
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eff33b87d647d28f4af8f452ea4662656a15a61e
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="view-events-with-intellitrace-in-visual-studio"></a>Zobrazení událostí s použitím technologie IntelliTrace v sadě Visual Studio
Můžete shromáždit informace o určité události nebo kategorie události nebo o volání jednotlivých funkcí kromě události IntelliTrace. Následující postupy ukazují, jak to udělat.  
  
 Ve Visual Studio Enterprise edition, ale není edice Professional nebo komunity můžete IntelliTrace.  
  
##  <a name="GettingStarted"></a>Konfigurace Intellitrace  
 Můžete zkusit ladění pomocí právě události IntelliTrace. Události IntelliTrace jsou události ladicí program, výjimky, rozhraní .NET Framework události a dalších událostí systému. Měli zapnout nebo vypnout určité události řídit události tohoto IntelliTrace záznamy před zahájením ladění. Další informace najdete v tématu [funkce IntelliTrace](../debugger/intellitrace-features.md).  
  
 - Zapněte události IntelliTrace pro přístup k souborům. Přejděte na **nástroje > Možnosti > IntelliTrace > události IntelliTrace** stránky a rozbalte **souboru** kategorie. Zkontrolujte **souboru** kategorie události. To způsobí, že všechny souboru události (Zavřít, přístup, odstraňte) ke kontrole.

## <a name="create-your-app"></a>Vytvoření aplikace
  
1.  Vytvořte konzolovou aplikaci C#. V souboru Program.cs přidejte následující `using` příkaz:  
  
    ```CSharp  
    using System.IO;  
    ```  
  
2.  Vytvoření <xref:System.IO.FileStream> v metodu Main, čtení z něj, zavřete je a odstranit soubor. Přidáte další čáru právě do mají místo, kde můžete nastavit zarážky:  
  
    ```CSharp  
    static void Main(string[] args)  
    {  
        FileStream fs = File.Create("WordSearchInputs.txt");  
        fs.ReadByte();  
        fs.Close();  
        File.Delete("WordSearchInputs.txt");  
  
        Console.WriteLine("done");  
    }  
    ```  
  
3.  Nastavit zarážky`Console.WriteLine("done");`  

## <a name="start-debugging-and-view-intellitrace-events"></a>Spuštění ladění a zobrazit události IntelliTrace
  
1.  Spusťte ladění jako obvykle. (Stisknutím klávesy **F5** nebo klikněte na tlačítko **ladění > Spustit ladění**.  
  
    > [!TIP]
    >  Zachovat **místní hodnoty –** a **automobily** windows otevřete při ladění najdete v článku a záznam hodnoty v těchto windows.  
  
2.  Provádění zastaví u zarážky. Pokud se nezobrazí **diagnostické nástroje** okně klikněte na tlačítko **ladění > Windows > události IntelliTrace**.  
  
     V **diagnostické nástroje** okno, Najít **události** karta (karty 3, byste měli vidět **události**, **využití paměti**, a **procesoru Využití**). **Události** kartě se zobrazují chronologickém seznam událostí, s poslední událost před překročila spuštění ladicího programu. Měli byste vidět událost s názvem **přístup WordSearchInputs.txt**.  
  
     Na následujícím snímku obrazovky je z Visual Studia 2015 Update 1.  
  
     ![IntelliTrace & č. 45; Aktualizaci1](../debugger/media/intellitrace-update1.png "aktualizaci1 IntelliTrace")  
  
3.  Vyberte událost rozbalíte podrobnosti.  
  
     Na následujícím snímku obrazovky je z Visual Studia 2015 Update 1.  
  
     ![IntelliTraceUpdate1 & č. 45; SingleEvent](../debugger/media/intellitraceupdate1-singleevent.png "IntelliTraceUpdate1 SingleEvent")  
  
     Můžete zvolit pathname odkazu k otevření souboru. Pokud není k dispozici, úplná cesta **otevření souboru** zobrazí se dialogové okno.  
  
     Klikněte na tlačítko **aktivovat historické ladění**, který nastaví kontextu ladicího programu na čas, kdy byla vybrané události shromážděné, historická data zobrazují v **zásobníkem volání**, **místní hodnoty –** a dalších zúčastněných ladicího programu systému windows. Zdrojový kód je k dispozici, přesune Visual Studio ukazatele odpovídající kód v okně zdroj, můžete ho zkontrolovat.  
  
     Na následujícím snímku obrazovky je z Visual Studia 2015 Update 1.  
  
     ![HistoricalDebugging & č. 45; Aktualizaci1](../debugger/media/historicaldebugging-update1.png "HistoricalDebugging aktualizaci1")  
  
4.  Pokud nebyl nalezen chybě, zkuste zkoumání jiné události vedoucí k chybě. Může také mít informace o záznamu volání IntelliTrace, takže můžete krokovat volání funkcí. 
  
## <a name="next-steps"></a>Další kroky

Můžete používat některé z pokročilých funkcí IntelliTrace s historické ladění:

 - Snímky najdete v tématu [zobrazit snímky pomocí zpětný krok IntelliTrace](../debugger/how-to-use-intellitrace-step-back.md)
 - Zjistěte, jak zkontrolovat proměnné a přejděte kód, najdete v tématu [zkontrolovat vaší aplikace pomocí historické ladění](../debugger/historical-debugging-inspect-app.md)