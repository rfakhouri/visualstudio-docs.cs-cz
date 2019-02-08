---
title: Nepodporované scénáře ladění v návrháři postupu provádění
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 169f7d1cdd0976cac377f99f5f09b3c43948524c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918231"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nepodporované scénáře ladění v návrháři postupu provádění

Návrháři pracovních postupů v rozhraní .NET Framework 4 přidali spoustu nových funkcí, ale stále existují některé scénáře ladění, které nepodporuje.

Tady jsou nepodporované návrháře postupu provádění ladění scénářů:

-   Provádění nelze pokračovat, až se upravil kód.

-   Spuštění nemůže pokračovat z libovolného bodu v pracovním postupu (nastavit další).

-   Provádění nelze pokračovat, dokud nenastane kurzoru (Spustit ke kurzoru).

-   Chcete-li ladit pracovní postupy vytvořené v kódu bez použití návrháře nelze použít Návrháře postupu provádění.

-   V Návrháři rozhraní .NET Framework 4 není možné ladit pracovní postupy vytvořené v dřívějších verzích Windows Workflow Foundation (WF).

-   Zarážky nelze zadat u propojení mezi aktivitami nebo <xref:System.Activities.Statements.Flowchart> uzly.

-   Během ladění není k dispozici do schránky.

-   Zarážky nejsou zachovány při jsou aktivity kopírování a vložení.

-   V okně zásobník volání nelze nastavit zarážky pracovního postupu.

-   Při vytváření zarážky v návrháři **řádku** a **znak** nastavení v **Nová zarážka** nepoužívají dialogového okna.

-   Zarážka okna nebo v místní nabídce nepodporuje následující sloupce nebo možnosti pro ladění pracovního postupu:

    -   Podmínka

    -   Počet přístupů

    -   Při průchodu

    -   Funkce

    -   Data

    -   Proces

    -   Přejít na zpětný překlad