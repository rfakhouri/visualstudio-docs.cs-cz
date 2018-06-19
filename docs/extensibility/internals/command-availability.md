---
title: Příkaz dostupnosti | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, context
- menu items, visibility contexts
ms.assetid: c74e3ccf-d771-48c8-a2f9-df323b166784
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 08f6ceb6c57eccf359b4aa23db7d693df3b86453
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128688"
---
# <a name="command-availability"></a>Příkaz dostupnosti

Kontext sady Visual Studio Určuje, které příkazy, které jsou k dispozici. Kontext, můžete změnit v závislosti na aktuální projekt, aktuální editor, VSPackages, která jsou načtena a dalších aspektů integrované vývojové prostředí (IDE).

## <a name="command-contexts"></a>Příkaz kontexty

Následující příkaz kontexty jsou nejobvyklejší.

-   **IDE** příkazy poskytované IDE jsou vždy k dispozici.

-   **VSPackage** VSPackages můžete definovat, když jsou příkazy k zobrazení nebo skrytí.

-   **Projekt** projektu příkazy jsou zobrazeny pouze pro aktuálně vybrané projektu.

-   **Editor** pouze jeden editor může být aktivní v čase. Příkazy z editoru aktivní jsou k dispozici. Editor úzce spolupracuje s služba jazyka. Služba jazyka musí zpracovat jeho příkazy v kontextu přidružené editoru.

-   **Typ souboru** editoru můžete načíst více než jeden typ souboru. Dostupné příkazy můžete změnit v závislosti na typu souboru.

-   **Aktivní okno** poslední okno aktivní dokument nastaví kontext uživatelské rozhraní (UI) pro vazeb klíče. Okno nástroje, který má klíč vazby tabulku, která se podobá interní webový prohlížeč může však také nastavit kontext uživatelského rozhraní. Pro více kartami dokumentu windows, jako je například HTML editor má každé kartě kontextu jiný příkaz identifikátor GUID. Po registraci okno nástroje je vždy k dispozici na **zobrazení** nabídky.

-   **Kontext uživatelského rozhraní** kontexty uživatelského rozhraní jsou určeny hodnoty <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT> třídy, například <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionBuilding_guid> při sestavuje řešení, nebo <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.Debugging_guid> když je aktivní ladicí program. Ve stejnou dobu může být aktivní více kontexty uživatelského rozhraní.

## <a name="defining-custom-context-guids"></a>Definování vlastních kontextu identifikátory GUID

Pokud příslušný příkaz kontextu, identifikátor GUID není již definována, můžete definovat jeden ve vašem VSPackage a pak programu mohla být aktivní nebo neaktivní podle potřeby řízení zobrazení vaší příkazů.

1.  Zaregistrovat identifikátory GUID kontextu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> metoda.

2.  Zjištění stavu kontextu GUID voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> metoda.

3.  Zapnutí a vypnutí identifikátory GUID kontextu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> metoda.

    > [!CAUTION]
    > Zajistěte, aby vaše VSPackage vzhledem k tomu může jsou na nich závislé jiné VSPackages neovlivní žádné existující kontext identifikátory GUID.

## <a name="see-also"></a>Viz také

- [Kontextové objekty výběru](../../extensibility/internals/selection-context-objects.md)
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)