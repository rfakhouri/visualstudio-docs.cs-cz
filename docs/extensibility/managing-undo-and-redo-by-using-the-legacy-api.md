---
title: Správa vrátit zpět a znovu pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c43dc4892f1cf2a938a4ed29fc68bc55e99cc05e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54948125"
---
# <a name="manage-undo-and-redo-by-using-the-legacy-api"></a>Správa vrácení zpět a znovu pomocí starší verze rozhraní API
Editory musí podporovat operace vrácení zpět, které umožňují uživateli obrátit jejich poslední změny při jejich upravit kód. Většina editory implementovaná v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] může mít podpora pro vracení zpět automaticky poskytuje integrované vývojové prostředí (IDE).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Implementace správy zpět](../extensibility/how-to-implement-undo-management.md)  
 Poskytuje možnost vrácení zpět pro editory s jedním nebo více zobrazení.  
  
 [Postupy: Vymazat zásobník vrácení zpátky](../extensibility/how-to-clear-the-undo-stack.md)  
 Popisuje, jak vymazat zásobník akcí zpět.  
  
 [Postupy: Použijte správu propojená operace vrácení zpět](../extensibility/how-to-use-linked-undo-management.md)  
 Do editoru v sobě zahrnuje správu propojená operace vrácení zpět.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 Poskytuje správu vrácení zpět pro editor, který podporuje několik zobrazení.  
