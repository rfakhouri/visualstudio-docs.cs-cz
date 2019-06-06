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
ms.openlocfilehash: 62d8a2ad847ef1b9aaad02b2739e8154b3148425
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747271"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nepodporované scénáře ladění v návrháři postupu provádění

Návrháře postupu provádění nepodporuje následující scénáře ladění:

- Provádění nelze pokračovat, až se upravil kód.

- Spuštění nemůže pokračovat z libovolného bodu v pracovním postupu (nastavit další).

- Provádění nelze pokračovat, dokud nenastane kurzoru (Spustit ke kurzoru).

- Chcete-li ladit pracovní postupy vytvořené v kódu bez použití návrháře nelze použít Návrháře postupu provádění.

- Pracovní postupy vytvořené v dřívějších verzích Windows Workflow Foundation (WF) není možné ladit v rozhraní .NET Framework 4 nebo novější.

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