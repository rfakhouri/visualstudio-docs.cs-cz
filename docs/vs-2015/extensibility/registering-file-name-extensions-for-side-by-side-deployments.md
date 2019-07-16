---
title: Registrace přípony názvů souborů pro nasazení vedle sebe | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions, registering for side-by-side
ms.assetid: 9ab046a2-147d-4167-aa14-7d661b1eaaa5
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 354b91dd1282df9726c1ee9c47f610b0dfdd9c1a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68163699"
---
# <a name="registering-file-name-extensions-for-side-by-side-deployments"></a>Registrace přípony názvů souborů pro nasazení vedle sebe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pro balíčky VSPackages nasazení v prostředí vedle sebe, je nutné zaregistrovat přípony názvů souborů pro přidružení souborů k správnou verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Pokud nechcete použít příponu názvu souboru specifické pro verzi, registrace umožňuje uživatelům otevřete svůj projekt a projekt soubory položek v příslušné verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přípony názvů souborů](../extensibility/about-file-name-extensions.md)  
 Tento článek popisuje způsob registrace přípony názvů souborů.  
  
 [Určení popisovačů souborů pro přípony názvů souborů](../extensibility/specifying-file-handlers-for-file-name-extensions.md)  
 Poskytuje informace o postupu při registraci aplikace, které můžete otevřít, upravit a tak dále, konkrétní příponu.  
  
 [Registrace operací pro přípony názvů souborů](../extensibility/registering-verbs-for-file-name-extensions.md)  
 Tento článek popisuje postup registrace příkazů.  
  
 [Správa přidružení souborů vedle sebe](../extensibility/managing-side-by-side-file-associations.md)  
 Tento článek popisuje způsob zpracování-souběžnými instalacemi, ve kterém konkrétní verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] by mělo být vyvoláno pro otevření souboru.  
  
## <a name="related-sections"></a>Související oddíly  
 [Podpora více verzí sady Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md)  
 Popisuje problémy spojené s více verzemi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a vaše VSPackage během vývoje a nasazení tak, aby koncoví uživatelé.
