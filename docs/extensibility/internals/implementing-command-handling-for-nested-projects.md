---
title: Implementace zpracování příkazů pro vnořené projekty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 66f89476e6d4a8fa009dbe921113c9e4cac54916
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66313201"
---
# <a name="implementing-command-handling-for-nested-projects"></a>Implementace zpracování příkazů pro vnořené projekty
Rozhraní IDE lze předat příkazy, které se předají <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní pro vnořené projekty nebo nadřazené projekty můžete filtrovat nebo přepište příkazy.

> [!NOTE]
> Dají se filtrovat jenom příkazy, které obvykle zpracovává nadřazený projekt. Příkazy, jako **sestavení** a **nasadit** , které jsou zpracovávány integrovaného vývojového prostředí se nedají filtrovat.

 Následující kroky popisují proces pro implementaci zpracování příkazu.

## <a name="procedures"></a>Procedury

#### <a name="to-implement-command-handling"></a>K implementaci zpracování příkazu

1. Když uživatel vybere vnořený projekt nebo uzlu v vnořený projekt:

   1. Volání rozhraní IDE <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody.

      – nebo –

   2. Pokud příkaz vytvoří se v okně hierarchie, například příkaz místní nabídky v Průzkumníku řešení, zavolá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> metodu na nadřazený objekt projektu.

2. Nadřazený projekt můžete prozkoumat parametry, které se mají předat `QueryStatus`, jako například `pguidCmdGroup` a `prgCmds`, chcete-li zjistit, zda by měl nadřazený projekt filtrování příkazů. Pokud nadřazený projekt je implementováno s cílem filtrovat příkazy, by měl nastavit:

   ```
   prgCmds[0].cmdf = OLECMDF_SUPPORTED;
   // make sure it is disabled
   prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;
   ```

    Pak by měl vrátit nadřazený projekt `S_OK`.

    Pokud nadřazený projekt nefiltruje příkazu, měla by jenom vrátit `S_OK`. V tomto případě rozhraní IDE automaticky směruje příkaz podřízený projekt.

    Nadřazený projekt nebude muset příkaz směrovat podřízeného projektu. Integrované vývojové prostředí provádí tento úkol...

## <a name="see-also"></a>Viz také
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>
- [Příkazy, nabídky a panely nástrojů](../../extensibility/internals/commands-menus-and-toolbars.md)
- [Vnoření projektů](../../extensibility/internals/nesting-projects.md)