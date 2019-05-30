---
title: Správa vrátit zpět a znovu pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1a223d23cb792f13f1df9f869a540ffa61f50f9b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340633"
---
# <a name="manage-undo-and-redo-by-using-the-legacy-api"></a>Správa vrácení zpět a znovu pomocí starší verze rozhraní API
Editory musí podporovat operace vrácení zpět, které umožňují uživateli obrátit jejich poslední změny při jejich upravit kód. Většina editory implementovaná v rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] může mít podpora pro vracení zpět automaticky poskytuje integrované vývojové prostředí (IDE).

## <a name="in-this-section"></a>V tomto oddílu
- [Postupy: Implementace správy zpět](../extensibility/how-to-implement-undo-management.md) poskytuje možnost vrácení zpět pro editory s jedním nebo více zobrazení.

- [Postupy: Vymazat zásobník vrácení zpátky](../extensibility/how-to-clear-the-undo-stack.md) popisuje, jak vymazat zásobník akcí zpět.

- [Postupy: Použijte správu propojená operace vrácení zpět](../extensibility/how-to-use-linked-undo-management.md) Incorporates propojené řízení zpět do editoru.

## <a name="reference"></a>Odkaz
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> Poskytuje správu vrácení zpět pro editor, který podporuje několik zobrazení.
