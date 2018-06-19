---
title: Řešení potíží s registrací RegPkg balíček | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4857e41888962a92dced87d63fa2b63161ecac55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137115"
---
# <a name="troubleshooting-regpkg-package-registration"></a>Řešení potíží s registrací RegPkg balíčku
> [!NOTE]
>  Pomocí souborů .pkgdef je upřednostňovaný způsob, jak zaregistrovat balíčky v sadě Visual Studio. To umožňuje nasazení rozšíření aniž by museli získat přístup k registru systému. Pkgdef soubory jsou vytvořeny pomocí [CreatePkgDef nástroj](../../extensibility/internals/createpkgdef-utility.md).  
  
 Registrace balíčku pomocí RegPkg v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], musíte použít verzi RegPkg, který je vhodný pro svůj balíček.  
  
## <a name="regpkg-versions-related-to-package-versions"></a>RegPkg verze související se verze balíčku  
 Existují dvě verze RegPkg. Je součástí jedné verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Tato verze použijte k registraci balíčky, které byly vytvořené pomocí jedné z následujících sestavení:  
  
1.  Microsoft.VisualStudioShell.9.0.dll  
  
2.  Microsoft.VisualStudioShell.10.0.dll  
  
3.  Microsoft.VisualStudioShell.11.0.dll  
  
 Balíčky, které byly vytvořené pomocí dřívějších sestavení Microsoft.VisualStudio.Shell.dll ji nelze zaregistrovat.  
  
 Starší verzi RegPkg můžete zaregistrovat balíčky, které byly vytvořené pomocí Microsoft.VisualStudio.Shell.dll sestavení. Je však nelze zaregistrovat balíčky vytvořené pomocí novější verze tohoto sestavení.  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../../extensibility/internals/vspackages.md)