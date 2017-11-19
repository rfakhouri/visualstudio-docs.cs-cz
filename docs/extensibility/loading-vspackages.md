---
title: "Načítání VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, loading
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 94db8d3bb95e254a3fa528a424048162916fce99
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="loading-vspackages"></a>Načítání VSPackages
VSPackages jsou načteny do sady Visual Studio jenom v případě, že se požaduje jejich funkce. Například VSPackage je načtena, když Visual Studio použije objekt pro vytváření projektu nebo služba, která implementuje VSPackage. Tato funkce je volána zpožděné načítání, který se používá, pokud je to možné ke zlepšení výkonu.  
  
> [!NOTE]
>  Visual Studio můžete určit určité VSPackage informace, například příkazy, které nabízí VSPackage, bez načítání VSPackage.  
  
 VSPackages může být nastavena na autoload v kontextu určitého uživatelského rozhraní (UI), například když je řešení otevřené. <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> Atribut nastaví tento kontext.  
  
### <a name="autoloading-a-vspackage-in-a-specific-context"></a>Autoloading VSPackage v konkrétní kontextu  
  
-   Přidat `ProvideAutoLoad` atribut VSPackage atributy:  
  
    ```csharp  
    [DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\14.0")]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid("00000000-0000-0000-0000-000000000000")] // your specific package GUID  
    public class MyAutoloadedPackage : Package  
    {. . .}  
    ```  
  
     V tématu Výčtové pole <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> seznam kontexty uživatelského rozhraní a jejich hodnoty identifikátor GUID.  
  
-   Nastavte zarážky v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda.  
  
-   Sestavení VSPackage a spusťte ladění.  
  
-   Spouštění řešení nebo ji vytvořte.  
  
     VSPackage načte a zastaví u zarážky.  
  
## <a name="forcing-a-vspackage-to-load"></a>Vynucení VSPackage načíst  
 Za určitých okolností může mít VSPackage vynutit jiný VSPackage má být načten. Například lightweight VSPackage může načíst větší VSPackage v kontextu, který není k dispozici jako CMDUIContext.  
  
 Můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A> metoda vynutit VSPackage načíst.  
  
-   Vložte tento kód do <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda VSPackage, který vynutí jiné VSPackage načíst:  
  
    ```csharp  
    IVsShell shell = GetService(typeof(SVsShell)) as IVsShell;  
    if (shell == null) return;  
  
    IVsPackage package = null;  
    Guid PackageToBeLoadedGuid =   
        new Guid(Microsoft.PackageToBeLoaded.GuidList.guidPackageToBeLoadedPkgString);  
    shell.LoadPackage(ref PackageToBeLoadedGuid, out package);  
  
    ```  
  
     Při inicializaci VSPackage vynutí `PackageToBeLoaded` načíst.  
  
     Platnost načítání není vhodné používat pro komunikaci VSPackage. Použití [pomocí a poskytování služeb](../extensibility/using-and-providing-services.md) místo.  
  
## <a name="using-a-custom-attribute-to-register-a-vspackage"></a>Pomocí vlastních atributů k registraci VSPackage  
 V některých případech musíte vytvořit nový atribut registrace pro rozšíření. Atributy registrace můžete použít, chcete-li přidat nového klíče registru nebo přidání nové hodnoty do existující klíče. Nový atribut musí být odvozeny od <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, a musí přepsat <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> a <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> metody.  
  
## <a name="creating-a-registry-key"></a>Vytvoření klíče registru  
 Následující kód vytvoří vlastní atribut **vlastní** podklíčů pod klíčem pro VSPackage, která je registrována.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
  
```  
  
## <a name="creating-a-new-value-under-an-existing-registry-key"></a>Vytvoření nové hodnoty v části existující klíč registru  
 Můžete přidat vlastní hodnoty do existujícího klíče. Následující kód ukazuje, jak přidat novou hodnotu do VSPackage registrační klíč.  
  
```csharp  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [VSPackages](../extensibility/internals/vspackages.md)