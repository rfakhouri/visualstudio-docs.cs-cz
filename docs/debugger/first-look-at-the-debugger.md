---
title: Začínáme s ladicím programem v sadě Visual Studio | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 02/07/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: get-started-article
ms.assetid: 0b3138c4-b840-446a-a15c-10ed8e2dd050
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 171b07d453c81883354848f70458bab39daa313e
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/29/2018
---
# <a name="get-started-with-the-visual-studio-debugger"></a>Začínáme s ladicím programu sady Visual Studio
Ladicí program Visual Studio je snadno použitelný v libovolném jazyce. Zde ukážeme postup ladění jednoduché programu v C#, ale můžete použít stejný postup na kód v jiných jazycích, jako je například C++ a JavaScript.

Pokud chcete přehrát video, zobrazující podobné funkce, najdete v části [Začínáme s ladicím programem](https://www.youtube.com/watch?v=FtGCi5j30YU&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=6).
  
##  <a name="BKMK_Start_debugging_a_VS_project"></a> Ladění projektu pro základní C#  
 Začněme s jednoduchou aplikaci konzoly C# (**soubor > Nový > projekt**, pak vyberte **Visual C#** a potom **konzolové aplikace**). Pokud jste nikdy práce pomocí sady Visual Studio před, přečtěte si téma [návod: vytvoření jednoduché aplikace](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md). **Hlavní** metoda právě přidá 1 do proměnná typu integer 10krát a vytiskne výsledek do konzoly:  
  
```csharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    for (int i = 1; i <= 10; i++)  
    {  
        testInt += 1;  
    }  
    Console.WriteLine(testInt);  
}  
```  
  
 Sestavení tento kód **ladění** konfigurace. Tato konfigurace je ve výchozím nastavení. Další informace o konfiguracích najdete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).  
  
 Spustit tento kód v ladicím programu kliknutím **ladění > Spustit ladění** (nebo **spustit** na panelu nástrojů nebo **F5**). Aplikace by měl téměř okamžitě ukončena, nelze ve skutečnosti zjistit, zda byl nic vytištěn v okně konzoly.  
  
 Zastavit provádění můžete dostatečně dlouho budou zobrazovat v okně konzoly nastavení boru přerušení a pak můžete některé krokování s. K nastavení boru přerušení, umístěte kurzor `Console.WriteLine` řádku a klikněte na tlačítko **ladění > nové zarážek > funkce zarážek**, nebo stačí kliknout na levém okraji na stejném řádku. Zarážce by měl vypadat takto:  
  
 ![Nastavit zarážky](../debugger/media/getstartedbreakpoint.png "GetStartedBreakpoint")  
  
 Další informace o zarážkách najdete v tématu [pomocí zarážek](../debugger/using-breakpoints.md).  
  
##  <a name="BKMK_Inspect_Variables"></a> Zkontrolujte proměnné  
 Ladění často zahrnuje hledání proměnné, které neobsahují hodnoty, které očekáváte, že na určitém místě. Ukážeme některé způsoby, si můžete prohlédnout proměnné.  
  
 Ladění spusťte znovu. Spuštění zastaví před `Console.WriteLine` kód spustí. Může být spuštěna pomocí procházení dopředu způsobit (klikněte na tlačítko **ladění > Krokovat s přeskočením** nebo **F10**). V takovém případě může zvolili jste **Krokovat s vnořením** (**F11**) a že podmínky stejného výsledku; vysvětlíme rozdíl později. Řádek s poslední složené závorky metody by měla mít zapnuta žlutý. Podívejte se na v okně konzoly. Měli byste vidět **10**.  
  
 Můžete ukazatel myši přesunete **testInt** proměnné, které chcete zobrazit aktuální hodnota v data tip.  
  
 ![DBG&#95;Basics&#95;Data&#95;Tips](../debugger/media/dbg_basics_data_tips.png "DBG_Basics_Data_Tips")  
  
 Pod okno kódu byste měli vidět **automobily**, **místní hodnoty –**, a **sledovat** systému windows. Tyto windows zobrazit aktuální hodnoty proměnných v době spuštění. Obě **automobily** a **místní hodnoty –** windows zobrazit **testInt** s hodnotou **10**.  
  
 ![Automatické hodnoty – okno při ladění](../debugger/media/getstartedwindows.png "GetStartedWindows")  
  
 Další informace o těchto windows najdete v tématu [automobily a místní hodnoty – Windows](../debugger/autos-and-locals-windows.md).  
  
 Podívejme se, jak se změní, jak jsme provede program hodnotu proměnné. Nastavit zarážky `testInt += 1;` řádku a znovu spusťte ladění. Měli byste vidět, který **testInt** v **místní hodnoty –** a **automobily** je systém windows **0**, a **i** je **1**. Pokud budete pokračovat, ladění (**ladění > Pokračovat**, nebo **pokračovat** na panelu nástrojů nebo **F5**), můžete uvidíte, že hodnota **testInt** změny **1**, pak **2**a tak dále. Když získáte unavená z vyhledávání na tyto změny, odeberte bod přerušení (**ladění > Přepnout zarážku**, nebo klepněte na ni na okraji) a pokračovat, ladění. Pokud chcete odebrat všechny zarážky, klikněte na tlačítko **ladění > Odstranit všechny zarážky**, nebo **CTRL + SHIFT + F9**a klikněte na tlačítko **Ano** v dialogovém okně s dotazem, **provést Chcete odebrat všechny zarážky?** .  
  
## <a name="stepping-into-and-over-function-calls"></a>Krokování s do a přes volání funkcí  
 Ladicí program příkaz podle-příkazu může spustit kód (**Krokovat s vnořením**) nebo při ladicího programu přeskočí funkce se může spustit kód (**Krokovat s přeskočením**) rychle získat kódu, aby vás zajímá více ( Funkce stále spuštění kódu). Můžete přepínat mezi obě metody ve stejné relaci ladění.  
  
 Rozdíl mezi **Krokovat s vnořením** a **Krokovat s přeskočením**, je potřeba přidat metodu, která volá jinou metodu. Přidání metody do aplikace C# a volat z metody Main. Kód by měl vypadat přibližně takto:  
  
```csharp  
static void Main(string[] args)  
{  
    Method1();  
    Console.WriteLine("end");  
}  
  
private static void Method1()  
{  
    Console.WriteLine("in Method1");  
}  
```  
  
 Nastavit zarážky `Method1();` volání v metodě hlavní a spuštění ladění. Při provádění dělí, klikněte na tlačítko **ladění > Krokovat s vnořením** (nebo **Krokovat s vnořením** na panelu nástrojů nebo **F11**). Provádění zalomení znovu na první složených závorek v Method1():  
  
 ![Zanoříte se do kódu](../debugger/media/getstartedstepinto.png "GetStartedStepInto")  
  
 Zastavte ladění a znovu spustit a po spuštění dělí u zarážky, klikněte na tlačítko **ladění > Krokovat s přeskočením** (nebo **Krokovat s přeskočením** na panelu nástrojů nebo **F10**). Provádění znovu dělí na `Console.WriteLine("end");`.  
  
 Pokud chcete získat další informace o navigace v kódu s ladicím programem, najdete v článku [procházení kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md).