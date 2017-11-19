---
title: "Registrace a zrušení registrace VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4443195babbe3f8926633a992aa942dcb80dc3f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="registering-and-unregistering-vspackages"></a>Registrace a zrušení registrace VSPackages
Použijte atributy k registraci VSPackage, ale  
  
## <a name="registering-a-vspackage"></a>Registrace VSPackage  
 Atributy můžete použít k řízení registrace spravované VSPackages. Všechny informace o registraci je obsažený v souboru .pkgdef. Další informace o registraci na základě souborů najdete v tématu [CreatePkgDef nástroj](../extensibility/internals/createpkgdef-utility.md).  
  
 Následující kód ukazuje, jak použít atributy standardní registrace k registraci vaší VSPackage.  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]  
public sealed class BasicPackage : Package  
{. . .}  
```  
  
## <a name="unregistering-an-extension"></a>Zrušení registrace rozšíření  
 Pokud byla experimentování se spoustu různých VSPackages a chcete je odebrat z experimentální instance, stačí můžete spustit **resetovat** příkaz. Vyhledejte **resetovat Visual Studio experimentální instanci** na stránce start počítače, nebo spuštěním tohoto příkazu z příkazového řádku:  
  
```vb  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp  
```  
  
 Pokud chcete odinstalovat rozšíření, které jste nainstalovali ve vaší instanci vývoj sady Visual Studio, přejděte na **nástroje nebo rozšíření a aktualizace**, najít rozšíření a klikněte na tlačítko **odinstalovat**.  
  
 Pokud z nějakého důvodu ani jeden z těchto metod úspěšné při odinstalaci rozšíření, můžete zrušit registraci VSPackage sestavení z příkazového řádku následujícím způsobem:  
  
```  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg" /unregister <pathToVSPackage assembly>  
```  
  
<a name="using-a-custom-registration-attribute-to-register-an-extension"></a>  
  
## <a name="use-a-custom-registration-attribute-to-register-an-extension"></a>Použijte atribut vlastní registrace k registraci rozšíření  
  
V některých případech musíte vytvořit nový atribut registrace pro rozšíření. Atributy registrace můžete použít, chcete-li přidat nového klíče registru nebo přidání nové hodnoty do existující klíče. Nový atribut musí být odvozeny od <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, a musí přepsat <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> a <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> metody.  
  
### <a name="creating-a-custom-attribute"></a>Vytváření vlastních atributů  
  
Následující kód ukazuje, jak vytvořit nový atribut registrace.  
  
```csharp  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
    public class CustomRegistrationAttribute : RegistrationAttribute  
    {  
    }  
```  
  
 <xref:System.AttributeUsageAttribute> Se používá na třídy atributů k určení do atribut týkající se oblasti, zda jej lze použít více než jednou, a jestli možné zdědit elementu programu (třída, metoda atd.).  
  
### <a name="creating-a-registry-key"></a>Vytvoření klíče registru  
  
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
  
### <a name="creating-a-new-value-under-an-existing-registry-key"></a>Vytvoření nové hodnoty v části existující klíč registru  
  
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