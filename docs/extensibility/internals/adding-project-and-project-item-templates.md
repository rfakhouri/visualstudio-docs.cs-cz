---
title: "Přidání projektu a šablony položek projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], adding
- project items [Visual Studio], adding
ms.assetid: 8c59217f-56e5-4540-a73b-cd10de189373
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0201d2f282365a028b6251324b07276c995621ba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adding-project-and-project-item-templates"></a>Přidání projektů a šablon položek projektu
Když vytvoříte vlastní typy projektů, je nutné zadat podpora pro přidání nových projektů a položek projektu pomocí standardní [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývoj prostředí (IDE) dialogových oken. Následující témata popisují různé postupy pro přidání projektů a položek projektů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Kontext projektu](../../extensibility/internals/project-context.md)  
 Vysvětluje, že projekt poskytuje většinu kontextové informace pro co ukáže v prostředí.  
  
 [Priorita projektu](../../extensibility/internals/project-priority.md)  
 Vysvětluje, že položka projektu je obvykle členem jeden projektu, abyste zabránili nejednoznačné identifikaci o tom, které se používá projektu otevřete položku.  
  
 [Ostatní soubory projektu](../../extensibility/internals/miscellaneous-files-project.md)  
 Poskytuje informace o dva typy editory, které lze použít k otevření souborů v projektu a roli, že projekt hraje při určení, které editoru použijte, pokud je otevřen položka projektu.  
  
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)  
 Vysvětluje, co se stane, když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vytvoření projektu.  
  
 [Přidávání položek do pro přidání nové položky dialogových oken](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)  
 Vysvětluje postup přidání položky na **přidat novou položku** dialogové okno.  
  
 [Přidávání adresářů do dialogového okna Nový projekt](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)  
 Poskytuje příklad registrace nového adresáře, který obsahuje vlastní šablony, které jsou zpřístupněny VSPackage.  
  
 [Přidávání do adresáře přidat novou položku – dialogové okno](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)  
 Poskytuje příklad registrace novou sadu adresářů pro **přidat novou položku** dialogové okno.  
  
 [Příkazy definované IDE pro rozšíření projektu systémy](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)  
 Uvádí různé typy položek příkazu pro rozšíření projektu systémy.  
  
 [CATIDs pro objekty, které jsou obvykle používány k rozšíření projektů](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)  
 Uvádí CATIDs pro objekty, které se používají k rozšíření [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projektu systémy.  
  
## <a name="related-sections"></a>Související oddíly  
 [Postupy: otevření projektu konkrétní editory](../../extensibility/how-to-open-project-specific-editors.md)  
 Poskytuje podrobné pokyny k otevření položku vnitřně vázaný na konkrétní editor pro projekt.  
  
 [Postupy: otevření standardní editory](../../extensibility/how-to-open-standard-editors.md)  
 Poskytuje podrobné pokyny k otevření standardního editoru.  
  
 [Projekt podtypů](../../extensibility/internals/project-subtypes.md)  
 Obsahuje odkazy na projekt dílčí koncepční témata. Projekt podtypů rozšířit stávající [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projekty.  
  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Obsahuje odkazy na další témata, které nabízí informace o tom, jak navrhnout nové typy projektů.