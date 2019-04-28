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
ms.openlocfilehash: 83c9b1158319b580bc860982b6c51c9c28edf5af
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62433874"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nepodporované scénáře ladění v návrháři postupu provádění

Návrháři pracovních postupů v rozhraní .NET Framework 4 přidali spoustu nových funkcí, ale stále existují některé scénáře ladění, které nepodporuje.

Tady jsou nepodporované návrháře postupu provádění ladění scénářů:

- Provádění nelze pokračovat, až se upravil kód.

- Spuštění nemůže pokračovat z libovolného bodu v pracovním postupu (nastavit další).

- Provádění nelze pokračovat, dokud nenastane kurzoru (Spustit ke kurzoru).

- Chcete-li ladit pracovní postupy vytvořené v kódu bez použití návrháře nelze použít Návrháře postupu provádění.

- V Návrháři rozhraní .NET Framework 4 není možné ladit pracovní postupy vytvořené v dřívějších verzích Windows Workflow Foundation (WF).

- Zarážky nelze zadat u propojení mezi aktivitami nebo <xref:System.Activities.Statements.Flowchart> uzly.

- Během ladění není k dispozici do schránky.

- Zarážky nejsou zachovány při jsou aktivity kopírování a vložení.

- V okně zásobník volání nelze nastavit zarážky pracovního postupu.

- Při vytváření zarážky v návrháři **řádku** a **znak** nastavení v **Nová zarážka** nepoužívají dialogového okna.

- Zarážka okna nebo v místní nabídce nepodporuje následující sloupce nebo možnosti pro ladění pracovního postupu:

    - Podmínka

    - Počet přístupů

    - Při průchodu

    - Funkce

    - Data

    - Proces

    - Přejít na zpětný překlad