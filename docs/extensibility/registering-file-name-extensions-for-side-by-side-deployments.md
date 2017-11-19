---
title: "Registrace přípony názvů souborů pro nasazení vedle sebe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: file extensions, registering for side-by-side
ms.assetid: 9ab046a2-147d-4167-aa14-7d661b1eaaa5
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 42c1c573554ee6d92b3967517bdcdf0f3106ce61
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="registering-file-name-extensions-for-side-by-side-deployments"></a>Registrace přípony názvů souborů pro nasazení vedle sebe
Pro VSPackages nasadí v prostředí s vedle sebe, je nutné zaregistrovat přípony názvů souborů přidružení souborů k správnou verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Pokud nechcete použít příponu názvu souboru specifické pro verzi, registrace umožňuje uživatelům, otevřete projekt a projekt položky souborů v příslušné verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [O přípony názvů souborů](../extensibility/about-file-name-extensions.md)  
 Popisuje, jak jsou registrované přípony názvů souborů.  
  
 [Určení souboru obslužné rutiny pro přípony názvu souboru](../extensibility/specifying-file-handlers-for-file-name-extensions.md)  
 Poskytuje informace o postupu při registraci aplikace, které můžete otevřít, upravit a tak dále, konkrétní příponu názvu.  
  
 [Registrace příkazy pro přípony názvu souboru](../extensibility/registering-verbs-for-file-name-extensions.md)  
 Popisuje postup registrace příkazy.  
  
 [Správa přidružení souboru vedle sebe](../extensibility/managing-side-by-side-file-associations.md)  
 Popisuje, jak zpracovat souběžně sdílená zařízení, ve které konkrétní verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] by měla být volána k otevření souboru.  
  
## <a name="related-sections"></a>Související oddíly  
 [Podpora více verzí sady Visual Studio](../extensibility/supporting-multiple-versions-of-visual-studio.md)  
 Popisuje problémy související s více verzemi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vaše VSPackage během vývoje a nasazení pro koncové uživatele.