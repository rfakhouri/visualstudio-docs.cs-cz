---
title: Vytváření rozšíření pomocí VSPackage | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
ms.assetid: c0cc5e08-4897-44f2-8309-e3478f1f999e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6b66aef72d9af1ef40a061d1a82d18161a416586
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345362"
---
# <a name="create-an-extension-with-a-vspackage"></a>Vytvoření rozšíření pomocí VSPackage

Tento návod ukazuje, jak vytvořit projekt VSIX a přidejte položku projektu VSPackage. Použijeme sady VSPackage se získat službu uživatelského prostředí. Chcete-li zobrazit okno se zprávou.

## <a name="prerequisites"></a>Požadavky

Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-vspackage"></a>Vytvoření VSPackage

1. Vytvořte projekt VSIX s názvem **FirstPackage**. Šablona projektu VSIX v můžete najít **nový projekt** dialogové okno tak, že "vsix".

2. Po otevření projektu přidat šablonu položky balíčku sady Visual Studio s názvem **FirstPackage**. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat** > **nová položka**. V **přidat novou položku** dialogové okno, přejděte na **Visual C#**  > **rozšiřitelnost** a vyberte **balíček Visual Studio**. V **název** pole v dolní části okna, změňte název souboru příkazu *FirstPackage.cs*.

3. Sestavte projekt a spusťte ladění.

    Experimentální instanci sady Visual Studio se zobrazí. Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).

4. V experimentální instanci aplikace, otevřete **nástroje** > **rozšíření a aktualizace** okna. Měli byste vidět **FirstPackage** rozšíření tady. (Pokud otevřete **rozšíření a aktualizace** v instanci pracovního sadě Visual Studio, neuvidíte **FirstPackage**).

## <a name="load-the-vspackage"></a>Načtení sady VSPackage

V tomto okamžiku rozšíření nenačte, protože není nic, která způsobí, že ho pro načtení. Rozšíření můžete načíst obecně při interakci s jeho uživatelské rozhraní (kliknutím na příkaz nabídky, otevřete okno nástroje), nebo tak, že určíte, že by se měly načíst sady VSPackage v určitém kontextu uživatelského rozhraní. Další informace o načítání rozšíření VSPackages a uživatelské rozhraní kontextech najdete v tématu [načítání rozšíření VSPackages](../extensibility/loading-vspackages.md). V tomto postupu vám ukážeme, jak načíst VSPackage při otevření řešení.

1. Otevřít *FirstPackage.cs* souboru. Vyhledejte prohlášení o `FirstPackage` třídy. Nahraďte existující atributy s následujícími atributy:

    ```csharp
    [PackageRegistration(UseManagedResourcesOnly = true)]
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]
    [Guid(FirstPackage.PackageGuidString)]
    public sealed class FirstPackage : Package
    ```

2. Přidejme zpráva, že získáme tak jistotu, že byl načten sady VSPackage. Pomocí sady VSPackage `Initialize()` služby metody, chcete-li to provést, protože Visual Studio můžete získat až poté, co byly umístěny balíčku VSPackage. (Další informace o tom, jak služby najdete v tématu [jak: Získání služby](../extensibility/how-to-get-a-service.md).) Nahraďte `Initialize()` metoda `FirstPackage` s kódem, který získá <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> služby, získá <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> rozhraní a volání jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowMessageBox%2A> metoda.

    ```csharp
    protected override void Initialize()
    {
        base.Initialize();

        IVsUIShell uiShell = (IVsUIShell)GetService(typeof(SVsUIShell));
        Guid clsid = Guid.Empty;
        int result;
        Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(uiShell.ShowMessageBox(
            0,
            ref clsid,
            "FirstPackage",
             string.Format(CultureInfo.CurrentCulture, "Inside {0}.Initialize()", this.GetType().FullName),
            string.Empty,
            0,
            OLEMSGBUTTON.OLEMSGBUTTON_OK,
            OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,
            OLEMSGICON.OLEMSGICON_INFO,
            0,
            out result));
    }
    ```

3. Sestavte projekt a spusťte ladění. Zobrazí se experimentální instance.

4. Otevřete řešení v experimentální instanci aplikace. Měli byste vidět okno se zprávou, že **první balíček uvnitř Initialize()** .
