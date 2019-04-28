---
title: Podpora více verzí sady Visual Studio | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, supporting multiple versions
- VSPackages, side-by-side compatibility
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 566407f4d15fdaedaf9a89eb50648e555a370750
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434538"
---
# <a name="supporting-multiple-versions-of-visual-studio"></a>Podpora více verzí sady Visual Studio
Termín *vedle sebe* znamená, že můžete nainstalovat a spravovat více verzí produktů ve stejném počítači. Pro balíčky VSPackages, to znamená, že uživatel může mít několik verzí sady Visual Studio nainstalované ve stejném počítači. Však nemůže mít vedle sebe verzích vaše rozšíření VSPackages načteno do jedné verze sady Visual Studio.

 Než provedete vašeho balíčku VSPackage moci být načtena do vedle sebe verzích sady Visual Studio, zvažte následující:

- Je nutné určit strategii implementace vedle sebe, kterou chcete sledovat.

   Další informace najdete v tématu [výběr mezi sdílené a vyvíjených balíčků VSPackage](../extensibility/choosing-between-shared-and-versioned-vspackages.md).

- Řešení a projektu formátů souborů se musí vejít strategie implementace.

   Další informace najdete v tématu [upgrade projektů vlastní](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects) a [registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md).

- Instalační program musí umět zpracovat strategie implementace tak, aby se systémovou správou verzí komponenty a komponenty sdílené mezi všemi verzemi správně nainstalovaný a zaregistrovaný.

   Další informace najdete v tématu [instalace rozšíření VSPackages s Windows Installer](../extensibility/internals/installing-vspackages-with-windows-installer.md) a také [Správa komponent](../extensibility/internals/component-management.md).

  > [!NOTE]
  > Nainstalovat verzi sady Visual Studio nainstaluje taky odpovídající verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Například instalace sady Visual Studio 2010 a Visual Studio 2012 ve stejném počítači nainstaluje taky verze 4.0 a 4.5 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]v uvedeném pořadí.

## <a name="in-this-section"></a>V tomto oddílu
- [Volba mezi sdílené a vyvíjených balíčků VSPackage](../extensibility/choosing-between-shared-and-versioned-vspackages.md) vysvětluje, jak vyřešit problémy vedle sebe ve vaší VSPackage.

- [Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md) popisuje, jak vaše VSPackage přidružení souborů zaregistrovat ve scénáři vedle sebe.

## <a name="related-sections"></a>Související oddíly
- [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../extensibility/internals/installing-vspackages-with-windows-installer.md)
