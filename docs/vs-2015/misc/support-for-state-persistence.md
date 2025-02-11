---
title: Podpora pro trvalost stavu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- state persistence, managed package framework support
- managed package framework, state persistence support
- state, persistence
ms.assetid: d25866f2-8d1f-477f-8aa5-3af3fbbf6e97
caps.latest.revision: 15
manager: jillfra
ms.openlocfilehash: 6dc542d2e410b79a21e436a1881c06bd3cc4eef8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62434316"
---
# <a name="support-for-state-persistence"></a>Podpora pro trvalost stavu
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] můžete spravovat stav běžně používané objekty. Například řešení a projektu vlastnosti jsou uloženy do a obnoven ze souborů řešení a projektu. Uživatelská nastavení můžete exportovat do a importovat ze souborů s nastavením.  
  
 Rozšíření VSPackages se zpravidla spoléhají na místní úložiště, v systémovém registru nebo ve složce application data pro aktuálního uživatele nebo počítač. Hodnoty, které vyžadují malé množství místa pro ukládání dat, jako jsou celá čísla a řetězce, jsou obvykle uložena v registru systému. Hodnoty, které vyžadují hodně místa pro ukládání dat, jako je například rastrové obrázky, jsou uloženy v souboru. Samotný cestu k souboru můžete uložit v systémovém registru. Mechanismus trvalého musí mít oprávnění pro přístup k místním úložišti.  
  
## <a name="support-for-locating-local-storage"></a>Podpora pro vyhledání místní úložiště  
 <xref:Microsoft.VisualStudio.Shell.Package> Třída poskytuje podporu pro vyhledání informací o stavu ve složce systému registru nebo application data pro aktuálního uživatele nebo počítač.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>  
 Vrátí cestu v místním počítači kořenový klíč registru pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], například HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0Exp.  
  
 Kořen místního registru se získávají z <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> služby. Pokud je k dispozici, se získávají z <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute> atribut sady VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>  
 Vrátí cestu aktuálního uživatele (pro jednotlivé počítače) kořenový klíč registru pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], například HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp.  
  
 Kořen místního registru se získávají z <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> služby. Pokud je k dispozici, se získávají z atributu DefaultLocalRegistryRoot sady VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserDataPath%2A>  
 Vrátí cestu k adresáři, který slouží jako běžné úložiště pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] data aktuální roamingu uživatele, například C:\Documents and nastavení\\*YourAccountName*\Application Data\Microsoft\ VisualStudio\8.0Exp.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserLocalDataPath%2A>  
 Vrátí cestu k adresáři, který slouží jako běžné úložiště pro [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] data aktuální nepřenosných uživatele, například C:\Documents and nastavení\\*YourAccountName*\Local Data\Microsoft\VisualStudio\8.0Exp.  
  
## <a name="see-also"></a>Viz také  
 [Stav balíčku VSPackage](../misc/vspackage-state.md)