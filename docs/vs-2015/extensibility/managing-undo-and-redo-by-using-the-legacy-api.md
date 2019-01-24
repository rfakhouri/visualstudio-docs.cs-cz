---
title: Správa vrátit zpět a znovu pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7c2133c75b32e56c1a054740bd829bd04cac97cc
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797307"
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>Správa zpět a znovu pomocí starší verze rozhraní API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Editory musí podporovat operace vrácení zpět, které umožňují uživateli obrátit jejich poslední změny při jejich upravit kód. Většina editory implementovaná v rámci [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] může mít podpora pro vracení zpět automaticky poskytuje integrované vývojové prostředí (IDE).  
  
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
  
## <a name="related-sections"></a>Související oddíly
