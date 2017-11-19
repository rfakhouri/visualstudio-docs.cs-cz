---
title: "Ladění pomocí Xamarin | Microsoft Docs"
description: "Ladění je běžné a potřeby součástí programování. Visual Studio pro Mac jako vyspělá rozhraní IDE, obsahuje celou sadu funkcí, které usnadňují easy ladění. Z bezpečné ladění, k vizualizaci dat, tento článek vysvětluje, jak použít úplnou potenciálně ladění v sadě Visual Studio for Mac."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-debug
ms.assetid: BB7A084D-9AC2-48B5-8076-6C8518796BBA
ms.openlocfilehash: 6d85c318b60e065be86d242bf3199b3716c59ada
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-with-xamarin"></a>Ladění pomocí Xamarinu


Visual Studio pro Mac má nativní ladicí program povolení ladění podporu pro aplikace Xamarin.iOS, Xamarin.Mac a Xamarin.Android.
Visual Studio pro Mac používá [ *logicky ladicí program Mono*](http://www.mono-project.com/docs/advanced/runtime/docs/soft-debugger/), která je implementována do Mono modulu runtime umožňuje sadě Visual Studio pro Mac k ladění spravovaného kódu pro všechny platformy.

## <a name="the-debugger"></a>Ladicí program

Visual Studio pro Mac používá Mono logicky ladicí program k ladění spravovaného kódu (C# nebo F #) ve všech aplikacích Xamarin. Mono logicky ladicí program se liší od regular ladicí programy, to znamená společné ladicí program, který je součástí Mono modulu runtime; generovaný kód a Mono runtime spolupracovat s IDE a poskytuje prostředí ladění. Modul runtime Mono zveřejňuje ladění funkce prostřednictvím přenosu protokol, který si můžete přečíst více o [v Mono dokumentaci](http://www.mono-project.com/docs/advanced/runtime/docs/soft-debugger-wire-format/).


Pevné ladicí programy, jako například [LLDB]( http://lldb.llvm.org/index.html) nebo [GDB]( https://www.gnu.org/software/gdb/), řídit program bez vědomí nebo spolupráce vyladěnou programu, ale může být užitečné při ladění aplikace Xamarin v události, které třeba ladění nativní aplikace pro iOS nebo Android kódu.

## <a name="using-the-debugger"></a>Používání ladicího programu

Spustit ladění – všechny aplikace, vždy zajistěte, že konfigurace je nastavená na **ladění**. Konfigurace ladění poskytuje užitečné sadu nástrojů na podporu ladění, jako je například zarážky, pomocí vizualizérech dat a zobrazení zásobníku volání:

![Konfigurace ladění](media/debugging-image_0.png)

## <a name="setting-a-breakpoint"></a>Nastavení boru přerušení

Chcete-li nastavit zarážky ve vaší IDE, klikněte na tlačítko oblasti okraje editoru, vedle číslo řádku kódu, kde chcete rozdělit:

![Nastavení zarážek v rozpětí](media/debugging-image0.png)


Můžete zobrazit všechny zarážky, které byly nastaveny ve vašem kódu přechodem na **zarážky pad**:

![Seznam zarážky](media/debugging-image0a.png)


## <a name="start-debugging"></a>Spuštění ladění

Spustit ladění, vyberte v vaší IDE podobné nebo emulátoru nebo cílové zařízení:

![Vyberte cílové zařízení](media/debugging-image1.png)

Potom nasaďte aplikaci stisknutím **přehrání** tlačítko nebo **Cmd + vrátit**. Při zásahu zarážku kód bude zvýrazněná žlutý:

![Narazil zvýraznění zobrazující zarážek](media/debugging-image2.png)

Ladicí nástroje, jako je třeba použít ke kontrole hodnoty objektů, lze použít v tomto okamžiku získat další informace o co se děje ve vašem kódu:

![Ladění vizualizace](media/debugging-image3.png)

## <a name="conditional-breakpoints"></a>Podmíněné zarážky

Můžete také nastavit pravidla diktování v případech, podle nichž má dojít k zarážky, to se označuje jako přidávání *podmíněného zarážek*. Pro nastavení podmíněné zarážky, přístup **zarážku – vlastnosti – okno**, což lze provést dvěma způsoby:


* Pokud chcete přidat nový podmíněné zarážky, klikněte pravým tlačítkem na editor okrajem, nalevo od číslo řádku pro kód, který chcete nastavit zarážky a vyberte nové zarážek:


 ![Breakpoint – kontextové nabídky](media/debugging-image4.png)

* Pokud chcete přidat do existující zarážek podmínku, klikněte pravým tlačítkem na zarážek a vyberte **zarážek vlastnosti**, nebo v **zarážky Pad**, kliknutím na tlačítko Upravit zarážek znázorněné dole:


 ![Upravit existující zarážka v odsazení zarážky](media/debugging-image5.png)


Potom můžete zadat podmínky, pod kterým chcete zarážek proběhnout:

 ![Upravit podmínky zarážek](media/debugging-image6.png)

## <a name="stepping-through-code"></a>Procházení kódu

Pokud bylo dosaženo zarážky, nástroje pro ladění umožňují získat kontrolu nad spuštění tohoto programu. Visual Studio pro Mac se zobrazí čtyři tlačítka, který vám umožní spustit a projděte kód. V sadě Visual Studio pro Mac bude vypadat takto:

 ![Tlačítka pro krok prostřednictvím kódu](media/debugging-image7.png)

Zde jsou čtyři tlačítka:

*   **Přehrání** – tím se zahájí provádění kód, dokud na další zarážku.
*   **Krokovat s přeskočením** – tato funkce spustí dalším řádku kódu. Pokud na další řádek je volání funkce, Krokovat s přeskočením provede funkci a zastaví se v dalším řádku kódu *po* funkce.
*   **Krokovat s vnořením** – to budou také spuštěny při dalším řádku kódu. Pokud na další řádek je volání funkce, Krokovat s vnořením se zastaví na prvním řádku funkce, abyste mohli pokračovat, řádek po řádku ladění funkce. Pokud na další řádek není funkce, bude se chovat stejná jako Krokovat s přeskočením.
*   **Krokovat s Vystoupením** – to se vrátí na řádek, kde byl volán aktuální funkce.


## <a name="debugging-monos-class-libraries"></a>Ladění na Mono knihovny tříd
Xamarin produkty dodávají spolu s zdrojový kód pro knihovny tříd Mono společnosti a na jediném kroku z ladicí program můžete použít ke kontrole, jak jsou pod pokličkou práce věcí.

Vzhledem k tomu, že tato funkce vyžaduje další paměť během ladění, je ve výchozím nastavení vypnutý.

Chcete-li povolit tuto funkci, procházejte k **Visual Studio pro Mac > Předvolby > ladicí program** a ujistěte se, že "**ladění projektu kódu pouze; není kroku do kódu framework.** " možnost je **nezaškrtnuté**, jak je uvedeno dále:

 ![Není krok do framework kód – možnost](media/debugging-image8.png)
