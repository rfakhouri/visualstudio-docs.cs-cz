---
title: Vytváření rozšíření s VSPackage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: c0cc5e08-4897-44f2-8309-e3478f1f999e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 706cdcd26df18af9ccd79b5bf83890c47b1faf57
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109448"
---
# <a name="creating-an-extension-with-a-vspackage"></a>Vytváření rozšíření s VSPackage
Tento návod ukazuje, jak vytvořit projekt VSIX a přidat položku VSPackage projektu. Chcete-li zobrazit okno se zprávou získat službu prostředí uživatelského rozhraní budeme používat VSPackage.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-vspackage"></a>Vytváření VSPackage  
  
1.  Vytvoření projektu VSIX s názvem **FirstPackage**. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Po otevření projektu přidat šablonu položky balíčku sady Visual Studio s názvem **FirstPackage**. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **balíček Visual Studio**. V **název** pole v dolní části okna, změňte název souboru příkaz **FirstPackage.cs**.  
  
3.  Sestavte projekt a spusťte ladění.  
  
     Zobrazí se experimentální instanci sady Visual Studio. Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
4.  V experimentální instance, otevřete **nástroje nebo rozšíření a aktualizace** okno. Měli byste vidět **FirstPackage** rozšíření sem. (Pokud otevřete **rozšíření a aktualizace** v instanci pracovní sady Visual Studio, neuvidíte **FirstPackage**).  
  
## <a name="loading-the-vspackage"></a>Načítání VSPackage  
 V tomto okamžiku rozšíření nepodaří načíst, protože není nic, který způsobuje, že ho načíst. Rozšíření můžete načíst obecně při interakci s jeho uživatelském rozhraní (kliknutím na příkaz nabídky, otevřete okno nástroj), nebo zadáním, že VSPackage by se měly načíst v konkrétní kontextu uživatelského rozhraní. Další informace o načítání uživatelského rozhraní a VSPackages kontexty najdete v tématu [načítání VSPackages](../extensibility/loading-vspackages.md). Pro tento postup jsme budete ukazují, jak načíst VSPackage při řešení je otevřený.  
  
1.  Otevřete soubor FirstPackage.cs. Podívejte se na deklaraci třídy FirstPackage. Nahradí existující atributy následující:  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid(FirstPackage.PackageGuidString)]  
    public sealed class FirstPackage : Package  
    ```  
  
2.  Umožňuje přidat zprávu, která oznamuje, že VSPackage načetl. Metodu Initialize() VSPackage používáme k tomu, protože služby Visual Studio můžete získat až poté, co má byla umístěný VSPackage. (Další informace o získání služby najdete v tématu [jak: získat službu](../extensibility/how-to-get-a-service.md).) Nahraďte kód, který získá metodě inicializaci() FirstPackage <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> služby, získá <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> rozhraní a volání jeho <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowMessageBox%2A> metoda.  
  
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
  
3.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci.  
  
4.  Otevřete řešení v experimentální instanci. Měli byste vidět okno se zprávou, která uvádí, že **první balíček uvnitř inicializaci()**.