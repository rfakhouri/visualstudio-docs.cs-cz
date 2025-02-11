---
title: Registrace a zrušení registrace rozšíření VSPackages | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
caps.latest.revision: 36
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1f6bc85fb00c15831dcf1a9f64e4b886272df218
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68193821"
---
# <a name="registering-and-unregistering-vspackages"></a>Registrace a zrušení registrace rozšíření VSPackages
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Použít atributy k evidenci VSPackage, ale  
  
## <a name="registering-a-vspackage"></a>Registrace VSPackage  
 Atributy můžete použít k řízení registrací spravovaných rozšíření VSPackages. Veškeré informace o registraci je obsažen v souboru .pkgdef. Další informace o registraci na základě souboru, naleznete v tématu [nástroj CreatePkgDef](../extensibility/internals/createpkgdef-utility.md).  
  
 Následující kód ukazuje, jak používat atributy standardní registrace k registraci vašeho balíčku VSPackage.  
  
```csharp  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]  
public sealed class BasicPackage : Package  
{. . .}  
```  
  
## <a name="unregistering-an-extension"></a>Zrušení registrace rozšíření  
 Pokud byl experimentování s spoustu různých rozšíření VSPackages a chcete ho odebrat z experimentální instanci, můžete pouze spustit **resetování** příkazu. Vyhledejte **resetovat experimentální instanci aplikace Visual Studio** na úvodní stránce vašeho počítače nebo spuštěním tohoto příkazu z příkazového řádku:  
  
```vb  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp  
```  
  
 Pokud chcete odinstalovat rozšíření, které jste nainstalovali na vývoj instanci sady Visual Studio, přejděte na **nástrojů / rozšíření a aktualizace**najít rozšíření a klikněte na tlačítko **odinstalovat**.  
  
 Pokud z nějakého důvodu ani jeden z těchto metod úspěšná na odinstalovat rozšíření, můžete zrušit registraci balíčku VSPackage sestavení z příkazového řádku takto:  
  
```  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg” /unregister <pathToVSPackage assembly>  
```  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
