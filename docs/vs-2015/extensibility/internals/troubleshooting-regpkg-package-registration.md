---
title: Řešení potíží s registrací balíčku RegPkg | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c6b95b440d83b8f7158dadb2d757b6d5b1d1f392
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49245086"
---
# <a name="troubleshooting-regpkg-package-registration"></a>Řešení potíží s registrací balíčku RegPkg
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!NOTE]
>  Preferovaný způsob, jak zaregistrovat balíčky v sadě Visual Studio je pomocí souborů .pkgdef. To umožňuje nasazení rozšíření bez nutnosti přístupu k registru systému. Pkgdef soubory jsou vytvořeny pomocí [nástroj CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md).  
  
 K registraci balíčku RegPkg v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], musíte použít verzi RegPkg, která je vhodná pro váš balíček.  
  
## <a name="regpkg-versions-related-to-package-versions"></a>Související s verzí balíčku verze RegPkg  
 Existují dvě verze RegPkg. Je součástí jedné verze [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Pomocí této verze zaregistrovat balíčky, které jsou sestavené pomocí jedné z následujících sestavení:  
  
1.  Microsoft.VisualStudioShell.9.0.dll  
  
2.  Microsoft.VisualStudioShell.10.0.dll  
  
3.  Microsoft.VisualStudioShell.11.0.dll  
  
 Balíčky, které jsou sestavené pomocí předchozích sestavení Microsoft.VisualStudio.Shell.dll se nemůže zaregistrovat.  
  
 V předchozích verzích RegPkg můžete zaregistrovat balíčky, které jsou sestavené s využitím Microsoft.VisualStudio.Shell.dll sestavení. Ale se nemůže zaregistrovat balíčky sestavené s použitím novější verze tohoto sestavení.  
  
## <a name="see-also"></a>Viz také  
 [Vydání produktu](../../misc/releasing-a-visual-studio-integration-product.md)

