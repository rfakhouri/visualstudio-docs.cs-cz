---
title: 'Kurz: Ladění spravovaného a nativního kódu (ve smíšeném režimu)'
description: Zjistěte, jak ladit nativní knihovnu DLL z aplikace .NET Core nebo .NET Framework pomocí ladění ve smíšeném režimu
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 97ad3b6e112a05db817f7a522c3865893d439fd7
ms.sourcegitcommit: 12d6398c02e818de4fbcb4371bae9e5db6cf9509
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/25/2018
ms.locfileid: "50050323"
---
# <a name="tutorial-debug-managed-and-native-code-in-the-same-debugging-session"></a>Kurz: Ladění spravovaného a nativního kódu ve stejné relaci ladění

Visual Studio umožňuje povolit více než jeden typ ladicího programu během ladění, která se nazývá ladění ve smíšeném režimu. V tomto kurzu nastavujete možnosti pro ladění spravovaného a nativního kódu v jedné relaci ladění. Tento kurz ukazuje postupy při ladění nativního kódu ze spravovaných aplikací, ale můžete také provést opačný a [ladění spravovaného kódu z nativní aplikace](../debugger/how-to-debug-in-mixed-mode.md). Ladicí program podporuje ladění ve smíšeném režimu, jako je ladění jiných typů také [Python a nativní kód](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md) a pomocí ladicího programu skriptu v typech aplikací, jako je například technologie ASP.NET.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Vytvoření jednoduché nativní knihovny DLL
> * Vytvořte jednoduchou aplikaci .NET Core nebo .NET Framework pro volání knihovny DLL
> * Spuštění ladicího programu
> * Na zarážku ve spravované aplikaci
> * Krok do nativního kódu

## <a name="prerequisites"></a>Požadavky

* Musíte mít nainstalovanou sadu Visual Studio a **vývoj desktopových aplikací pomocí C++** pracovního vytížení.

    Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

    Pokud potřebujete nainstalovat úlohu, ale Visual Studio už máte, klikněte v dialogovém okně **Nový projekt** v levém podokně na odkaz **Otevřít instalační program pro Visual Studio**. Spustí se instalační program pro Visual Studio. Zvolte **vývoj desktopových aplikací pomocí C++** úloh, klikněte na tlačítko **změnit**.

* Musíte také mít **vývoj desktopových aplikací .NET** úlohy nebo **.NET Core pro vývoj napříč platformami** nainstalovaná úloha, v závislosti na typu aplikace, které chcete vytvořit.

## <a name="create-a-simple-native-dll"></a>Vytvoření jednoduché nativní knihovny DLL

1. V sadě Visual Studio, zvolte **souboru** > **nový** > **projektu**.

1. V **nový projekt** dialogového okna zvolte **Visual C++**, **jiných** z části nainstalovaných šablon a potom v prostředním podokně vyberte **prázdný projekt** .

1. V **název** zadejte **Mixed_Mode_Debugging** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří prázdný projekt, který se zobrazí v Průzkumníku řešení v pravém podokně.

1. V Průzkumníku řešení klikněte pravým tlačítkem na **zdrojové soubory** uzel v C++ projektu a klikněte na tlačítko **přidat** > **nová položka**a pak vyberte **C++ souboru (.cpp)**. Zadejte název souboru **Mixed_Mode.cpp**a zvolte **přidat**.

    Visual Studio přidá nový soubor jazyka C++.

1. Zkopírujte následující kód do *Mixed_Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. V Průzkumníku řešení klikněte pravým tlačítkem na **hlavičkové soubory** uzel v C++ projektu a klikněte na tlačítko **přidat** > **nová položka**a pak vyberte  **Soubor hlaviček (.h)**. Zadejte název souboru **Mixed_Mode.h**a zvolte **přidat**.

    Visual Studio přidá nový soubor hlaviček.

1. Zkopírujte následující kód do *Mixed_Mode.h*:

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

1. Vyberte z panelu nástrojů ladění **ladění** konfigurace a **x86** nebo **x64** jako platformu (pro .NET Core, který se vždy spouští v 64bitovém režimu, vyberte **x64**  jako platformu).

1. V Průzkumníku řešení klikněte pravým tlačítkem myši na uzel projektu (**Mixed_Mode_Debugging**) a zvolte **vlastnosti**.

    > [!IMPORTANT]
    > Konfigurace vlastností jazyka C++ je podle platformy. Proto při přepínání z jednoho do jiné (x86 k x64 nebo naopak), je musí také nastavit vlastnosti pro novou konfiguraci. (Na stránce vlastností, ověřte **x64** nebo **Win32** je nastaven jako platformu v horní části stránky.)

1. V **vlastnosti** zvolte **vlastnosti konfigurace** > **Linkeru** > **Upřesnit**, a pak v **bez vstupního bodu** rozevíracího seznamu, ujistěte se, že **č** je vybrána. Pokud potřebujete změnit nastavení pro **ne**, klikněte na tlačítko **použít**.

1. V **vlastnosti** zvolte **vlastnosti konfigurace** > **Obecné**a pak vyberte **dynamická knihovna (.dll)** z **typ konfigurace** pole. Pak použijte nastavení.

    ![Přepnout na nativní knihovnu DLL](../debugger/media/mixed-mode-set-as-native-dll.png)

1. Klikněte pravým tlačítkem na projekt a zvolte **sestavení**.

    Projekt by se měl sestavit bez chyb.

## <a name="create-a-simple-net-framework-or-net-core-app-to-call-the-dll"></a>Vytvoření jednoduché aplikace rozhraní .NET Framework nebo .NET Core pro volání knihovny DLL

1. V sadě Visual Studio, zvolte **souboru** > **nový** > **projektu**.

    > [!NOTE]
    > I když můžete také přidat nový spravovaný projekt do řešení pomocí projektu C++, místo vytvoření nového řešení, jsme se to provedete zde pro podporu většímu množství ladění scénářů.

1. Vyberte šablonu pro kód aplikace.

    Pro rozhraní .NET Framework v **nový projekt** dialogového okna zvolte **Visual C#**, **Windows Desktop** z části nainstalovaných šablon a potom v prostředním podokně vyberte  **Aplikace konzoly (.NET Framework)**.

    Pro .NET Core v **nový projekt** dialogového okna zvolte **Visual C#**, **.NET Core** z části nainstalovaných šablon a potom v prostředním podokně vyberte  **Aplikace (.NET Core) konzoly**.

1. V **název** zadejte **Mixed_Mode_Calling_App** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt konzoly, která se zobrazí v Průzkumníku řešení v pravém podokně.

1. V *Program.cs*, nahraďte kód následujícím kódem:

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
            // C:\Users\username\source\repos\Mixed_Mode_Debugging\x64\Debug\Mixed_Mode_Debugging.dll
            // Here, we show a typical path for a DLL targeting the **x86** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed_Mode_Debugging\Debug\Mixed_Mode_Debugging.dll", EntryPoint =
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

1. V novém kódu aktualizujte cestu k souboru do cesty pro knihovnu DLL, kterou jste vytvořili (viz komentáře ke kódu). Ujistěte se, že nahradíte *uživatelské jméno* zástupný symbol.

## <a name="configure-mixed-mode-debugging-net-framework"></a>Konfigurace ve smíšeném režimu ladění (.NET Framework)

1. V Průzkumníku řešení klikněte pravým tlačítkem na spravovanou **Mixed_Mode_Calling_App** projekt a zvolte **nastavit jako spouštěný projekt**.

1. Klikněte pravým tlačítkem na spravovanou **Mixed_Mode_Calling_App** projektu a klikněte na tlačítko **vlastnosti**a klikněte na tlačítko **ladění** v levém podokně. Vyberte **povolit ladění nativního kódu**a pak zavřete stránku vlastností a uložte změny.

    ![Povolit ladění ve smíšeném režimu](../debugger/media/mixed-mode-enable-native-code-debugging.png)

## <a name="configure-mixed-mode-debugging-net-core"></a>Konfigurace ve smíšeném režimu ladění (.NET Core)

Ve většině verzí sady Visual Studio 2017, musíte povolit ladění ve smíšeném režimu pro nativní kód v aplikaci .NET Core pomocí *launchSettings.json* souborů namísto **vlastnosti** stránky. Pokud chcete sledovat aktualizace uživatelského rozhraní pro tuto funkci, najdete v tomto [problém Githubu](https://github.com/dotnet/project-system/issues/1125).

1. Otevřít *launchSettings.json* soubor *vlastnosti* složky. Ve výchozím nastavení najdete v tomto umístění souboru.

    *C:\Users\<uživatelské jméno > \source\repos\Mixed_Mode_Calling_App\Properties*

    Pokud soubor není k dispozici, otevřete vlastnosti projektu (klikněte pravým tlačítkem na spravovanou **Mixed_Mode_Calling_App** projektu v Průzkumníku řešení a vyberte **vlastnosti**). Změňte dočasné v **ladění** kartu a sestavte projekt. Vrátit se provedené změny.

1. V *lauchsettings.json* přidejte následující vlastnost:

    ```csharp
    "nativeDebugging": true
    ```

    Například může tedy váš soubor vypadat nějak takto:

    ```csharp
    {
      "profiles": {
        "Mixed_Mode_Calling_App": {
          "commandName": "Project",
          "nativeDebugging": true
        }
      }
    }
    ```

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Nastavte zarážku a spuštění ladicího programu

1. V C# projekt, otevřete *Program.cs* a nastavte zarážku v následující řádek kódu kliknutím do levého okraje:

    ```csharp
    int result = Multiply(7, 7);
    ```

    Na levém okraji k označení, že je nastavena zarážka se zobrazí červený kruh.

1. Stisknutím klávesy **F5** (**ladění** > **spustit ladění**) spuštění ladicího programu.

    Ladicí program pozastavení na zarážce, kterou jste nastavili. Žlutá šipka označuje, kde je nyní pozastavena ladicím programu.

## <a name="step-into-native-code"></a>Krok do nativního kódu

1. Během pozastavení ve spravované aplikaci, stiskněte klávesu **F11** (**ladění** > **Krokovat s vnořením**).

    Otevře se soubor hlaviček s nativním kódem a uvidíte žlutou šipku, kde je pozastavena ladicím programu.

    ![Krok do nativního kódu](../debugger/media/mixed-mode-step-into-native-code.png)

    Teď můžete provádět akce podobně jako sada a dosažení zarážky a kontrolovat proměnné.

1. Najeďte myší proměnné zobrazíte jejich hodnoty.

1. Podívejte se na **automatické hodnoty** a **lokální** windows zobrazit proměnné a jejich hodnoty.

    Během pozastavení v ladicím programu, můžete použít další funkce ladicího programu, jako **Watch** okno a **zásobník volání** okna.

1. Stisknutím klávesy **F11** znovu, aby ladicí program jeden řádek záloh.

1. Stisknutím klávesy **Shift + F11** (**ladění** > **Krokovat s Vystoupením**) a pokračovat v provádění aplikace znovu pozastavit ve spravované aplikaci.

1. Pokud chcete pokračovat v aplikaci, stiskněte **F5**.

    Blahopřejeme! Dokončili jste kurz na ladění ve smíšeném režimu.

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak k ladění nativního kódu ze spravovaných aplikací tím, že ladění ve smíšeném režimu. Přehled o další funkce ladicího programu najdete v následujícím článku:

> [!div class="nextstepaction"]
> [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)
