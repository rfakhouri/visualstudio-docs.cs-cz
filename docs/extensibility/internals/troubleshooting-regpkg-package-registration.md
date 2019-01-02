---
title: Řešení potíží s registrací balíčku RegPkg | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 54196fcacb5af5560482bf1b40ff21de57e175d8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900955"
---
# <a name="troubleshooting-regpkg-package-registration"></a>Řešení potíží s registrací balíčku RegPkg
> [!NOTE]
>  Preferovaný způsob, jak zaregistrovat balíčky v sadě Visual Studio je pomocí souborů .pkgdef. To umožňuje nasazení rozšíření bez nutnosti přístupu k registru systému. Pkgdef soubory jsou vytvořeny pomocí [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md).  
  
 K registraci balíčku RegPkg v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], musíte použít verzi RegPkg, která je vhodná pro váš balíček.  
  
## <a name="regpkg-versions-related-to-package-versions"></a>Související s verzí balíčku verze RegPkg  
 Existují dvě verze RegPkg. Je součástí jedné verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Pomocí této verze zaregistrovat balíčky, které jsou sestavené pomocí jedné z následujících sestavení:  
  
1. Microsoft.VisualStudioShell.9.0.dll  
  
2. Microsoft.VisualStudioShell.10.0.dll  
  
3. Microsoft.VisualStudioShell.11.0.dll  
  
   Balíčky, které jsou sestavené pomocí předchozích sestavení Microsoft.VisualStudio.Shell.dll se nemůže zaregistrovat.  
  
   V předchozích verzích RegPkg můžete zaregistrovat balíčky, které jsou sestavené s využitím Microsoft.VisualStudio.Shell.dll sestavení. Ale se nemůže zaregistrovat balíčky sestavené s použitím novější verze tohoto sestavení.  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)