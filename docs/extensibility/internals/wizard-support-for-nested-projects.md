---
title: "Podpora průvodce pro vnořené projekty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add Item wizard
- nested projects, wizard support
- New Project wizard
ms.assetid: 1b496acc-b326-4cdb-bb48-e3b5c6f12e05
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7191d31d4ec53fb26f4ab20114201836f1b58fc5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="wizard-support-for-nested-projects"></a>Podpora průvodce pro vnořené projekty
Rozhraní IDE spustí dvou průvodců, které můžete implementovat nadřazený projekt pro vnořené projekty: **nový projekt** průvodce a **přidat položku** průvodce.  
  
 Pokud uživatel spustí **nový projekt** Průvodce výběrem **přidat projekt** a kliknutím na **nový projekt** v nabídce Soubor nebo výběrem **přidat** a kliknete pravým tlačítkem **nový projekt** v Průzkumníku řešení rozhraní IDE spustí **AddProject** příkaz a provádění nadřazený projekt **AddProject**příkaz buď vrátí soubor šablony projektu, nebo soubor průvodce (.vsz), který obsahuje sadu kontextové parametry.  
  
 Podobně nadřazený projekt implementace **AddItem** průvodců vrátí .vsz Soubor, který má jinou sadu kontextové parametry.  
  
 Další informace o Průvodci najdete v tématu [průvodce (. Soubor vsz)](../../extensibility/internals/wizard-dot-vsz-file.md), [kontextové parametry](../../extensibility/internals/context-parameters.md) a [registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [Vnoření projekty](../../extensibility/internals/nesting-projects.md)