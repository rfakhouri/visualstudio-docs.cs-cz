---
title: 'Postupy: Upgrade vlastní úvodní stránku sady Visual Studio | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78342ce6-36c8-485b-a5f6-760e7a420a26
caps.latest.revision: 8
manager: douge
ms.openlocfilehash: 2b41e92cd086d908f0a2fa0e6e9c4f99a1e24cc5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672184"
---
# <a name="how-to-upgrade-a-visual-studio-custom-start-page"></a>Postupy: Upgrade vlastní úvodní stránku sady Visual Studio
Můžete upgradovat Visual Studio 2010 nebo Visual Studio 2012 vlastní úvodní stránku do sady Visual Studio 2015 podle pokynů uvedených níže.  
  
> [!WARNING]
>  Vlastní úvodní stránku upgradovat v tomto postupu je vytvořena s [vlastní úvodní stránky](http://visualstudiogallery.msdn.microsoft.com/f655a5dc-1a2d-4eca-b774-76c352c03b87) šablony pro Galerii Visual Studio. Úvodní stránka může mít jiné funkce, které je potřeba upgradovat.  
  
### <a name="to-upgrade-a-custom-start-page-to-visual-studio-2015"></a>Vlastní úvodní stránku upgradovat na Visual Studio 2015  
  
1.  Ujistěte se, že jsou nainstalované Visual Studio 2015 a Visual Studio 2015 SDK. Můžete si stáhnout VSSDK z [Microsoft Visual Studio 2013 SDK](http://go.microsoft.com/?linkid=9863867).  
  
2.  Otevřete svůj projekt vlastní šablony. Zobrazí se zpráva s upozorněním, že projekt je třeba upgradovat. Klikněte na tlačítko **OK** a počkat na dokončení.  
  
3.  Ve vlastnostech projektu pro projekt úvodní stránky a řízení projektu, ujistěte se, že Cílová architektura, která je minimálně rozhraní .NET Framework 4.5.  
  
4.  V kategorii ladění vlastnosti projektu pro projekt úvodní stránky nastavení cesty k verzi sady Visual Studio 2015 devenv.exe.  
  
5.  V odkazech projektu pro oba projekty odkazy na Microsoft.VisualStudio.Shell.11.0 odebrat a přidat odkazy na Microsoft.VisualStudio.Shell.14.0.  
  
6.  Otevřete StartPage.xaml pomocí editoru XML a proveďte následující změny:  
  
    1.  Aktualizace oboru názvů. Změňte následující řádky:  
  
        ```  
  
        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0"  
         xmlns:vsfxim="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"  
        xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.11.0"  
        ```  
  
         pro následující:  
  
        ```  
  
        xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.142.0"  
         xmlns:vsfxim="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.14.0"  
        xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
        ```  
  
7.  Otevřete MyControl.xaml a změňte odkaz na obor názvů `xmlns:vs="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.11.0"` k `xmlns:vs="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"` .