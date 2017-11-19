---
title: "Podpora více verzí sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, supporting multiple versions
- VSPackages, side-by-side compatibility
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cc9c13ecf6a5cc6e62caa897adce16830026261a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="supporting-multiple-versions-of-visual-studio"></a>Podpora více verzí sady Visual Studio
Termín *vedle sebe* znamená, že můžete nainstalovat a spravovat více verzí produktu na stejném počítači. Pro VSPackages, to znamená, že uživatel může mít několik verzí sady Visual Studio nainstalované na stejném počítači. Ale nemůže mít vedle sebe verze vaší VSPackages načíst do jediné verze sady Visual Studio.  
  
 Dříve, než vaše VSPackage moci být načtena do souběžně sdílená verze sady Visual Studio, zvažte následující:  
  
-   Je třeba určit strategii implementace vedle sebe, kterou chcete provést.  
  
     Další informace najdete v tématu [výběr mezi sdílené a verzí VSPackages](../extensibility/choosing-between-shared-and-versioned-vspackages.md).  
  
-   Vaše řešení a projektu formáty souborů se musí vejít strategie implementace.  
  
     Další informace najdete v tématu [upgrade projektů vlastní](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects) a [registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md).  
  
-   Vaše instalační program musí zpracovávat strategie implementace tak, aby verzí a také komponenty sdílené mezi všemi verzemi správně nainstalovaný a zaregistrovaný.  
  
     Další informace najdete v tématu [instalaci VSPackages pomocí Instalační služby systému Windows](../extensibility/internals/installing-vspackages-with-windows-installer.md) a také [správu součástí](../extensibility/internals/component-management.md).  
  
    > [!NOTE]
    >  Instalaci verze sady Visual Studio se nainstaluje také odpovídající verzi systému [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Například instalaci sady Visual Studio 2010 a Visual Studio 2012 na stejném počítači se nainstaluje také verze 4.0 a 4.5 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], v uvedeném pořadí.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Volba mezi VSPackages sdílené a verzí](../extensibility/choosing-between-shared-and-versioned-vspackages.md)  
 Vysvětluje, jak řešit problémy vedle sebe v vaší VSPackage.  
  
 [Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)  
 Popisuje, jak vaše VSPackage registraci přidružení souborů ve scénáři vedle sebe.  
  
## <a name="related-sections"></a>Související oddíly  
 [Instalace VSPackages pomocí Instalační služby systému Windows](../extensibility/internals/installing-vspackages-with-windows-installer.md)  
