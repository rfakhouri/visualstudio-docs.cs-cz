---
title: Registrace přípony názvů souborů pro nasazení vedle sebe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions, registering for side-by-side
ms.assetid: 9ab046a2-147d-4167-aa14-7d661b1eaaa5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae7d7307ef12184dcbfc29254ec5cbae9ff55bb8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31136307"
---
# <a name="registering-file-name-extensions-for-side-by-side-deployments"></a>Registrace přípony názvů souborů pro nasazení vedle sebe
Pro VSPackages nasadí v prostředí s vedle sebe, je nutné zaregistrovat přípony názvů souborů přidružení souborů k správnou verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Pokud nechcete použít příponu názvu souboru specifické pro verzi, registrace umožňuje uživatelům, otevřete projekt a projekt položky souborů v příslušné verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přípony názvů souborů](../extensibility/about-file-name-extensions.md)  
 Popisuje, jak jsou registrované přípony názvů souborů.  
  
 [Určení popisovačů souborů pro přípony názvů souborů](../extensibility/specifying-file-handlers-for-file-name-extensions.md)  
 Poskytuje informace o postupu při registraci aplikace, které můžete otevřít, upravit a tak dále, konkrétní příponu názvu.  
  
 [Registrace operací pro přípony názvů souborů](../extensibility/registering-verbs-for-file-name-extensions.md)  
 Popisuje postup registrace příkazy.  
  
 [Správa přidružení souborů vedle sebe](../extensibility/managing-side-by-side-file-associations.md)  
 Popisuje, jak zpracovat souběžně sdílená zařízení, ve které konkrétní verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] by měla být volána k otevření souboru.  
  
## <a name="related-sections"></a>Související oddíly  
 [Podpora více verzí sady Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md)  
 Popisuje problémy související s více verzemi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vaše VSPackage během vývoje a nasazení pro koncové uživatele.