---
title: Registrace a zrušení registrace rozšíření VSPackages | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 701700ba9d5c6db1e5858a2419e1b2c0fa950ae5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66334296"
---
# <a name="register-and-unregister-vspackages"></a>Registrace a zrušení registrace rozšíření VSPackages
Použít atributy k evidenci VSPackage, ale

## <a name="register-a-vspackage"></a>Zaregistrujte VSPackage
 Atributy můžete použít k řízení registrací spravovaných rozšíření VSPackages. Veškeré informace o registraci je součástí *.pkgdef* souboru. Další informace o registraci na základě souboru, naleznete v tématu [nástroj CreatePkgDef](../extensibility/internals/createpkgdef-utility.md).

 Následující kód ukazuje, jak používat atributy standardní registrace k registraci vašeho balíčku VSPackage.

```csharp
[PackageRegistration(UseManagedResourcesOnly = true)]
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]
public sealed class BasicPackage : Package
{
    // ...
}
```

## <a name="unregister-an-extension"></a>Zrušit registraci rozšíření
 Pokud byl experimentování s spoustu různých rozšíření VSPackages a chcete ho odebrat z experimentální instanci, můžete pouze spustit **resetování** příkazu. Vyhledejte **resetovat experimentální instanci aplikace Visual Studio** na úvodní stránce vašeho počítače nebo spuštěním tohoto příkazu z příkazového řádku:

```cmd
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp
```

 Pokud chcete odinstalovat rozšíření, které jste nainstalovali na vývoj instanci sady Visual Studio, přejděte na **nástroje** > **rozšíření a aktualizace**najít rozšíření a klikněte na tlačítko  **Odinstalujte**.

 Pokud z nějakého důvodu ani jeden z těchto metod úspěšná na odinstalovat rozšíření, můžete zrušit registraci balíčku VSPackage sestavení z příkazového řádku takto:

```cmd
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg" /unregister <pathToVSPackage assembly>
```

<a name="using-a-custom-registration-attribute-to-register-an-extension"></a>

## <a name="use-a-custom-registration-attribute-to-register-an-extension"></a>Použijte atribut vlastní registrace k registraci rozšíření

V některých případech budete muset vytvořit nový atribut registrace pro vaše rozšíření. Přidat nové klíče registru nebo přidat nové hodnoty pro existující klíče, můžete použít atributy registrace. Nový atribut musí být odvozen od <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, a musí přepsat <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> a <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> metody.

### <a name="create-a-custom-attribute"></a>Vytvoření vlastního atributu

Následující kód ukazuje, jak vytvořit nový atribut registrace.

```csharp
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]
public class CustomRegistrationAttribute : RegistrationAttribute
{
}
```

 <xref:System.AttributeUsageAttribute> Se používá na třídy atributů k určení ovládací prvek programu (třídy, metody atd.), které se vztahují atribut, zda jej lze použít více než jednou a určuje, zda mohou dědit.

### <a name="create-a-registry-key"></a>Vytvoření klíče registru

Následující kód vytvoří vlastní atribut **vlastní** podklíče pod klíčem pro sady VSPackage, která je registrována.

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

### <a name="create-a-new-value-under-an-existing-registry-key"></a>Vytvořte novou hodnotu existujícího klíče registru

Vlastní hodnoty můžete přidat do existujícího klíče. Následující kód ukazuje, jak přidat novou hodnotu balíčku VSPackage registrační klíč.

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

## <a name="see-also"></a>Viz také:
- [Balíčky VSPackage](../extensibility/internals/vspackages.md)
