---
title: Správa vrátit zpět a znovu pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0bb1cc883941c8365e4d4341c93084beaef44d48
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696374"
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>Správa zpět a znovu pomocí starší verze rozhraní API
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Správa vrátit zpět a znovu s použitím rozhraní API starší verze](https://docs.microsoft.com/visualstudio/extensibility/managing-undo-and-redo-by-using-the-legacy-api).  
  
Editory musí podporovat operace vrácení zpět, které umožňují uživateli obrátit jejich poslední změny při jejich upravit kód. Většina editory implementovaná v rámci [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] může mít podpora pro vracení zpět automaticky poskytuje integrované vývojové prostředí (IDE).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Implementace správy zpět](../extensibility/how-to-implement-undo-management.md)  
 Poskytuje možnost vrácení zpět pro editory s jedním nebo více zobrazení.  
  
 [Postupy: vymazání zásobník vrácení zpátky](../extensibility/how-to-clear-the-undo-stack.md)  
 Popisuje, jak vymazat zásobník akcí zpět.  
  
 [Postupy: použití správy propojená operace vrácení zpět](../extensibility/how-to-use-linked-undo-management.md)  
 Do editoru v sobě zahrnuje správu propojená operace vrácení zpět.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 Poskytuje správu vrácení zpět pro editor, který podporuje několik zobrazení.  
  
## <a name="related-sections"></a>Související oddíly

