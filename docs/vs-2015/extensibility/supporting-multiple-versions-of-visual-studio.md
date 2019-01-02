---
title: Podpora více verzí sady Visual Studio 2015 | Dokumentace Microsoftu
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio, supporting multiple versions
- VSPackages, side-by-side compatibility
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0e5f364cbdb799951bed8edeae78ce34c1ad7dea
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53955046"
---
# <a name="supporting-multiple-versions-of-visual-studio"></a>Podpora více verzí sady Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Termín *vedle sebe* znamená, že můžete nainstalovat a spravovat více verzí produktů ve stejném počítači. Pro balíčky VSPackages, to znamená, že uživatel může mít několik verzí sady Visual Studio nainstalované ve stejném počítači. Však nemůže mít vedle sebe verzích vaše rozšíření VSPackages načteno do jedné verze sady Visual Studio.

 Než provedete vašeho balíčku VSPackage moci být načtena do vedle sebe verzích sady Visual Studio, zvažte následující:

-   Je nutné určit strategii implementace vedle sebe, kterou chcete sledovat.

     Další informace najdete v tématu [výběr mezi sdílené a vyvíjených balíčků VSPackage](../extensibility/choosing-between-shared-and-versioned-vspackages.md).

-   Řešení a projektu formátů souborů se musí vejít strategie implementace.

     Další informace najdete v tématu [upgrade projektů vlastní](../misc/upgrading-custom-projects.md) a [registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md).

-   Instalační program musí umět zpracovat strategie implementace tak, aby se systémovou správou verzí komponenty a komponenty sdílené mezi všemi verzemi správně nainstalovaný a zaregistrovaný.

     Další informace najdete v tématu [instalace rozšíření VSPackages s Windows Installer](../extensibility/internals/installing-vspackages-with-windows-installer.md) a také [Správa komponent](../extensibility/internals/component-management.md).

    > [!NOTE]
    >  Nainstalovat verzi sady Visual Studio nainstaluje taky odpovídající verzi [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. Například instalace sady Visual Studio 2010 a Visual Studio 2012 ve stejném počítači nainstaluje taky verze 4.0 a 4.5 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]v uvedeném pořadí.

## <a name="in-this-section"></a>V tomto oddílu
 [Volba mezi sdílené a vyvíjených balíčků VSPackage](../extensibility/choosing-between-shared-and-versioned-vspackages.md) vysvětluje, jak vyřešit problémy vedle sebe ve vaší VSPackage.

 [Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md) popisuje, jak vaše VSPackage přidružení souborů zaregistrovat ve scénáři vedle sebe.

## <a name="related-sections"></a>Související oddíly
 [Instalace balíčků VSPackage](../misc/installing-vspackages.md) popisuje, jak sestavit a nainstalovat rozšíření VSPackages a jak podporovat uživatelům, kteří používají více verzí sady Visual Studio ve stejnou dobu.
