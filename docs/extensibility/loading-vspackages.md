---
title: Načítání rozšíření VSPackages | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, loading
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2c7c2a558abc928524813419df6b7848d34f0f3e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66309575"
---
# <a name="load-vspackages"></a>Načtení rozšíření VSPackages
Rozšíření VSPackages se načtou do sady Visual Studio pouze v případě jejich funkce je povinný. Například VSPackage se načte, když Visual Studio používá objekt pro vytváření projektu nebo služba, která implementuje sady VSPackage. Tato funkce je volána opožděné načtení, který se používá vždy, když je možné zvýšit výkon.

> [!NOTE]
> Visual Studio můžete určit určité VSPackage informace, jako jsou příkazy, které nabízí VSPackage bez načtení sady VSPackage.

 Rozšíření VSPackages lze nastavit na automaticky načíst v kontextu konkrétní uživatelské rozhraní (UI), například při otevření řešení. <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> Atribut nastaví tento kontext.

### <a name="autoload-a-vspackage-in-a-specific-context"></a>AutoLoad VSPackage v určitém kontextu

- Přidat `ProvideAutoLoad` atribut VSPackage atributy:

    ```csharp
    [DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\14.0")]
    [PackageRegistration(UseManagedResourcesOnly = true)]
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]
    [Guid("00000000-0000-0000-0000-000000000000")] // your specific package GUID
    public class MyAutoloadedPackage : Package
    {. . .}
    ```

     Zobrazit výčet pole <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> seznam kontexty uživatelského rozhraní a jejich hodnoty identifikátor GUID.

- Nastavit zarážku <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metody.

- Sestavení sady VSPackage a spusťte ladění.

- Načítání řešení nebo vytvořit novou.

     Sady VSPackage načte a zastaví na zarážce.

## <a name="force-a-vspackage-to-load"></a>Vynutit načtení VSPackage
 Za určitých okolností může mít VSPackage vynutit jiný VSPackage, který se má načíst. Zjednodušené VSPackage může například načíst větší VSPackage v kontextu, který není k dispozici jako CMDUIContext.

 Můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A> metoda přinutit VSPackage načíst.

- Vložte tento kód do <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda sady VSPackage, která vynutí jiného VSPackage načíst:

    ```csharp
    IVsShell shell = GetService(typeof(SVsShell)) as IVsShell;
    if (shell == null) return;

    IVsPackage package = null;
    Guid PackageToBeLoadedGuid =
        new Guid(Microsoft.PackageToBeLoaded.GuidList.guidPackageToBeLoadedPkgString);
    shell.LoadPackage(ref PackageToBeLoadedGuid, out package);

    ```

     Při inicializaci sady VSPackage, vynutí `PackageToBeLoaded` načíst.

     Platnost načítání by neměl použít pro komunikaci VSPackage. Použití [používání a poskytování služeb](../extensibility/using-and-providing-services.md) místo.

## <a name="see-also"></a>Viz také:
- [Balíčky VSPackage](../extensibility/internals/vspackages.md)
