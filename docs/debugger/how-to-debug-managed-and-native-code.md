---
title: 'Kurz: Ladění nativního a spravovaného kódu (smíšený režim)'
description: Zjistěte, jak ladit nativní knihovny DLL z aplikace .NET Core nebo rozhraní .NET Framework pomocí ladění ve smíšeném režimu
ms.custom: ''
ms.date: 04/27/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- mixed mode debugging
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: 0abe9da4ff34217097cd8c4021f44b2ce7d52d5f
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281128"
---
# <a name="tutorial-debug-managed-and-native-code-in-visual-studio"></a>Kurz: Ladění nativního a spravovaného kódu v sadě Visual Studio

Visual Studio umožňuje povolit více než jeden typ ladicí program při ladění, která se nazývá ladění ve smíšeném režimu. V tomto kurzu nastavíte možnosti ladění spravovaná a nativní kód v rámci jedné relace ladění. Tento kurz ukazuje, jak k ladění nativního kódu ze spravované aplikace, ale můžete také provést zpětného, a [ladění spravovaného kódu z nativní aplikace](../debugger/how-to-debug-in-mixed-mode.md). Ladicí program podporuje i jiné typy ladění ve smíšeném režimu, jako je například ladění [Python a nativní kód](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md) a používání ladicího programu skript v typy aplikací, jako je například technologie ASP.NET.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Vytvoření jednoduchého nativní knihovny DLL
> * Vytvoření jednoduché aplikace .NET Core nebo rozhraní .NET Framework pro volání knihovny DLL
> * Spuštění ladicího programu
> * Stiskněte tlačítko zarážky ve spravované aplikaci
> * Krok do nativního kódu

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio a **vývoj aplikací s jazykem C++** zatížení.

    Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

    Pokud potřebujete nainstalovat úlohu, ale Visual Studio už máte, klikněte v dialogovém okně **Nový projekt** v levém podokně na odkaz **Otevřít instalační program pro Visual Studio**. Spustí se instalační program pro Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

* Je také nutné mít buď **vývoj aplikací .NET** zatížení nebo **.NET Core křížové vývoj platformy** zatížení nainstalovaná, v závislosti na typ aplikace, které chcete vytvořit.

## <a name="create-a-simple-native-dll"></a>Vytvoření jednoduchého nativní knihovny DLL

1. V sadě Visual Studio, vyberte **soubor** > **nový** > **projektu**.

1. V **nový projekt** dialogovém okně vyberte **Visual C++**, **Obecné** z části nainstalovaných šablon a potom v prostředním podokně vyberte **prázdný projekt** .

1. V **název** zadejte **ladění režimu Mixed** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří prázdný projekt, který se zobrazí v Průzkumníku řešení v pravém podokně.

1. V Průzkumníku řešení klikněte pravým tlačítkem myši **zdrojové soubory** uzlu v jazyce C++ projektu a potom vyberte **přidat** > **nová položka**a potom vyberte **C++ soubor ()**. Zadejte název souboru **Mixed Mode.cpp**a zvolte **přidat**.

    Visual Studio přidá nový soubor C++.

1. Zkopírujte následující kód do *Mixed Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. V Průzkumníku řešení klikněte pravým tlačítkem myši **soubory hlaviček** uzlu v jazyce C++ projektu a potom vyberte **přidat** > **nová položka**a potom vyberte  **Soubor (hlaviček)**. Zadejte název souboru **Mixed Mode.h**a zvolte **přidat**.

    Visual Studio přidá nový soubor záhlaví.

1. Zkopírujte následující kód do *Mixed Mode.h*:

    ```cpp
    #ifndef MIXED_MODE_MULTIPLY_HPP
    #define MIXED_MODE_MULTIPLY_HPP

    extern "C"
    {
        __declspec(dllexport) int __stdcall mixed_mode_multiply(int a, int b) {
            return a * b;
        }
    }
    #endif
    ```

1. Na panelu nástrojů ladění vyberte **ladění** konfigurace a **libovolný procesor** jako platformu, nebo pro .NET Core, vyberte **x64** jako platformu.

    > [!NOTE]
    > Na .NET Core, zvolte **x64** jako platformu. .NET core se vždycky spustí v režimu 64-bit, je to nezbytné.

1. V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu (**ladění režimu Mixed**) a zvolte **vlastnosti**.

1. V **vlastnosti** vyberte **vlastnosti konfigurace** > **Linkeru** > **Upřesnit**, a potom v **žádný vstupní bod** rozevíracího seznamu vyberte **ne**. Pak použijte nastavení.

1. V **vlastnosti** vyberte **vlastnosti konfigurace** > **Obecné**a potom vyberte **dynamická knihovna (DLL)** z **typ konfigurace** pole. Pak použijte nastavení.

    ![Přepnout na nativní knihovny DLL](../debugger/media/mixed-mode-set-as-native-dll.png)

1. Klikněte pravým tlačítkem na projekt a zvolte **ladění** > **sestavení**.

    Projekt by se měl sestavit bez chyb.

## <a name="create-a-simple-net-framework-or-net-core-app-to-call-the-dll"></a>Vytvoření jednoduché aplikace rozhraní .NET Framework nebo .NET Core volání knihovny DLL

1. V sadě Visual Studio, vyberte **soubor** > **nový** > **projektu**.

1. Vyberte šablonu pro kód aplikace.

    Pro rozhraní .NET Framework v **nový projekt** dialogovém okně vyberte **Visual C#**, **Windows Desktop** z části nainstalovaných šablon a potom v prostředním podokně vyberte  **Konzole aplikace (rozhraní .NET Framework)**.

    Pro .NET Core v **nový projekt** dialogovém okně vyberte **Visual C#**, **.NET Core** z části nainstalovaných šablon a potom v prostředním podokně vyberte  **Konzole aplikace (.NET Core)**.

1. V **název** zadejte **Mixed_Mode_Calling_App** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt konzoly, která se zobrazí v Průzkumníku řešení v pravém podokně.

1. V *Program.cs*, ve výchozím kódu nahraďte následujícím kódem:

    ```csharp
    using System;
    using System.Runtime.InteropServices;

    namespace Mixed_Mode_Calling_App
    {
        public class Program
        {
            // Replace the file path shown here with the
            // file path on your computer. For .NET Core, the typical (default) path
            // for a 64-bit DLL might look like this:
            // C:\Users\username\source\repos\Mixed-Mode-Debugging\x64\Debug\Mixed-Mode-Debugging.dll
            // Here, we show a typical path for a DLL targeting the **Any CPU** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed-Mode-Debugging\Debug\Mixed-Mode-Debugging.dll", EntryPoint =
            "mixed_mode_multiply", CallingConvention = CallingConvention.StdCall)]
            public static extern int Multiply(int x, int y);
            public static void Main(string[] args)
            {
                int result = Multiply(7, 7);
                Console.WriteLine("The answer is {0}", result);
                Console.ReadKey();
            }
        }
    }
    ```

## <a name="configure-mixed-mode-debugging-net-framework"></a>Konfigurace ladění (rozhraní .NET Framework) ve smíšeném režimu

1. V Průzkumníku řešení klikněte pravým tlačítkem na spravovaný **Mixed_Mode_Calling_App** projektu a zvolte **nastavit jako spouštěný projekt**.

1. Klikněte pravým tlačítkem na spravovaný **Mixed_Mode_Calling_App** projektu a potom vyberte **vlastnosti**a potom zvolte **ladění** v levém podokně. Vyberte **povolit ladění nativního kódu**a pak zavřete stránku vlastností a uložte změny.

    ![Povolit ladění ve smíšeném režimu](../debugger/media/mixed-mode-enable-native-code-debugging.png)

## <a name="configure-mixed-mode-debugging-net-core"></a>Konfigurace ladění (.NET Core) ve smíšeném režimu

Ve většině verzí aplikace Visual Studio 2017, musíte povolit ladění ve smíšeném režimu pro nativní kód v aplikaci .NET Core pomocí *launchSettings.json* souboru místo **vlastnosti** stránky. Ke sledování uživatelského rozhraní aktualizace pro tuto funkci, najdete v části to [potíže Githubu](https://github.com/dotnet/project-system/issues/1125).

1. Otevřete *launchSettings.json* v soubor *vlastnosti* složky. Ve výchozím nastavení můžete najít soubor v tomto umístění.

    *C:\Users\<uživatelské jméno > \source\repos\Mixed_Mode_Calling_App\Properties*

    Pokud soubor neexistuje, otevřete vlastnosti projektu (klikněte pravým tlačítkem na spravovaný **Mixed_Mode_Calling_App** projektu v Průzkumníku řešení a vyberte **vlastnosti**). Změňte dočasné v **ladění** kartě a sestavte projekt. Vrátit zpět změny, která jste udělali.

1. V *lauchsettings.json* soubor, přidejte následující vlastnost:

    ```
    "nativeDebugging": true
    ```

    Ano například souboru může vypadat následovně:

    ```
    {
      "profiles": {
        "Mixed_Mode_Calling_App": {
          "commandName": "Project",
          "nativeDebugging": true
        }
      }
    }
    ```

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Nastavit zarážky a spuštění ladicího programu

1. Otevřete v projektu jazyka C# *Program.cs* a kliknutím na levém okraji nastavit zarážky následující řádek kódu:

    ```csharp
    int result = Multiply(7, 7);
    ```

    Červené kolečko se zobrazí na levém okraji indikující, že jste si nastavili zarážku.

1. Stiskněte klávesu **F5** (**ladění** > **spustit ladění**) ke spuštění ladicího programu.

    Ladicí program se pozastaví na zarážce, kterou nastavíte. Žlutá šipka označuje, kde je momentálně pozastaven ladicího programu.

## <a name="step-into-native-code"></a>Krok do nativního kódu

1. Při pozastavená ve spravované aplikaci, stiskněte klávesu **F11** (**ladění** > **Krokovat s vnořením**).

    Otevře se soubor hlaviček s nativním kódem a zobrazí žlutý šipku, kde je pozastaven ladicího programu.

    ![Krok do nativního kódu](../debugger/media/mixed-mode-step-into-native-code.png)

    Teď můžete provádět akce podobně jako sada a dosáhl zarážky a zkontrolovat proměnné.

1. Podržte ukazatel nad proměnné zobrazíte jejich hodnotu.

1. Podívejte se na **automobily** a **místní hodnoty –** windows proměnné a jejich hodnoty.

    Při pozastavena v ladicím programu, můžete použít jiné funkce ladicího programu, jako **sledovat** okno a **zásobníkem volání** okno.

1. Stiskněte klávesu **F11** znovu, aby ladicí program jeden řádek záloh.

1. Stiskněte klávesu **Shift + F11** (**ladění** > **Krokovat s Vystoupením**) a pokračovat v provádění aplikace pozastavit znovu ve spravované aplikaci.

1. Pokud chcete pokračovat v aplikaci, stiskněte **F5**.

    Blahopřejeme! Dokončili jste kurz na ladění ve smíšeném režimu.

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak k ladění nativního kódu ze spravované aplikace povolením ladění ve smíšeném režimu. Přehled dalších funkcí ladicího programu najdete v následujícím článku:

> [!div class="nextstepaction"]
> [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)