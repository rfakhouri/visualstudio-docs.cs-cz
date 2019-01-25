---
title: Nástroj pro Windows v registru | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, registering
ms.assetid: c4bb8add-7148-49e4-a377-01d059fd5524
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8cedb95ccd98c3d5bd5e05086cfd1b53b0f97cd9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54771845"
---
# <a name="tool-windows-in-the-registry"></a>Nástroj Windows v registru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Rozšíření VSPackages, které poskytují nástroje systému windows musíte zaregistrovat u [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] jako nástroj pro okno poskytovatelů. Okna nástrojů, které jsou vytvářeny instalační sadou Visual Studio balíček šablony se provést ve výchozím nastavení. Okno poskytovatelů nástrojů mít systémových klíčů registru, které určují atributy viditelnosti, jako je například výchozí velikost okna nástrojů a umístění, identifikátor GUID okna, která slouží jako podokno okna nástrojů a styl ukotvení.  
  
 Během vývoje registraci poskytovatelů spravovaných nástrojů okna okna nástrojů přidávání atributů do zdrojového kódu a následným spuštěním nástroje RegPkg.exe výsledného sestavení. Další informace najdete v tématu [registrace panelu nástrojů](../extensibility/registering-a-tool-window.md).  
  
## <a name="registering-unmanaged-tool-window-providers"></a>Registrace zprostředkovatele okno nespravované nástroj  
 Poskytovatelů nespravované nástrojů okna musíte zaregistrovat u [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] v části ToolWindows systémového registru. Následující fragment souboru .reg ukazuje, jak může být zaregistrovaný dynamického panelu nástrojů:  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\<version number>\ToolWindows\{f0e1e9a1-9860-484d-ad5d-367d79aabf55}]  
@="{01069cdd-95ce-4620-ac21-ddff6c57f012}"  
"Name"="Microsoft.Samples.VisualStudio.IDE.ToolWindow.DynamicWindowPane"  
"Float"="250, 250, 410, 430"  
"DontForceCreate"=dword:00000001  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\ToolWindows\{f0e1e9a1-9860-484d-ad5d-367d79aabf55}\Visibility]  
"{f1536ef8-92ec-443c-9ed7-fdadf150da82}"=dword:00000000  
```  
  
 V první klíč v předchozím příkladu, číslo verze je verze [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], jako jsou 7.1 nebo 8.0, podklíč {f0e1e9a1-9860-484d-ad5d-367d79aabf55} je identifikátor GUID z podokna okna nástrojů (DynamicWindowPane) a hodnota {výchozí 01069cdd-95ce-4620-ac21-ddff6c57f012} je identifikátor GUID balíčku VSPackage poskytují panel nástrojů. Vysvětlení podklíčů plovoucí desetinnou čárkou a DontForceCreate, najdete v článku [konfigurace zobrazení okna nástroje](../extensibility/tool-window-display-configuration.md).  
  
 Druhý volitelný klíč ToolWindows\Visibility, určuje identifikátory GUID příkazy, které vyžadují okno nástroje, které budou viditelné. V takovém případě nejsou žádné příkazy zadané. Další informace najdete v tématu [konfigurace zobrazení okna nástroje](../extensibility/tool-window-display-configuration.md).  
  
## <a name="see-also"></a>Viz také  
 [VSPackage Essentials](../misc/vspackage-essentials.md)
