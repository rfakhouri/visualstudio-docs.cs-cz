---
title: Zkontrolujte vaší aplikace pomocí historické ladění | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 629b5d93-39b2-430a-b8ba-d2a47fdf2584
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d6a8e4ec27c73516d2eb4ea79ee8beee91dfd19c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="inspect-your-app-with-intellitrace-historical-debugging-in-visual-studio"></a>Zkontrolujte vaše aplikace s použitím technologie IntelliTrace historické ladění v sadě Visual Studio
Můžete použít [historické ladění](../debugger/historical-debugging.md) přesunout zpátky a předávat prostřednictvím spuštění vaší aplikace a zkontrolovat stav.  
  
Ve Visual Studio Enterprise edition, ale není edice Professional nebo komunity můžete IntelliTrace.  
  
## <a name="navigate-your-code-with-historical-debugging"></a>Procházení kódu s historické ladění  
 Začněme jednoduchý program, který obsahuje chyby. V jazyce C# konzolovou aplikaci přidejte následující kód:  
  
```csharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    int resultInt = AddAll(testInt);  
    Console.WriteLine(resultInt);  
}  
private static int AddAll(int j)  
{  
    for (int i = 0; i < 20; i++)  
    {  
        j = AddInt(j);  
    }  
    return j;  
}  
  
private static int AddInt(int add)  
{  
    if (add == 10)  
    {  
        return add += 25;  
    }  
    return ++add;  
}  
```  
  
 Budeme předpokládat, s očekávanou hodnotou `resultInt` po volání `AddAll()` je 20 (výsledek zvyšování `testInt` 20krát). (Budete také předpokládáme, že nemůžete zobrazit chyby v `AddInt()`). Ale výsledkem je ve skutečnosti 44. Jak jsme najdete chyb bez procházení `AddAll()` 10krát? Historické ladění budeme můžete použít k vyhledání chybě snadnější a rychlejší. Tady je jak:  
  
1.  V **nástroje > Možnosti > IntelliTrace > Obecné**, ujistěte se, zda je povoleno IntelliTrace a vyberte **události IntelliTrace a volání informace**. Pokud tuto možnost nevyberete, nebudete moci zobrazit navigační mezera (jak je popsáno níže).  
  
2.  Nastavit zarážky `Console.WriteLine(resultInt);` řádku.  
  
3.  Spusťte ladění. Spustí kód na zarážku. V **místní hodnoty –** okně uvidíte, že hodnota `resultInt` je 44.  
  
4.  Otevřete **diagnostické nástroje** okno (**ladění > zobrazit diagnostické nástroje**). V okně Kód by měl vypadat takto:  
  
     ![Okno kódu u zarážky](../debugger/media/historicaldebuggingbreakpoint.png "HistoricalDebuggingBreakpoint")  
  
5.  Měli byste vidět na dvojitou šipku vedle levým okrajem, nad zarážku. Tato oblast se nazývá navigační mezera a slouží pro historické ladění. Klikněte na šipku.  
  
     V okně Kód by měl uvidíte, že předchozí řádek kódu (`int resultInt = AddIterative(testInt);`) je barevný růžový. Výše okna měli byste vidět zprávu, která jste v historické ladění.  
  
     V okně kód nyní vypadat třeba takto:  
  
     ![okno kódu v režimu historické ladění](../debugger/media/historicaldebuggingback.png "HistoricalDebuggingBack")  
  
6.  Teď můžete krok do `AddAll()` – metoda (**F11**, nebo **Krokovat s vnořením** tlačítka na navigační mezera. Krok dál (**F10**, nebo **přejít na další volání** v navigační mezera. Růžová čára je teď na `j = AddInt(j);` řádku. **F10** v takovém případě není krok na další řádek kódu. Místo toho kroky pro další volání funkce. Historické ladění přejde z volání volání a vynechává řádků kódu, které neobsahují volání funkce.  
  
7.  Teď krok do `AddInt()` metoda. Chyby v tento kód byste měli vidět okamžitě.  

## <a name="next-steps"></a>Další kroky

Tento postup právě poškrábání prostor co můžete dělat s historické ladění.

- Snímky při ladění naleznete v tématu [zobrazit snímky IntelliTrace zpětným krok pomocí](../debugger/how-to-use-intellitrace-step-back.md).
- Další informace o různých nastavení a účinky různých tlačítka v navigační mezera, najdete v tématu [funkce IntelliTrace](../debugger/intellitrace-features.md).